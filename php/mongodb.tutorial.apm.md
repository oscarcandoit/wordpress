---
url: https://www.php.net/manual/en/mongodb.tutorial.apm.php
scraped_at: 2025-10-20T02:58:48.597Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Application Performance Monitoring (APM) [¶](https://www.php.net/manual/en/mongodb.tutorial.apm.php\#mongodb.tutorial.apm)

The extension contains an event subscriber API, which allows applications to
monitor commands and internal activity pertaining to the
[» Server Discovery and Monitoring Specification](https://github.com/mongodb/specifications/blob/master/source/server-discovery-and-monitoring/server-discovery-and-monitoring.md).
This tutorial will demonstrate command monitoring using the
[MongoDB\\Driver\\Monitoring\\CommandSubscriber](https://www.php.net/manual/en/class.mongodb-driver-monitoring-commandsubscriber.php) interface.


The [MongoDB\\Driver\\Monitoring\\CommandSubscriber](https://www.php.net/manual/en/class.mongodb-driver-monitoring-commandsubscriber.php)
interface defines three methods: `commandStarted`,
`commandSucceeded`, and `commandFailed`.
Each of these three methods accept a single `event`
argument of a specific class for the respective event. For example, the
`commandSucceeded`'s `$event` argument
is a [MongoDB\\Driver\\Monitoring\\CommandSucceededEvent](https://www.php.net/manual/en/class.mongodb-driver-monitoring-commandsucceededevent.php)
object.


In this tutorial we will implement a subscriber that creates a list of all
the query profiles and the average time they took.


## Subscriber Class Scaffolding

We start with the framework for our subscriber:


`<?php
class QueryTimeCollector implements \MongoDB\Driver\Monitoring\CommandSubscriber
{
    public function commandStarted( \MongoDB\Driver\Monitoring\CommandStartedEvent $event ): void
    {
    }
    public function commandSucceeded( \MongoDB\Driver\Monitoring\CommandSucceededEvent $event ): void
    {
    }
    public function commandFailed( \MongoDB\Driver\Monitoring\CommandFailedEvent $event ): void
    {
    }
}
?>`

## Registering the Subscriber

Once a subscriber object is instantiated, it needs to be registered with the
extensions's monitoring system. This is done by calling
[MongoDB\\Driver\\Monitoring\\addSubscriber()](https://www.php.net/manual/en/function.mongodb.driver.monitoring.addsubscriber.php) or
[MongoDB\\Driver\\Manager::addSubscriber()](https://www.php.net/manual/en/mongodb-driver-manager.addsubscriber.php) to register
the subscriber globally or with a specific Manager, respectively.


`<?php
\MongoDB\Driver\Monitoring\addSubscriber( new QueryTimeCollector() );
?>`

## Implementing the Logic

With the object registered, the only thing left is to implement the logic
in the subscriber class. To correlate the two events that make up a
successfully executed command (commandStarted and commandSucceeded), each
event object exposes a `requestId` field.


To record the average time per query shape, we will start by checking for a
`find` command in the commandStarted event. We will then add
an item to the `pendingCommands` property indexed by its
`requestId` and with its value representing the query shape.


If we receive a corresponding commandSucceeded event with the same
`requestId`, we add the duration of the event (from
`durationMicros`) to the total time and increment the
operation count.


If a corresponding commandFailed event is encountered, we just remove the
entry from the `pendingCommands` property.


`<?php
class QueryTimeCollector implements \MongoDB\Driver\Monitoring\CommandSubscriber
{
    private $pendingCommands = [];
    private $queryShapeStats = [];
    /* Creates a query shape out of the filter argument. Right now it only
     * takes the top level fields into account */
    private function createQueryShape( array $filter )
    {
        return json_encode( array_keys( $filter ) );
    }
    public function commandStarted( \MongoDB\Driver\Monitoring\CommandStartedEvent $event ): void
    {
        if ( 'find' === $event->getCommandName() )
        {
            $queryShape = $this->createQueryShape( (array) $event->getCommand()->filter );
            $this->pendingCommands[$event->getRequestId()] = $queryShape;
        }
    }
    public function commandSucceeded( \MongoDB\Driver\Monitoring\CommandSucceededEvent $event ): void
    {
        $requestId = $event->getRequestId();
        if ( array_key_exists( $requestId, $this->pendingCommands ) )
        {
            $this->queryShapeStats[$this->pendingCommands[$requestId]]['count']++;
            $this->queryShapeStats[$this->pendingCommands[$requestId]]['duration'] += $event->getDurationMicros();
            unset( $this->pendingCommands[$requestId] );
        }
    }
    public function commandFailed( \MongoDB\Driver\Monitoring\CommandFailedEvent $event ): void
    {
        if ( array_key_exists( $event->getRequestId(), $this->pendingCommands ) )
        {
            unset( $this->pendingCommands[$event->getRequestId()] );
        }
    }
    public function __destruct()
    {
        foreach( $this->queryShapeStats as $shape => $stats )
        {
            echo "Shape: ", $shape, " (", $stats['count'], ")\n  ",
                $stats['duration'] / $stats['count'], "µs\n\n";
        }
    }
}
$m = new \MongoDB\Driver\Manager( 'mongodb://localhost:27016' );
/* Add the subscriber */
\MongoDB\Driver\Monitoring\addSubscriber( new QueryTimeCollector() );
/* Do a bunch of queries */
$query = new \MongoDB\Driver\Query( [\
    'region_slug' => 'scotland-highlands', 'age' => [ '$gte' => 20 ]\
] );
$cursor = $m->executeQuery( 'dramio.whisky', $query );
$query = new \MongoDB\Driver\Query( [\
    'region_slug' => 'scotland-lowlands', 'age' => [ '$gte' => 15 ]\
] );
$cursor = $m->executeQuery( 'dramio.whisky', $query );
$query = new \MongoDB\Driver\Query( [ 'region_slug' => 'scotland-lowlands' ] );
$cursor = $m->executeQuery( 'dramio.whisky', $query );
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mongodb/tutorial/apm.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmongodb.tutorial.apm%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mongodb.tutorial.apm&repo=en&redirect=https://www.php.net/manual/en/mongodb.tutorial.apm.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google