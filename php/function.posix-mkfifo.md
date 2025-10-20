---
url: https://www.php.net/manual/en/function.posix-mkfifo.php
scraped_at: 2025-10-20T02:59:14.379Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# posix\_mkfifo

(PHP 4, PHP 5, PHP 7, PHP 8)

posix\_mkfifo — Create a fifo special file (a named pipe)

### Description [¶](https://www.php.net/manual/en/function.posix-mkfifo.php\#refsect1-function.posix-mkfifo-description)

**posix\_mkfifo**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$permissions`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**posix\_mkfifo()** creates a special
`FIFO` file which exists in the file system and acts as
a bidirectional communication endpoint for processes.


### Parameters [¶](https://www.php.net/manual/en/function.posix-mkfifo.php\#refsect1-function.posix-mkfifo-parameters)

`filename`

Path to the `FIFO` file.


`permissions`

The second parameter `permissions` has to be given in
octal notation (e.g. 0644). The permission of the newly created
`FIFO` also depends on the setting of the current
[umask()](https://www.php.net/manual/en/function.umask.php). The permissions of the created file are
(mode & ~umask).


### Return Values [¶](https://www.php.net/manual/en/function.posix-mkfifo.php\#refsect1-function.posix-mkfifo-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/posix/functions/posix-mkfifo.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.posix-mkfifo%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.posix-mkfifo&repo=en&redirect=https://www.php.net/manual/en/function.posix-mkfifo.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=89642&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89642&page=function.posix-mkfifo&vote=down "Vote down!")

8


[**_tim_**](https://www.php.net/manual/en/function.posix-mkfifo.php#89642) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#89642)

**16 years ago**

`For non-blocking, fopen'd read access to a "half-connected" pipe (created with /usr/bin/mkfifo, posix_mkfifo, etc.), I just go ahead and do:
<?php
$fh=fopen($fifo, "r+"); // ensures at least one writer (us) so will be non-blocking
stream_set_blocking($fh, false); // prevent fread / fwrite blocking
?>
The "r+" allows fopen to return immediately regardless of external  writer channel.  You then have to use your own conventions to track $fh as a pseudo-read-only resource, since fwrite would technically be permitted as well.  I've successfully used this approach on Linux with PHP 4.3.10 and PHP 5.2.4 with both half-connected (no writer yet) and pre-connected (writer already waiting) pipes, polling with stream_select as usual.`

