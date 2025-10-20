---
url: https://www.php.net/manual/en/features.file-upload.php
scraped_at: 2025-10-20T02:33:21.487Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Handling file uploads [¶](https://www.php.net/manual/en/features.file-upload.php\#features.file-upload)

## Table of Contents [¶](https://www.php.net/manual/en/features.file-upload.php\#features.file-upload)

- [POST method uploads](https://www.php.net/manual/en/features.file-upload.post-method.php)
- [Error Messages Explained](https://www.php.net/manual/en/features.file-upload.errors.php)
- [Common Pitfalls](https://www.php.net/manual/en/features.file-upload.common-pitfalls.php)
- [Uploading multiple files](https://www.php.net/manual/en/features.file-upload.multiple.php)
- [PUT method support](https://www.php.net/manual/en/features.file-upload.put-method.php)
- [See Also](https://www.php.net/manual/en/features.file-upload.errors.seealso.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/file-upload.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.file-upload%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.file-upload&repo=en&redirect=https://www.php.net/manual/en/features.file-upload.php)

### User Contributed Notes 29 notes

[up](https://www.php.net/manual/vote-note.php?id=114004&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114004&page=features.file-upload&vote=down "Vote down!")

373


[**_CertaiN_**](https://www.php.net/manual/en/features.file-upload.php#114004) [¶](https://www.php.net/manual/en/features.file-upload.php#114004)

**11 years ago**

`You'd better check $_FILES structure and values throughly.
The following code cannot cause any errors absolutely.
Example:
<?php
header('Content-Type: text/plain; charset=utf-8');
try {

    // Undefined | Multiple Files | $_FILES Corruption Attack
    // If this request falls under any of them, treat it invalid.
    if (
        !isset($_FILES['upfile']['error']) ||
        is_array($_FILES['upfile']['error'])
    ) {
        throw new RuntimeException('Invalid parameters.');
    }
    // Check $_FILES['upfile']['error'] value.
    switch ($_FILES['upfile']['error']) {
        case UPLOAD_ERR_OK:
            break;
        case UPLOAD_ERR_NO_FILE:
            throw new RuntimeException('No file sent.');
        case UPLOAD_ERR_INI_SIZE:
        case UPLOAD_ERR_FORM_SIZE:
            throw new RuntimeException('Exceeded filesize limit.');
        default:
            throw new RuntimeException('Unknown errors.');
    }
    // You should also check filesize here.
    if ($_FILES['upfile']['size'] > 1000000) {
        throw new RuntimeException('Exceeded filesize limit.');
    }
    // DO NOT TRUST $_FILES['upfile']['mime'] VALUE !!
    // Check MIME Type by yourself.
    $finfo = new finfo(FILEINFO_MIME_TYPE);
    if (false === $ext = array_search(
        $finfo->file($_FILES['upfile']['tmp_name']),
        array(
            'jpg' => 'image/jpeg',
            'png' => 'image/png',
            'gif' => 'image/gif',
        ),
        true
    )) {
        throw new RuntimeException('Invalid file format.');
    }
    // You should name it uniquely.
    // DO NOT USE $_FILES['upfile']['name'] WITHOUT ANY VALIDATION !!
    // On this example, obtain safe unique name from its binary data.
    if (!move_uploaded_file(
        $_FILES['upfile']['tmp_name'],
        sprintf('./uploads/%s.%s',
            sha1_file($_FILES['upfile']['tmp_name']),
            $ext
        )
    )) {
        throw new RuntimeException('Failed to move uploaded file.');
    }
    echo 'File is uploaded successfully.';
} catch (RuntimeException $e) {
    echo $e->getMessage();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=111489&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111489&page=features.file-upload&vote=down "Vote down!")

20


[**_jan at lanteraudio dot nl_**](https://www.php.net/manual/en/features.file-upload.php#111489) [¶](https://www.php.net/manual/en/features.file-upload.php#111489)

**12 years ago**

`Also stumbled on the max_file_size problem, in particular getting no response, no error whatsoever when uploading a file bigger than the set upload_max_filesize.
I found that it's not the upload_max_filesize setting, but instead the post_max_size setting causing this no response issue. So if you set post_max_size way larger than upload_max_filesize, at least you are likely to get an error response when filesize exceeds upload_max_filesize but is still within the limits of post_max_size.
Hope this helps anyone.`

[up](https://www.php.net/manual/vote-note.php?id=39796&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39796&page=features.file-upload&vote=down "Vote down!")

17


[**_~caetin~ ( at ) ~hotpop~ ( dot ) ~com~_**](https://www.php.net/manual/en/features.file-upload.php#39796) [¶](https://www.php.net/manual/en/features.file-upload.php#39796)

**21 years ago**

`From the manual:
     If no file is selected for upload in your form, PHP will return $_FILES['userfile']['size'] as 0, and $_FILES['userfile']['tmp_name'] as none.
As of PHP 4.2.0, the "none" is no longer a reliable determinant of no file uploaded. It's documented if you click on the "error codes" link, but you need to look at the $_FILES['your_file']['error']. If it's 4, then no file was selected.`

[up](https://www.php.net/manual/vote-note.php?id=41615&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41615&page=features.file-upload&vote=down "Vote down!")

19


[**_steve dot criddle at crd-sector dot com_**](https://www.php.net/manual/en/features.file-upload.php#41615) [¶](https://www.php.net/manual/en/features.file-upload.php#41615)

**21 years ago**

`IE on the Mac is a bit troublesome.  If you are uploading a file with an unknown file suffix, IE uploads the file with a mime type of "application/x-macbinary".  The resulting file includes the resource fork wrapped around the file.  Not terribly useful.
The following code assumes that the mime type is in $type, and that you have loaded the file's contents into $content.  If the file is in MacBinary format, it delves into the resource fork header, gets the length of the data fork (bytes 83-86) and uses that to get rid of the resource fork.
(There is probably a better way to do it, but this solved my problem):
<?php
if ($type == 'application/x-macbinary') {
    if (strlen($content) < 128) die('File too small');
    $length = 0;
    for ($i=83; $i<=86; $i++) {
        $length = ($length * 256) + ord(substr($content,$i,1));
          }
    $content = substr($content,128,$length);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=52989&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52989&page=features.file-upload&vote=down "Vote down!")

23


[**_ceo at l-i-e dot com_**](https://www.php.net/manual/en/features.file-upload.php#52989) [¶](https://www.php.net/manual/en/features.file-upload.php#52989)

**20 years ago**

`Using /var/www/uploads in the example code is just criminal, imnsho.
One should *NOT* upload untrusted files into your web tree, on any server.
Nor should any directory within your web tree have permissions sufficient for an upload to succeed, on a shared server. Any other user on that shared server could write a PHP script to dump anything they want in there!
The $_FILES['userfile']['type'] is essentially USELESS.
A. Browsers aren't consistent in their mime-types, so you'll never catch all the possible combinations of types for any given file format.
B. It can be forged, so it's crappy security anyway.
One's code should INSPECT the actual file to see if it looks kosher.
For example, images can quickly and easily be run through imagegetsize and you at least know the first N bytes LOOK like an image.  That doesn't guarantee it's a valid image, but it makes it much less likely to be a workable security breaching file.
For Un*x based servers, one could use exec and 'file' command to see if the Operating System thinks the internal contents seem consistent with the data type you expect.
I've had trouble in the past with reading the '/tmp' file in a file upload.  It would be nice if PHP let me read that file BEFORE I tried to move_uploaded_file on it, but PHP won't, presumably under the assumption that I'd be doing something dangerous to read an untrusted file.  Fine.   One should move the uploaded file to some staging directory.  Then you check out its contents as thoroughly as you can.  THEN, if it seems kosher, move it into a directory outside your web tree.  Any access to that file should be through a PHP script which reads the file.  Putting it into your web tree, even with all the checks you can think of, is just too dangerous, imnsho.
There are more than a few User Contributed notes here with naive (bad) advice.  Be wary.`

[up](https://www.php.net/manual/vote-note.php?id=19926&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19926&page=features.file-upload&vote=down "Vote down!")

13


[**_am at netactor dot NO\_SPAN dot com_**](https://www.php.net/manual/en/features.file-upload.php#19926) [¶](https://www.php.net/manual/en/features.file-upload.php#19926)

**23 years ago**

`Your binary files may be uploaded incorrectly if you use modules what recode characters. For example, for Russian Apache, you should use
<Files ScriptThatReceivesUploads.php>
CharsetDisable On
</Files>`

[up](https://www.php.net/manual/vote-note.php?id=107406&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107406&page=features.file-upload&vote=down "Vote down!")

19


[**_xmontero at dsitelecom dot com_**](https://www.php.net/manual/en/features.file-upload.php#107406) [¶](https://www.php.net/manual/en/features.file-upload.php#107406)

**13 years ago**

`If "large files" (ie: 50 or 100 MB) fail, check this:
It may happen that your outgoing connection to the server is slow, and it may timeout not the "execution time" but the "input time", which for example in our system defaulted to 60s. In our case a large upload could take 1 or 2 hours.
Additionally we had "session settings" that should be preserved after upload.
1) You might want review those ini entries:
* session.gc_maxlifetime
* max_input_time
* max_execution_time
* upload_max_filesize
* post_max_size
2) Still fails? Caution, not all are changeable from the script itself. ini_set() might fail to override.
More info here:
[http://www.php.net/manual/es/ini.list.php](http://www.php.net/manual/es/ini.list.php)
You can see that the "upload_max_filesize", among others, is PHP_INI_PERDIR and not PHP_INI_ALL. This invalidates to use ini_set():
[http://www.php.net/manual/en/configuration.changes.modes.php](http://www.php.net/manual/en/configuration.changes.modes.php)
Use .htaccess instead.
3) Still fails?. Just make sure you enabled ".htaccess" to overwrite your php settings. This is made in the apache file. You need at least AllowOverride Options.
See this here:
[http://www.php.net/manual/en/configuration.changes.php](http://www.php.net/manual/en/configuration.changes.php)
You will necessarily allow this manually in the case your master files come with AllowOverride None.
Conclussion:
Depending on the system, to allow "large file uploads" you must go up and up and up and touch your config necessarily up to the apache config.
Sample files:
These work for me, for 100MB uploads, lasting 2 hours:
In apache-virtual-host:
-----------------------------------------------------------
<Directory /var/www/MyProgram>
    AllowOverride Options
</Directory>
-----------------------------------------------------------
In .htaccess:
-----------------------------------------------------------
php_value session.gc_maxlifetime 10800
php_value max_input_time         10800
php_value max_execution_time     10800
php_value upload_max_filesize    110M
php_value post_max_size          120M
-----------------------------------------------------------
In the example,
- As I last 1 to 2 hours, I allow 3 hours (3600x3)
- As I need 100MB, I allow air above for the file (110M) and a bit more for the whole post (120M).`

[up](https://www.php.net/manual/vote-note.php?id=55886&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55886&page=features.file-upload&vote=down "Vote down!")

9


[**_myko AT blue needle DOT com_**](https://www.php.net/manual/en/features.file-upload.php#55886) [¶](https://www.php.net/manual/en/features.file-upload.php#55886)

**20 years ago**

`Just a quick note that there's an issue with Apache, the MAX_FILE_SIZE hidden form field, and zlib.output_compression = On.  Seems that the browser continues to post up the entire file, even though PHP throws the MAX_FILE_SIZE error properly.  Turning zlib compression to OFF seems to solve the issue.  Don't have time to dig in and see who's at fault, but wanted to save others the hassle of banging their head on this one.`

[up](https://www.php.net/manual/vote-note.php?id=70471&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70471&page=features.file-upload&vote=down "Vote down!")

13


[**_jedi\_aka at yahoo dot com_**](https://www.php.net/manual/en/features.file-upload.php#70471) [¶](https://www.php.net/manual/en/features.file-upload.php#70471)

**19 years ago**

`For those of you trying to make the upload work with IIS on windows XP/2000/XP Media and alike here is a quick todo.
1) Once you have created subdirectories "uploads/"  in the same directory wher you code is running use the code from oportocala above and to make absolutely sure sure that the file you are trying to right is written under that folder. ( I recomend printing it using echo $uploadfile; )
2) In windows explorer browse to the upload directory created above and share it. To do that execute the following substeps.
     a) Right click the folder click "sharing and security..."
     b) Check 'Share this folder on the network'
     c) Check 'Allow network users to change my files' ( THIS STEP IS VERY IMPORTANT )
     d) click 'ok' or 'apply'
3) you can then go in the IIS to set read and write permissions for it. To do that execute the followin substeps.
     a) Open IIS (Start/Controp Panel (classic View)/ Admistrative tools/Internet Information Service
     b) Browse to your folder (the one we created above)
     c) right click and select properties.
     d) in the Directory tab, make sure, READ, WRITE, AND DIRECTORY BROWSING are checked.
     e) For the security freaks out there, You should also make sure that 'execute permissions:' are set to Script only or lower (DO NOT SET IT TO 'script and executable)'( that is because someone could upload a script to your directory and run it. And, boy, you do not want that to happen).
there U go.
Send me feed back it if worked for you or not so that I can update the todo.
jedi_aka@yahoo.com
PS: BIG thanks to oportocala`

[up](https://www.php.net/manual/vote-note.php?id=74692&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74692&page=features.file-upload&vote=down "Vote down!")

19


[**_svenr at selfhtml dot org_**](https://www.php.net/manual/en/features.file-upload.php#74692) [¶](https://www.php.net/manual/en/features.file-upload.php#74692)

**18 years ago**

`Clarification on the MAX_FILE_SIZE hidden form field:
PHP has the somewhat strange feature of checking multiple "maximum file sizes".
The two widely known limits are the php.ini settings "post_max_size" and "upload_max_size", which in combination impose a hard limit on the maximum amount of data that can be received.
In addition to this PHP somehow got implemented a soft limit feature. It checks the existance of a form field names "max_file_size" (upper case is also OK), which should contain an integer with the maximum number of bytes allowed. If the uploaded file is bigger than the integer in this field, PHP disallows this upload and presents an error code in the $_FILES-Array.
The PHP documentation also makes (or made - see bug #40387 - [http://bugs.php.net/bug.php?id=40387](http://bugs.php.net/bug.php?id=40387)) vague references to "allows browsers to check the file size before uploading". This, however, is not true and has never been. Up til today there has never been a RFC proposing the usage of such named form field, nor has there been a browser actually checking its existance or content, or preventing anything. The PHP documentation implies that a browser may alert the user that his upload is too big - this is simply wrong.
Please note that using this PHP feature is not a good idea. A form field can easily be changed by the client. If you have to check the size of a file, do it conventionally within your script, using a script-defined integer, not an arbitrary number you got from the HTTP client (which always must be mistrusted from a security standpoint).`

[up](https://www.php.net/manual/vote-note.php?id=88591&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88591&page=features.file-upload&vote=down "Vote down!")

16


[**_info at levaravel dot com_**](https://www.php.net/manual/en/features.file-upload.php#88591) [¶](https://www.php.net/manual/en/features.file-upload.php#88591)

**16 years ago**

`A little codesnippet which returns a filesize in a more legible format.
<?php
function display_filesize($filesize){

    if(is_numeric($filesize)){
    $decr = 1024; $step = 0;
    $prefix = array('Byte','KB','MB','GB','TB','PB');

    while(($filesize / $decr) > 0.9){
        $filesize = $filesize / $decr;
        $step++;
    }
    return round($filesize,2).' '.$prefix[$step];
    } else {
    return 'NaN';
    }

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=82762&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82762&page=features.file-upload&vote=down "Vote down!")

10


[**_Rob_**](https://www.php.net/manual/en/features.file-upload.php#82762) [¶](https://www.php.net/manual/en/features.file-upload.php#82762)

**17 years ago**

`You should not have any directories within your website root that has the permissions required for file upload.  If you are going to do a file upload, I recommend you use the PHP FTP Functions in conjunction with your file field, that way the files are transferred to a remote FTP location separate from your server.`

[up](https://www.php.net/manual/vote-note.php?id=53133&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53133&page=features.file-upload&vote=down "Vote down!")

20


[**_keith at phpdiary dot org_**](https://www.php.net/manual/en/features.file-upload.php#53133) [¶](https://www.php.net/manual/en/features.file-upload.php#53133)

**20 years ago**

`Caution: *DO NOT* trust $_FILES['userfile']['type'] to verify the uploaded filetype; if you do so your server could be compromised.  I'll show you why below:
The manual (if you scroll above) states: $_FILES['userfile']['type'] -  The mime type of the file, if the browser provided this information. An example would be "image/gif".
Be reminded that this mime type can easily be faked as PHP doesn't go very far in verifying whether it really is what the end user reported!
So, someone could upload a nasty .php script as an "image/gif" and execute the url to the "image".
My best bet would be for you to check the extension of the file and using exif_imagetype() to check for valid images.  Many people have suggested the use of getimagesize() which returns an array if the file is indeed an image and false otherwise, but exif_imagetype() is much faster. (the manual says it so)`

[up](https://www.php.net/manual/vote-note.php?id=87216&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87216&page=features.file-upload&vote=down "Vote down!")

7


[**_rnagavel at yahoo dot com dot au_**](https://www.php.net/manual/en/features.file-upload.php#87216) [¶](https://www.php.net/manual/en/features.file-upload.php#87216)

**16 years ago**

`If $_FILES is always empty, check the method of your form.
It should be POST. Default method of a form is GET.
<form action="myaction.php">
<input type="file" name"userfile">
</form>
File will not be uploaded as default method of the form is GET.
<form action="myaction.php" method="POST">
<input type="file" name"userfile">
</form>
Files will be uploaded and $_FILES will be populated.`

[up](https://www.php.net/manual/vote-note.php?id=66025&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66025&page=features.file-upload&vote=down "Vote down!")

5


[**_david at cygnet dot be_**](https://www.php.net/manual/en/features.file-upload.php#66025) [¶](https://www.php.net/manual/en/features.file-upload.php#66025)

**19 years ago**

`If you are experiencing problems posting files from Internet Explorer to a PHP script over an SSL connection, for instance "Page can not be displayed" or empty $_FILES and $_POST arrays (described by jason 10-Jan-2006 02:08), then check out this microsoft knowledgebase article:
[http://support.microsoft.com/?kbid=889334](http://support.microsoft.com/?kbid=889334)
This knowledgebase article explains how since service pack 2 there may be problems posting from IE over SSL. It is worth checking whether your problem is IE specific since this is definitely not a PHP problem!`

[up](https://www.php.net/manual/vote-note.php?id=60024&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60024&page=features.file-upload&vote=down "Vote down!")

7


[**_geert dot php at myrosoft dot com_**](https://www.php.net/manual/en/features.file-upload.php#60024) [¶](https://www.php.net/manual/en/features.file-upload.php#60024)

**19 years ago**

`When file names do contain single quote parts of the filename are being lost.
eg.: uploading a filename
      startName 'middlepart' endName.txt
will be uploaded (and hence stored in the _Files ['userfile'] variable as
      endName.txt
skipping everything before the second single quote.`

[up](https://www.php.net/manual/vote-note.php?id=87989&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87989&page=features.file-upload&vote=down "Vote down!")

7


[**_damien from valex_**](https://www.php.net/manual/en/features.file-upload.php#87989) [¶](https://www.php.net/manual/en/features.file-upload.php#87989)

**16 years ago**

`This is simpler method of checking for too much POST data (alternative to that by v3 from sonic-world.ru).
<?php
    if ($_SERVER['REQUEST_METHOD'] == 'POST' && empty($_POST) && $_SERVER['CONTENT_LENGTH'] > 0) {
        throw new Exception(sprintf('The server was unable to handle that much POST data (%s bytes) due to its current configuration', $_SERVER['CONTENT_LENGTH']));
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=51541&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=51541&page=features.file-upload&vote=down "Vote down!")

7


[**_robpet at tds dot net_**](https://www.php.net/manual/en/features.file-upload.php#51541) [¶](https://www.php.net/manual/en/features.file-upload.php#51541)

**20 years ago**

`People have remarked that incorrect permissions on the upload directory may prevent photos or other files from uploading.  Setting the Apache owner of the directory incorrectly will also prevent files from uploading -- I use a PHP script that creates a directory (if it doesn't exist already) before placing an uploaded file into it.  When the script creates the directory and then copies the uploaded file into the directory there is no problem because the owner of the file is whatever Apache is running as, typically "nobody". However, lets say that I've moved the site to a new server and have copied over existing file directories using FTP.  In this case the owner will have a different name from the Apache owner and files will not upload. The solution is to TelNet into the site and reset the owner to "nobody" or whatever Apache is running as using the CHOWN command.`

[up](https://www.php.net/manual/vote-note.php?id=55958&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55958&page=features.file-upload&vote=down "Vote down!")

7


[**_warwickbarnes at yahoo dot co dot uk_**](https://www.php.net/manual/en/features.file-upload.php#55958) [¶](https://www.php.net/manual/en/features.file-upload.php#55958)

**20 years ago**

`You may come across the following problem using PHP on Microsoft IIS: getting permission denied errors from the move_uploaded_file function even when all the folder permissions seem correct. I had to set the following to get it to work:
1. Write permissions on the the folder through the IIS management console.
2. Write permissions to IUSR_'server' in the folder's security settings.
3. Write permissions to "Domain Users" in the folder's security settings.
The third setting was required because my application itself lives in a secure folder - using authentication (either Basic or Windows Integrated) to identify the users. When the uploads happen IIS seems to be checking that these users have write access to the folder, not just whether the web server (IUSR_'server') has access.
Also, remember to set "Execute Permissions" to "None" in the IIS management console, so that people can't upload a script file and then run it. (Other checks of the uploaded file are recommended as well but 'Execute None' is a good start.)`

[up](https://www.php.net/manual/vote-note.php?id=109495&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109495&page=features.file-upload&vote=down "Vote down!")

5


[**_Thomas_**](https://www.php.net/manual/en/features.file-upload.php#109495) [¶](https://www.php.net/manual/en/features.file-upload.php#109495)

**13 years ago**

`MIME type can be faked.
VVV
$_FILES['userfile']['type']
The mime type of the file, if the browser provided this information. An example would be "image/gif". This mime type is however not checked on the PHP side and therefore don't take its value for granted.
[http://www.php.net/manual/en/features.file-upload.post-method.php](http://www.php.net/manual/en/features.file-upload.post-method.php)
[Editor's note: removed a reference to a deleted note, and edited the note to make sense by itself.]`

[up](https://www.php.net/manual/vote-note.php?id=48809&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48809&page=features.file-upload&vote=down "Vote down!")

4


[**_Tyfud_**](https://www.php.net/manual/en/features.file-upload.php#48809) [¶](https://www.php.net/manual/en/features.file-upload.php#48809)

**20 years ago**

`It's important to note that when using the move_uploaded_file() command, that some configurations (Especially IIS) will fail if you prefix the destination path with a leading "/". Try the following:
<?php move_uploaded_file($tmpFileName,'uploads/'.$fileName); ?>
Setting up permissions is also a must. Make sure all accounts have write access to your upload directory, and read access if you wish to view these files later. You might have to chmod() the directory or file afterwards as well if you're still getting access errors.`

[up](https://www.php.net/manual/vote-note.php?id=43372&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43372&page=features.file-upload&vote=down "Vote down!")

4


[**_olijon, iceland_**](https://www.php.net/manual/en/features.file-upload.php#43372) [¶](https://www.php.net/manual/en/features.file-upload.php#43372)

**21 years ago**

`When uploading large images, I got a "Document contains no data" error when using Netscape and an error page when using Explorer. My server setup is RH Linux 9, Apache 2 and PHP 4.3.
I found out that the following entry in the httpd.conf file was missing:
<Files *.php>
SetOutputFilter PHP
SetInputFilter PHP
LimitRequestBody 524288 (max size in bytes)
</Files>
When this had been added, everything worked smoothly.
- Oli Jon, Iceland`

[up](https://www.php.net/manual/vote-note.php?id=39654&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39654&page=features.file-upload&vote=down "Vote down!")

3


[**_maya\_gomez ~ at ~ mail ~ dot ~ ru_**](https://www.php.net/manual/en/features.file-upload.php#39654) [¶](https://www.php.net/manual/en/features.file-upload.php#39654)

**21 years ago**

`when you upload the file, $_FILES['file']['name'] contains its original name converted into server's default charset.
if a name contain characters that aren't present in default charset, the conversion fails and the $_FILES['file']['name'] remains in original charset.
i've got this behavior when uploading from a windows-1251 environment into koi8-r. if a filename has the number sign "?" (0xb9), it DOES NOT GET CONVERTED as soon as there is no such character in koi8-r.
Workaround i use:
<?php
if (strstr ($_FILES['file']['name'], chr(0xb9)) != "")
{
    $_FILES['file']['name'] = iconv (
        "windows-1251",
        "koi8-r",
        str_replace (chr(0xb9), "N.", $_FILES['file']['name']));
};
?>`

[up](https://www.php.net/manual/vote-note.php?id=45168&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=45168&page=features.file-upload&vote=down "Vote down!")

3


[**_therhinoman at hotmail dot com_**](https://www.php.net/manual/en/features.file-upload.php#45168) [¶](https://www.php.net/manual/en/features.file-upload.php#45168)

**21 years ago**

`If your upload script is meant only for uploading images, you can use the image function getimagesize() (does not require the GD image library) to make sure you're really getting an image and also filter image types.
<?php getimagesize($file); ?>
...will return false if the file is not an image or is not accessable, otherwise it will return an array...
<?php
$file = 'somefile.jpg';
# assuming you've already taken some other
# preventive measures such as checking file
# extensions...
$result_array = getimagesize($file);
if ($result_array !== false) {
    $mime_type = $result_array['mime'];
    switch($mime_type) {
        case "image/jpeg":
            echo "file is jpeg type";
            break;
        case "image/gif":
            echo "file is gif type";
            break;
        default:
            echo "file is an image, but not of gif or jpeg type";
    }
} else {
    echo "file is not a valid image file";
}
?>
using this function along with others mentioned on this page, image ploading can be made pretty much fool-proof.
See [http://php.net/manual/en/function.getimagesize.php](http://php.net/manual/en/function.getimagesize.php) for supported image types and more info.`

[up](https://www.php.net/manual/vote-note.php?id=56138&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56138&page=features.file-upload&vote=down "Vote down!")

2


[**_mariodivece at bytedive dot com_**](https://www.php.net/manual/en/features.file-upload.php#56138) [¶](https://www.php.net/manual/en/features.file-upload.php#56138)

**20 years ago**

`Just wanted to point out a detail that might be of interest to some:
when using base64_encode to store binary data in a database, you are increasing the size of the data by 1.33 times. There is a nicer way of storing the data directly. Try the following:
<?php $data = mysql_real_escape_string($data); ?>
This will leave the data untouched and formatted in the correct way and ready to be inserted right into a MySQL statement without wasting space.
By the way, I'd like to thank therebechips for his excellent advice on data chunks.`

[up](https://www.php.net/manual/vote-note.php?id=59156&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59156&page=features.file-upload&vote=down "Vote down!")

1


[**_djot at hotmail dot com_**](https://www.php.net/manual/en/features.file-upload.php#59156) [¶](https://www.php.net/manual/en/features.file-upload.php#59156)

**19 years ago**

`-
Be carefull with setting max_file_size via
<?php ini_get('upload_max_filesize'); ?>
ini_get might return values like "2M" which will result in non working uploads.
This was the "no no" in my case:
<?php
$form = '<input type="hidden" name="MAX_FILE_SIZE" value=".ini_get('upload_max_filesize')." />';
?>
Files were uploaded to the server, but than there was not any upload information, not even an error message. $_FILES was completly empty.
djot
-`

[up](https://www.php.net/manual/vote-note.php?id=49807&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49807&page=features.file-upload&vote=down "Vote down!")

1


[**_Leevi at izilla dot com dot au_**](https://www.php.net/manual/en/features.file-upload.php#49807) [¶](https://www.php.net/manual/en/features.file-upload.php#49807)

**20 years ago**

`This may help a newbie to file uploads.. it took advice from a friend to fix it..
If you are using
-windows xp
-iis 5
-php 5
If you keep getting permission errors on file uploads... and you have sworn you set the permissions to write to the directory in iis...
double check that
a) in windows explorer under tools > folder options
click the view tab
scroll down all the way to "use simple file sharing (recommended)"
uncheck this box
b) find the folder you wish to upload to on your server
c) click properties and then the security tab
d) make sure the appropriate write settings are checked.
you may want to test by setting "everyone" to have full permission....
BEWARE doing this will open up big security holes on your server....
hope this helps
Leevi Graham`

[up](https://www.php.net/manual/vote-note.php?id=93602&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93602&page=features.file-upload&vote=down "Vote down!")

 -3


[**_Phil Ciebiera_**](https://www.php.net/manual/en/features.file-upload.php#93602) [¶](https://www.php.net/manual/en/features.file-upload.php#93602)

**16 years ago**

`On a Microsoft platform utilizing IIS, you may run into a situation where, upon moving the uploaded file, anonymous web users can't access the content without being prompted to authenticate first...
The reason for this is, the uploaded file will inherit the permissions of the directory specified in the directive upload_tmp_dir of php.ini.  If this directive isn't set, the default of C:\Windows\Temp is used.
You can work around this by granting the IUSR_[server name] user read access to your temporary upload directory, so that after you move_uploaded_file the permissions will already be set properly.
It's also a good idea to set the Execute Permissions of the upload directory to NOT include Executables, for security reasons.
To accomplish this:
-Open the IIS Manager
-Browse to the relevant sites directory where the uploads will be placed
-Right Click the folder and select Properties
-In the Directory tab of the resulting dialog, set the Execute permissions to be None
This took me a while to figure out, so I hope this helps save some other peoples time.`

[up](https://www.php.net/manual/vote-note.php?id=82869&page=features.file-upload&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82869&page=features.file-upload&vote=down "Vote down!")

 -3


[**_jahajee_**](https://www.php.net/manual/en/features.file-upload.php#82869) [¶](https://www.php.net/manual/en/features.file-upload.php#82869)

**17 years ago**

`hi , i was having difficulty with the upload_max_filesize , if u set the max file size lesser than the php setting then ur script to report error will only work till this difference between ur max set file size and the php set max size .Hence if the uploaded file exceeds the php max file size then php end abruptly without a trace of error that is it behaves like no file is uploaded and hence no error reported .Sure if uploading a file is optional for a form then a user who uploads larger file will get no error and still the form will be processed only without the file.
The method of using GET can't be used for optional uploads. Can't find help even in the bugs .Be careful with optional uploads.
jahajee`

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.file-upload&repo=en&redirect=https://www.php.net/manual/en/features.file-upload.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google