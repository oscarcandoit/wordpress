---
url: https://www.php.net/manual/en/function.msg-send.php
scraped_at: 2025-10-20T02:54:24.023Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# msg\_send

(PHP 4 >= 4.3.0, PHP 5, PHP 7, PHP 8)

msg\_send — Send a message to a message queue

### Description [¶](https://www.php.net/manual/en/function.msg-send.php\#refsect1-function.msg-send-description)

**msg\_send**(

[SysvMessageQueue](https://www.php.net/manual/en/class.sysvmessagequeue.php) `$queue`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$message_type`,

[string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php) `$message`,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$serialize` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$blocking` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**,

[int](https://www.php.net/manual/en/language.types.integer.php) `&$error_code` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**msg\_send()** sends a `message` of type
`message_type` (which MUST be greater than 0) to
the message queue specified by `queue`.


### Parameters [¶](https://www.php.net/manual/en/function.msg-send.php\#refsect1-function.msg-send-parameters)

`queue`

The message queue.


`message_type`

The type of the message (MUST be greater than 0)


`message`

The body of the message.


> **Note**:
>
>
> If `serialize` set to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is supplied,
> MUST be of type: [string](https://www.php.net/manual/en/language.types.string.php), [int](https://www.php.net/manual/en/language.types.integer.php), [float](https://www.php.net/manual/en/language.types.float.php)
> or [bool](https://www.php.net/manual/en/language.types.boolean.php). In other case a warning will be issued.

`serialize`

The optional `serialize` controls how the
`message` is sent. `serialize`
defaults to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** which means that the `message` is
serialized using the same mechanism as the session module before being
sent to the queue. This allows complex arrays and objects to be sent to
other PHP scripts, or if you are using the WDDX serializer, to any WDDX
compatible client.


`blocking`

If the message is too large to fit in the queue, your script will wait
until another process reads messages from the queue and frees enough
space for your message to be sent.
This is called blocking; you can prevent blocking by setting the
optional `blocking` parameter to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, in which
case **msg\_send()** will immediately return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the
message is too big for the queue, and set the optional
`error_code` to **`[MSG\_EAGAIN](https://www.php.net/manual/en/sem.constants.php#constant.msg-eagain)`**,
indicating that you should try to send your message again a little
later on.


`error_code`

If the function fails, the optional errorcode will be set to the value of the system errno variable.


### Return Values [¶](https://www.php.net/manual/en/function.msg-send.php\#refsect1-function.msg-send-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


Upon successful completion the message queue data structure is updated as
follows: `msg_lspid` is set to the process-ID of the
calling process, `msg_qnum` is incremented by 1 and
`msg_stime` is set to the current time.


### Changelog [¶](https://www.php.net/manual/en/function.msg-send.php\#refsect1-function.msg-send-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `queue` expects a [SysvMessageQueue](https://www.php.net/manual/en/class.sysvmessagequeue.php)<br> instance now; previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### See Also [¶](https://www.php.net/manual/en/function.msg-send.php\#refsect1-function.msg-send-seealso)

- [msg\_remove\_queue()](https://www.php.net/manual/en/function.msg-remove-queue.php) \- Destroy a message queue
- [msg\_receive()](https://www.php.net/manual/en/function.msg-receive.php) \- Receive a message from a message queue
- [msg\_stat\_queue()](https://www.php.net/manual/en/function.msg-stat-queue.php) \- Returns information from the message queue data structure
- [msg\_set\_queue()](https://www.php.net/manual/en/function.msg-set-queue.php) \- Set information in the message queue data structure

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sem/functions/msg-send.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.msg-send%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.msg-send&repo=en&redirect=https://www.php.net/manual/en/function.msg-send.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=114831&page=function.msg-send&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114831&page=function.msg-send&vote=down "Vote down!")

5


[**_qeekin at gmail dot com_**](https://www.php.net/manual/en/function.msg-send.php#114831) [¶](https://www.php.net/manual/en/function.msg-send.php#114831)

**11 years ago**

`I created example how to comunnicate with programe written in C throught messages queues. First run C program (it will create queue) then PHP script.
C code compile with: gcc -std=c99 -o test_queue test_queue.c
test_queue.c:
/**
* Example how to use System V Messages Queues with PHP and C program.
* This is simple server which create message queue and receive message from it.
* Based on Beej's Guide to Unix IPC
* Autor: Jan Drazil, <qeekin at gmail dot com>
*/
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>
#include <string.h>
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/msg.h>
/* Buffer struct for receiving messages */
struct php_buf {
    long mtype;
    char msg[200];
};
int main(void)
{
    struct php_buf buf;
    int msqid;
    key_t key;
    /* Generate key (/var/www/index.php must be accessible file) */
    if((key = ftok("/var/www/index.php", 'G')) == -1) {
        perror("ftok");
        exit(EXIT_FAILURE);
    }
    /* Create message queue */
    if((msqid = msgget(key, 0666 | IPC_CREAT)) == -1) {
        perror("msgget");
        exit(EXIT_FAILURE);
    }
    printf("Ready to get string from PHP!\n");
    /* Receive message */
    if(msgrcv(msqid, &buf, sizeof(buf.msg)-1, 0, 0) == -1) {
        perror("msgrcv");
        exit(EXIT_FAILURE);
    }
    /* Eliminate segmentation fault */
    buf.msg[199] = '\0';
    printf("Recieved from PHP: %s\n", buf.msg);
    /* Destroy message queue */
    if(msgctl(msqid, IPC_RMID, NULL) == -1) {
        perror("msgctl");
        exit(EXIT_FAILURE);
    }
    return EXIT_SUCCESS;
}
test_queue.php:
<?php
/**
* Example how to use System V Messages Queues with PHP and C program.
* This is simple server which create message queue and receive message from it.
* Based on Beej's Guide to Unix IPC
* Autor: Jan Drazil, <qeekin at gmail dot com>
*/
/* Generate key, param fot ftok must be same as in test_msg.c */
if(($key = ftok("/var/www/index.php", "G")) == -1)
    die("ftok");
if(!msg_queue_exists($key))
    die("message queue doesn't exists");
/* Connect to message queue */
if(($msqid = msg_get_queue($key)) === FALSE)
    die("msg_get_queue");
echo "Sending text to msg queue.\n";
/* Send message to C program */
if(!msg_send($msqid, 12, "Hello from PHP!\0", false))
    die("msg_send");
echo "Done"
?>`

[up](https://www.php.net/manual/vote-note.php?id=110634&page=function.msg-send&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110634&page=function.msg-send&vote=down "Vote down!")

4


[**_Muffinman_**](https://www.php.net/manual/en/function.msg-send.php#110634) [¶](https://www.php.net/manual/en/function.msg-send.php#110634)

**12 years ago**

`When sending non-complex (serialize = false) messages to a program in C, you need to add the null character to the string (\0). Otherwise the previous message will be partially visible if it is longer than the current message. Took some kind help from comp.lang.php for me to figure that out. While it seems so obvious now, I thought I'd share it here.`

[up](https://www.php.net/manual/vote-note.php?id=94101&page=function.msg-send&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94101&page=function.msg-send&vote=down "Vote down!")

3


[**_michael dot NO dot SP dot AM dot cordover+php at gmail dot com_**](https://www.php.net/manual/en/function.msg-send.php#94101) [¶](https://www.php.net/manual/en/function.msg-send.php#94101)

**16 years ago**

`After about an hour of debugging I've discovered the meaning of the undocumented "PHP Warning: msg_send(): msgsnd failed: Invalid argument" ($errorcode = 13).
This occurred when the size of $message was larger than msg_qbytes (see msg_stat_queue() for how to determine and change msg_qbytes).`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.msg-send&repo=en&redirect=https://www.php.net/manual/en/function.msg-send.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google