[up](https://www.php.net/manual/vote-note.php?id=82326&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82326&page=function.posix-mkfifo&vote=down "Vote down!")

0


[**_TorokAlpar at Gmail dot com_**](https://www.php.net/manual/en/function.posix-mkfifo.php#82326) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#82326)

**17 years ago**

`Here is a possible solution to what  - tech at kwur dot com- mentioned:
I faced the problem where i had a process (a server) that needed to take care of socket connection, and in the meanwhile get some data from the database. I didn't wanted to make the clients wait for the query execution time, so i decided to make a separate process that executes the query on the DB, and the two would communicate over a pipe. Of course i didn't wanted the server blocking if no data was available. So what i come up with is to use stream_select() , and to overcome the mentioned problem, i would fork the process, open up the pipe for writing in the child, this way the parent won't block when it opens the pipe.
here is some code
<code>
<?php
if (pcntl_fork() == 0)
{
    // kid
    $file = fopen("JobsQueue","w");
    sleep(1);
    exit(0);
}
else
{
    usleep(15); // make sure that the child executes first
    $file = fopen("JobsQueue","r");
}
echo "opened the queue \n";

while (true)
{
     $reders = array($file);
     if (stream_select($reders,$writers=null,$except=null,0,15) < 1)
     {
         continue;
     }
     else
     {
         // read data from the fifo
         $data = fread($file,1024);
         echo $data;
     }
     sleep(1);
}
?>
</code>`

[up](https://www.php.net/manual/vote-note.php?id=77137&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77137&page=function.posix-mkfifo&vote=down "Vote down!")

0


[**_Enric Jaen_**](https://www.php.net/manual/en/function.posix-mkfifo.php#77137) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#77137)

**18 years ago**

`A way to have a non-blocking pipe reader is to check first if the pipe exists. If so, then read from the pipe, otherwise do other stuff. This will work assuming that the writer creates the pipe, writes on it, and after that deletes the pipe.
This is a blocking writer:
<?php
$pipe="/tmp/pipe";
$mode=0600;
if(!file_exists($pipe)) {
      // create the pipe
      umask(0);
      posix_mkfifo($pipe,$mode);
}
$f = fopen($pipe,"w");
fwrite($f,"hello");  //block until there is a reader
unlink($pipe); //delete pipe
?>
And this is the non-blocking reader:
<?php
$pipe="/tmp/pipe";
if(!file_exists($pipe)) {
      echo "I am not blocked!";
}
else {
      //block and read from the pipe
      $f = fopen($pipe,"r");
      echo fread($f,10);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=77928&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77928&page=function.posix-mkfifo&vote=down "Vote down!")

 -1


[**_tech at kwur dot com_**](https://www.php.net/manual/en/function.posix-mkfifo.php#77928) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#77928)

**18 years ago**

`This is still not a solution: if I listen to commands on a pipe and output status on a separate pipe, PHP will block on both opens because something else has not already connected to this pipe.  Because I can't do a low-level fcntl() to to set O_NONBLOCK or something like it, this always locks up and is really stupid.  The only way I can get it to work is to spawn seperate subshells with system() and have them cat, or echo respectively and then the pipes work properly...usually?  Its alot of trouble that we can't set the blocking on the open!!`

[up](https://www.php.net/manual/vote-note.php?id=75230&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75230&page=function.posix-mkfifo&vote=down "Vote down!")

 -1


[**_Uther Pendragon_**](https://www.php.net/manual/en/function.posix-mkfifo.php#75230) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#75230)

**18 years ago**

``Note (quoted from `man 7 pipe` on debian linux):
"On some systems (but not Linux), pipes are bidirectional:  data  can  be  transmitted  in  both directions  between  the pipe ends.  According to POSIX.1-2001, pipes only need to be unidirectional.  Portable applications should avoid reliance on bidirectional pipe semantics."
Linux pipes are NOT bidirectional.
Also, it appears to me that the use of fifo (named) pipes in php is pretty pointless as there appears to be NO way of determining whether opening (let alone reading) from it will block.  stream_select SHOULD be able to accomplish this, unfortunatly you cannot get to this point because even trying to OPEN a pipe for read will block until there is a writer.
I even tried to use popen("cat $name_of_pipe", 'r'), and even it blocked until it was opened for write by another process.``

[up](https://www.php.net/manual/vote-note.php?id=95385&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95385&page=function.posix-mkfifo&vote=down "Vote down!")

 -2


[**_Mauro Titimoli_**](https://www.php.net/manual/en/function.posix-mkfifo.php#95385) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#95385)

**15 years ago**

`Object Oriented FIFO Communication process:
<?php
interface Communication {
    public function receive($bytes = 1024);
    public function getData();
    public function clearData();
    public function send($data);
}
class FIFOCommunication implements Communication {
    private $fifos;
    private $data;
    static public function stream_fifo_open($fifoPath, $mode) {
        if (pcntl_fork() == 0) {
            if (! file_exists($fifoPath)) {
                posix_mkfifo($fifoPath, $mode);
            }
            $fifo = fopen($fifoPath, 'w');
            sleep(1);
            exit(0);
        }
        else {
            usleep(15);
            return fopen($fifoPath, 'r');
        }
    }
    static public function stream_fifo_write($fifoPath, $mode, $data) {
        if (pcntl_fork() == 0) {
            if (! file_exists($fifoPath)) {
                posix_mkfifo($fifoPath, $mode);
            }
            $fifo = fopen($fifoPath, 'w');
            fwrite($fifo, $data);
            exit(0);
        }
    }
    public function __construct(
        $fifoInputName, $fifoInputMode,
        $fifoOutputName, $fifoOutputMode
    ) {
        $this->fifos = array(
            'input' => array(
                'file' => self::stream_fifo_open($fifoInputName, $fifoInputMode),
                'mode' => $fifoInputMode,
                'name' => $fifoInputName,
                'use' => 'r',
            ),
            'output' => array(
                'mode' => $fifoOutputMode,
                'name' => $fifoOutputName,
                'use' => 'w'
            )
        );
    }
    public function remove($type = null) {
        switch ($type) {
            case 'input':
                @unlink($this->fifos['input']['name']);
                break;
            case 'output':
                @unlink($this->fifos['output']['name']);
                break;
            default:
                @unlink($this->fifos['input']['name']);
                @unlink($this->fifos['output']['name']);
        }
    }
    public function receive($bytes = 1024) {
        $readers = array($this->fifos['input']['file']);
        if (stream_select($readers, $writers = null, $except = null, 0, 15) == 1) {
            $data = fread($this->fifos['input']['file'], $bytes);
        }
        if (! empty($data)) {
            $this->data .= $data;
            return true;
        }
        else {
            return false;
        }
    }
    public function getData() {
        return $this->data;
    }
    public function clearData() {
        $this->data = null;
    }
    public function send($data) {
        $fifoOutput = & $this->fifos['output'];
        self::stream_fifo_write($fifoOutput['name'], $fifoOutput['mode'], $data);
    }
}
$fifoCommunication = new FIFOCommunication(
    getmypid() . '.input', 0600,
    getmypid() . '.output', 0600
);
echo "COMMUNICATION STARTED\n";
while (true) {
    if ($fifoCommunication->receive()) {
        $data = $fifoCommunication->getData();
        if ($data == "EXIT\n") {
            break;
        }
        else {
            $fifoCommunication->send('RECEIVED: ' . $fifoCommunication->getData());
        }
    }
    sleep(1);
}
$fifoComunication->remove();
?>`

[up](https://www.php.net/manual/vote-note.php?id=86345&page=function.posix-mkfifo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86345&page=function.posix-mkfifo&vote=down "Vote down!")

 -1


[**_mike at easystyle dot org_**](https://www.php.net/manual/en/function.posix-mkfifo.php#86345) [¶](https://www.php.net/manual/en/function.posix-mkfifo.php#86345)

**17 years ago**

`Couldn't you just open up a writer yourself right after you open up a reader?  Just to be sure that you won't have any blocking issues...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.posix-mkfifo&repo=en&redirect=https://www.php.net/manual/en/function.posix-mkfifo.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google