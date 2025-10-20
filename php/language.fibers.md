---
url: https://www.php.net/manual/en/language.fibers.php
scraped_at: 2025-10-20T02:30:56.416Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Fibers [¶](https://www.php.net/manual/en/language.fibers.php\#language.fibers)

### Fibers overview [¶](https://www.php.net/manual/en/language.fibers.php\#language.fibers.overview)

(PHP 8 >= 8.1.0)

Fibers represent full-stack, interruptible functions. Fibers may be suspended from anywhere in the call-stack,
pausing execution within the fiber until the fiber is resumed at a later time.


Fibers pause the entire execution stack, so the direct caller of the function does not need to change how it
invokes the function.


Execution may be interrupted anywhere in the call stack using [Fiber::suspend()](https://www.php.net/manual/en/fiber.suspend.php)
(that is, the call to [Fiber::suspend()](https://www.php.net/manual/en/fiber.suspend.php) may be in a deeply nested function or not
even exist at all).


Unlike stack-less [Generator](https://www.php.net/manual/en/class.generator.php)s, each [Fiber](https://www.php.net/manual/en/class.fiber.php) has its own call stack,
allowing them to be paused within deeply nested function calls. A function declaring an interruption point
(that is, calling [Fiber::suspend()](https://www.php.net/manual/en/fiber.suspend.php)) need not change its return type, unlike a function using
[`yield`](https://www.php.net/manual/en/language.generators.syntax.php#control-structures.yield) which must return a [Generator](https://www.php.net/manual/en/class.generator.php) instance.


Fibers can be suspended in any function call, including those called from within the PHP VM, such as functions
provided to [array\_map()](https://www.php.net/manual/en/function.array-map.php) or methods called by [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php) on an
[Iterator](https://www.php.net/manual/en/class.iterator.php) object.


Once suspended, execution of the fiber may be resumed with any value using [Fiber::resume()](https://www.php.net/manual/en/fiber.resume.php)
or by throwing an exception into the fiber using [Fiber::throw()](https://www.php.net/manual/en/fiber.throw.php). The value is returned
(or exception thrown) from [Fiber::suspend()](https://www.php.net/manual/en/fiber.suspend.php).


> **Note**:
>
> Prior to PHP 8.4.0, switching fibers during the execution of an object
> [destructor](https://www.php.net/manual/en/language.oop5.decon.php#language.oop5.decon.destructor) was not
> allowed.

**Example #1 Basic usage**

`<?php
$fiber = new Fiber(function (): void {
$value = Fiber::suspend('fiber');
echo "Value used to resume fiber: ", $value, PHP_EOL;
});
$value = $fiber->start();
echo "Value from fiber suspending: ", $value, PHP_EOL;
$fiber->resume('test');
?>`

The above example will output:

```
Value from fiber suspending: fiber
Value used to resume fiber: test

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/fibers.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.fibers%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.fibers&repo=en&redirect=https://www.php.net/manual/en/language.fibers.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=127029&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127029&page=language.fibers&vote=down "Vote down!")

99


[**_user at csa dot es_**](https://www.php.net/manual/en/language.fibers.php#127029) [¶](https://www.php.net/manual/en/language.fibers.php#127029)

**3 years ago**

`Perhaps not using the same variable name everywhere will be a good idea
<?php
$fiber = new Fiber(function (): void {
$parm = Fiber::suspend('fiber');
echo "Value used to resume fiber: ", $parm, PHP_EOL;
});
$res = $fiber->start();
echo "Value from fiber suspending: ", $res, PHP_EOL;
$fiber->resume('test');
?>`

[up](https://www.php.net/manual/vote-note.php?id=127282&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127282&page=language.fibers&vote=down "Vote down!")

44


[**_Ali Madadi_**](https://www.php.net/manual/en/language.fibers.php#127282) [¶](https://www.php.net/manual/en/language.fibers.php#127282)

**3 years ago**

`Here is a simple scheduler and thread pool that implements multithreading using fibers and tick functions in PHP 8.1 and returns the return value of each function in the pool in an array at the end.
Note that due to some bugs, you need to register a new tick function for each "thread". Remember to unregister all of them at the end.
The link bellow is the discussion on a bug that is going on right now (At the time of writing this). Note that based on the discussion, the ability to call Fiber::suspend() inside tick function may become forbidden in PHP 8.2+. But if the bug gets fixed, you can move register_tick_function() line to the top of the class, and this simple multithreading class in pure PHP code will work like a charm.
[https://github.com/php/php-src/issues/8960](https://github.com/php/php-src/issues/8960)
<?php
declare(ticks=1);
class Thread {
protected static $names = [];
protected static $fibers = [];
protected static $params = [];
public static function register(string|int $name, callable $callback, array $params)
{
    self::$names[]  = $name;
    self::$fibers[] = new Fiber($callback);
    self::$params[] = $params;
}
public static function run() {
    $output = [];
    while (self::$fibers) {
      foreach (self::$fibers as $i => $fiber) {
          try {
              if (!$fiber->isStarted()) {
                  // Register a new tick function for scheduling this fiber
                  register_tick_function('Thread::scheduler');
                  $fiber->start(...self::$params[$i]);
              } elseif ($fiber->isTerminated()) {
                  $output[self::$names[$i]] = $fiber->getReturn();
                  unset(self::$fibers[$i]);
              } elseif ($fiber->isSuspended()) {
                $fiber->resume();
              }
          } catch (Throwable $e) {
              $output[self::$names[$i]] = $e;
          }
      }
    }
    return $output;
}
public static function scheduler () {
    if(Fiber::getCurrent() === null) {
      return;
    }
    // running Fiber::suspend() in this if condition will prevent an infinite loop!
    if(count(self::$fibers) > 1)
    {
      Fiber::suspend();
    }
}
}
?>
And here is an example code on how to use above Thread class:
<?php
// defining a non-blocking thread, so multiple calls will run in concurrent mode using above Thread class.
function thread (string $print, int $loop)
{
$i = $loop;
while ($i--){
    echo $print;
}
return "Thread '{$print}' finished after printing '{$print}' for {$loop} times!";
}
// registering 6 Threads (A, B, C, D, E, and F)
foreach(range('A', 'F') as $c) {
Thread::register($c, 'thread', [$c, rand(5, 20)]);
}
// run threads and wait until execution finishes
$outputs = Thread::run();
// print outputs
echo PHP_EOL, '-------------- RETURN VALUES --------------', PHP_EOL;
print_r($outputs);
?>
The output will be something like this (but probably different):
ABCDEFABCDEFABCDEFABCDEFABCDEFABCEFABFABFABEBEFBEFEFEFAABEABEBEFBEFFAAAAAA
-------------- RETURN VALUES --------------
Array
(
    [D] => Thread 'D' finished after printing 'D' for 5 times!
    [C] => Thread 'C' finished after printing 'C' for 6 times!
    [E] => Thread 'E' finished after printing 'E' for 15 times!
    [B] => Thread 'B' finished after printing 'B' for 15 times!
    [F] => Thread 'F' finished after printing 'F' for 15 times!
    [A] => Thread 'A' finished after printing 'A' for 18 times!
)`

[up](https://www.php.net/manual/vote-note.php?id=129688&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129688&page=language.fibers&vote=down "Vote down!")

5


[**_nikiDOTamministratoreATgmail at no dot spam_**](https://www.php.net/manual/en/language.fibers.php#129688) [¶](https://www.php.net/manual/en/language.fibers.php#129688)

**1 year ago**

`TL;DR
The Thread class from Ali Madabi above has been eventually deprecated by the linked issue as relaying on tick functions for preemptive multi-threading simulation has been deemed "bad practice". Better ways were suggested for achieving some sort of multi-threading, such as: Revolt and AMP.
[https://github.com/php/php-src/issues/8960#issuecomment-1184249445](https://github.com/php/php-src/issues/8960#issuecomment-1184249445)`

[up](https://www.php.net/manual/vote-note.php?id=127846&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127846&page=language.fibers&vote=down "Vote down!")

12


[**_nesk at xakep dot ru_**](https://www.php.net/manual/en/language.fibers.php#127846) [¶](https://www.php.net/manual/en/language.fibers.php#127846)

**2 years ago**

`I think that in some cases it makes sense to convert a Fiber to a Generator (Coroutine) for convenience. In such cases, this code will be useful:
<?php
function fiber_to_coroutine(\Fiber $fiber): \Generator
{
    $index = -1; // Note: Pre-increment is faster than post-increment.
    $value = null;
    // Allow an already running fiber.
    if (!$fiber->isStarted()) {
        $value = yield ++$index => $fiber->start();
    }
    // A Fiber without suspends should return the result immediately.
    if (!$fiber->isTerminated()) {
        while (true) {
            $value = $fiber->resume($value);
            // The last call to "resume()" moves the execution of the
            // Fiber to the "return" stmt.
            //
            // So the "yield" is not needed. Skip this step and return
            // the result.
            if ($fiber->isTerminated()) {
                break;
            }
            $value = yield ++$index => $value;
        }
    }
    return $fiber->getReturn();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=127125&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127125&page=language.fibers&vote=down "Vote down!")

20


[**_maxpanchnko at gmail dot com_**](https://www.php.net/manual/en/language.fibers.php#127125) [¶](https://www.php.net/manual/en/language.fibers.php#127125)

**3 years ago**

`One of examples, how to make multi_curl faster twice (pseudocode) using Fibers:
<?php
$curlHandles = [];
$urls = [\
    ' [https://example.com/1](https://example.com/1)',\
    ' [https://example.com/2](https://example.com/2)',\
    ...\
    ' [https://example.com/1000](https://example.com/1000)',\
];
$mh = curl_multi_init();
$mh_fiber = curl_multi_init();
$halfOfList = floor(count($urls) / 2);
foreach ($urls as $index => $url) {
    $ch = curl_init($url);
    $curlHandles[] = $ch;
    // half of urls will be run in background in fiber
    $index > $halfOfList ? curl_multi_add_handle($mh_fiber, $ch) : curl_multi_add_handle($mh, $ch);
}
$fiber = new Fiber(function (CurlMultiHandle $mh) {
    $still_running = null;
    do {
        curl_multi_exec($mh, $still_running);
        Fiber::suspend();
    } while ($still_running);
});
// run curl multi exec in background while fiber is in suspend status
$fiber->start($mh_fiber);
$still_running = null;
do {
    $status = curl_multi_exec($mh, $still_running);
} while ($still_running);
do {
    /**
     * at this moment curl in fiber already finished (maybe)
     * so we must refresh $still_running variable with one more cycle "do while" in fiber
     **/
    $status_fiber = $fiber->resume();
} while (!$fiber->isTerminated());
foreach ($curlHandles as $index => $ch) {
    $index > $halfOfList ? curl_multi_remove_handle($mh_fiber, $ch) : curl_multi_remove_handle($mh, $ch);
}
curl_multi_close($mh);
curl_multi_close($mh_fiber);
?>`

[up](https://www.php.net/manual/vote-note.php?id=127383&page=language.fibers&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127383&page=language.fibers&vote=down "Vote down!")

5


[**_newuser_**](https://www.php.net/manual/en/language.fibers.php#127383) [¶](https://www.php.net/manual/en/language.fibers.php#127383)

**3 years ago**

`Example of the same functionality showing what is the difference between Fiber and Generator
<?php
$gener = (function () use (&$gener): Generator {
    $userfunc = function () use (&$gener) : Generator {
        register_shutdown_function(function () use (&$gener) {
            $gener->send('test');
        });
        return yield 'test';
    };
    $parm = yield from $userfunc();
    echo "Value used to resume fiber: ", $parm, PHP_EOL;
})();
$res = $gener->current();
echo "Value from fiber suspending: ", $res, PHP_EOL;
?>
<?php
$fiber = new Fiber(function () use (&$fiber) : void {
    $userfunc = function () use (&$fiber) : string {
        register_shutdown_function(function () use (&$fiber) {
            $fiber->resume('test');
        });
        return Fiber::suspend('fiber');
    };
    $parm = $userfunc();
    echo "Value used to resume fiber: ", $parm, PHP_EOL;
});
$res = $fiber->start();
echo "Value from fiber suspending: ", $res, PHP_EOL;
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.fibers&repo=en&redirect=https://www.php.net/manual/en/language.fibers.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google