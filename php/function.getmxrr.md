---
url: https://www.php.net/manual/en/function.getmxrr.php
scraped_at: 2025-10-20T02:48:18.044Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# getmxrr

(PHP 4, PHP 5, PHP 7, PHP 8)

getmxrr — Get MX records corresponding to a given Internet host name

### Description [¶](https://www.php.net/manual/en/function.getmxrr.php\#refsect1-function.getmxrr-description)

**getmxrr**([string](https://www.php.net/manual/en/language.types.string.php) `$hostname`, [array](https://www.php.net/manual/en/language.types.array.php) `&$hosts`, [array](https://www.php.net/manual/en/language.types.array.php) `&$weights` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Searches DNS for MX records corresponding to
`hostname`.


### Parameters [¶](https://www.php.net/manual/en/function.getmxrr.php\#refsect1-function.getmxrr-parameters)

`hostname`

The Internet host name.


`hosts`

A list of the MX records found is placed into the array
`hosts`.


`weights`

If the `weights` array is given, it will be filled
with the weight information gathered.


### Return Values [¶](https://www.php.net/manual/en/function.getmxrr.php\#refsect1-function.getmxrr-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if any records are found; returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if no records
were found or if an error occurred.


### Notes [¶](https://www.php.net/manual/en/function.getmxrr.php\#refsect1-function.getmxrr-notes)

> **Note**:
>
>
> This function should not be used for the purposes of address
> verification. Only the mailexchangers found in DNS are returned,
> however, according to [» RFC 2821](https://datatracker.ietf.org/doc/html/rfc2821)
> when no mail exchangers are listed, `hostname`
> itself should be used as the only mail exchanger with a priority of
> `0`.

> **Note**:
>
>
> For compatibility with Windows before this was implemented, then try the
> [» PEAR](https://pear.php.net/) class
> [» Net\_DNS](https://pear.php.net/package/Net_DNS).

### See Also [¶](https://www.php.net/manual/en/function.getmxrr.php\#refsect1-function.getmxrr-seealso)

- [checkdnsrr()](https://www.php.net/manual/en/function.checkdnsrr.php) \- Check DNS records corresponding to a given Internet host name or IP address
- [dns\_get\_record()](https://www.php.net/manual/en/function.dns-get-record.php) \- Fetch DNS Resource Records associated with a hostname
- [gethostbyname()](https://www.php.net/manual/en/function.gethostbyname.php) \- Get the IPv4 address corresponding to a given Internet host name
- [gethostbynamel()](https://www.php.net/manual/en/function.gethostbynamel.php) \- Get a list of IPv4 addresses corresponding to a given Internet host
name
- [gethostbyaddr()](https://www.php.net/manual/en/function.gethostbyaddr.php) \- Get the Internet host name corresponding to a given IP address
- the `named(8)` manual page

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/network/functions/getmxrr.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.getmxrr%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getmxrr&repo=en&redirect=https://www.php.net/manual/en/function.getmxrr.php)

### User Contributed Notes 19 notes

[up](https://www.php.net/manual/vote-note.php?id=103123&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103123&page=function.getmxrr&vote=down "Vote down!")

19


[**_Robert Imhoff_**](https://www.php.net/manual/en/function.getmxrr.php#103123) [¶](https://www.php.net/manual/en/function.getmxrr.php#103123)

**14 years ago**

`I tried using getmxrr() to validate the domain portion of email addresses in enquiry submission forms, and there is a curious effect with some top-level domains when checking non-existant domains.
With sdlkfjsdl.com, since the domain does not exist, getmxrr() returns false, as expected, and the returned mxhosts array is empty.
But with sdlkfjsdl.gov, getmxrr() returns true,  and the returned mxhosts array contains one element: NULL
With sdlkfjsdl.org, getmxrr() returns true,  and the returned mxhosts array contains one element: '0.0.0.0'
With sdlkfjsdl.co.uk, getmxrr()  returns true and supplies one MX record: uk-net-wildcard-null-mx.centralnic.net
So to validate the email domain, it would seem one has to check the returned mxhosts array to exclude the possibility of mxhosts being returned as NULL, 0.0.0.0 and wildcard ...`

[up](https://www.php.net/manual/vote-note.php?id=49290&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49290&page=function.getmxrr&vote=down "Vote down!")

10


[**_rune dot heggtveit at devzone dot progative dot com_**](https://www.php.net/manual/en/function.getmxrr.php#49290) [¶](https://www.php.net/manual/en/function.getmxrr.php#49290)

**20 years ago**

`An other way to do mx-lookup on a windows platform.
Rewrote this from an other class i wrote for DNS lookup - so it might be a bit messy - but hope you get the idea.
Big thanks to the rfc community.
<?php
class mxlookup
{
      var $dns_socket = NULL;
      var $QNAME = "";
      var $dns_packet= NULL;
      var $ANCOUNT = 0;
      var $cIx = 0;
      var $dns_repl_domain;
      var $arrMX = array();
      function mxlookup($domain, $dns="192.168.2.1")
      {
         $this->QNAME($domain);
         $this->pack_dns_packet();
         $dns_socket = fsockopen("udp://$dns", 53);
         fwrite($dns_socket,$this->dns_packet,strlen($this->dns_packet));
         $this->dns_reply  = fread($dns_socket,1);
         $bytes = stream_get_meta_data($dns_socket);
         $this->dns_reply .= fread($dns_socket,$bytes['unread_bytes']);
         fclose($dns_socket);
         $this->cIx=6;
         $this->ANCOUNT   = $this->gord(2);
         $this->cIx+=4;
         $this->parse_data($this->dns_repl_domain);
         $this->cIx+=7;
         for($ic=1;$ic<=$this->ANCOUNT;$ic++)
         {
           $QTYPE = ord($this->gdi($this->cIx));
           if($QTYPE!==15){print("[MX Record not returned]"); die();}
           $this->cIx+=9;
           $mxPref = ord($this->gdi($this->cIx));
           $this->parse_data($curmx);
           $this->arrMX[] = array("MX_Pref" => $mxPref, "MX" => $curmx);
           $this->cIx+=3;
         }
      }
      function parse_data(&$retval)
      {
        $arName = array();
        $byte = ord($this->gdi($this->cIx));
        while($byte!==0)
        {
          if($byte==192) //compressed
          {
            $tmpIx = $this->cIx;
            $this->cIx = ord($this->gdi($cIx));
            $tmpName = $retval;
            $this->parse_data($tmpName);
            $retval=$retval.".".$tmpName;
            $this->cIx = $tmpIx+1;
            return;
          }
          $retval="";
          $bCount = $byte;
          for($b=0;$b<$bCount;$b++)
          {
            $retval .= $this->gdi($this->cIx);
          }
          $arName[]=$retval;
         $byte = ord($this->gdi($this->cIx));
       }
       $retval=join(".",$arName);
     }
     function gdi(&$cIx,$bytes=1)
     {
       $this->cIx++;
       return(substr($this->dns_reply, $this->cIx-1, $bytes));
     }
      function QNAME($domain)
      {
        $dot_pos = 0; $temp = "";
        while($dot_pos=strpos($domain,"."))
        {
          $temp   = substr($domain,0,$dot_pos);
          $domain = substr($domain,$dot_pos+1);
          $this->QNAME .= chr(strlen($temp)).$temp;
        }
        $this->QNAME .= chr(strlen($domain)).$domain.chr(0);
      }
      function gord($ln=1)
      {
        $reply="";
        for($i=0;$i<$ln;$i++){
         $reply.=ord(substr($this->dns_reply,$this->cIx,1));
         $this->cIx++;
         }
        return $reply;
      }
      function pack_dns_packet()
      {
        $this->dns_packet = chr(0).chr(1).
                            chr(1).chr(0).
                            chr(0).chr(1).
                            chr(0).chr(0).
                            chr(0).chr(0).
                            chr(0).chr(0).
                            $this->QNAME.
                            chr(0).chr(15).
                            chr(0).chr(1);
      }
}
?>
<?php
/* Exampe of use: */
$mx = new mxlookup("php.net");
print $mx->ANCOUNT." MX Records\n";
print "Records returned for ".$mx->dns_repl_domain.":\n<pre>";
print_r($mx->arrMX);
?>
Return:
02 MX Records Records returned for php.net:
Array
(
    [0] => Array
        (
            [MX_Pref] => 15
            [MX] => smtp.osuosl.org
        )
    [1] => Array
        (
            [MX_Pref] => 5
            [MX] => osu1.php.net
        )
)`

[up](https://www.php.net/manual/vote-note.php?id=77751&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77751&page=function.getmxrr&vote=down "Vote down!")

3


[**_Jay_**](https://www.php.net/manual/en/function.getmxrr.php#77751) [¶](https://www.php.net/manual/en/function.getmxrr.php#77751)

**18 years ago**

`As stated, some of the code listed below will have trouble with multiple equal weights, such as if you query gmail.com. The following code will prevent that by switching the key/values.
<?php
// Get the records
getmxrr("gmail.com", $mx_records, $mx_weight);
// Put the records together in a array we can sort
for($i=0;$i<count($mx_records);$i++){
    $mxs[$mx_records[$i]] = $mx_weight[$i];
}
// Sort them
asort ($mxs);
// Since the keys actually hold the data we want, just put those in an array, called records
$records = array_keys($mxs);
// Simply echoes all the stuff in the records array
for($i = 0; $i < count($records); $i++){
    echo $records[$i];
    echo '<br>';
}
?>
If you wanted to get the weight, you would use "array_values($mxs);" instead of "array_keys($mxs);".
Hope this helps some people.`

[up](https://www.php.net/manual/vote-note.php?id=42396&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42396&page=function.getmxrr&vote=down "Vote down!")

3


[**_zorlac\_man at hotmail dot com_**](https://www.php.net/manual/en/function.getmxrr.php#42396) [¶](https://www.php.net/manual/en/function.getmxrr.php#42396)

**21 years ago**

`For some reason this and the other DNS lookup functions seem to be really slow on my Linux box. I've checked several things and have no explanation.
As a work-around, I gave in and just used a system call to dig:
<?php
CheckMX("fakedomain.org");
CheckMX("hotmail.com");
function CheckMX($domain) {
        exec("dig +short MX " . escapeshellarg($domain),$ips);
        if($ips[0] == "") {
                print "MX record found for $domain not found!\n";
                return FALSE;
        }
        print "MX Record for $domain found\n";
        return TRUE;
}
?>
Output:
MX record found for fakedomain.org not found!
MX Record for hotmail.com found
As someone else pointed out, it is prudent to check to see if the TLD has an IP address if the MX record is not found.`

[up](https://www.php.net/manual/vote-note.php?id=88033&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88033&page=function.getmxrr&vote=down "Vote down!")

1


[**_php \[spat\] hm2k.org_**](https://www.php.net/manual/en/function.getmxrr.php#88033) [¶](https://www.php.net/manual/en/function.getmxrr.php#88033)

**16 years ago**

`I decided to have a bash at this after doing a bit of research...
<?php
// getmxrr() support for Windows by HM2K <php [spat] hm2k.org>
function win_getmxrr($hostname, &$mxhosts, &$mxweight=false) {
    if (strtoupper(substr(PHP_OS, 0, 3)) != 'WIN') return;
    if (!is_array ($mxhosts) ) $mxhosts = array();
    if (empty($hostname)) return;
    $exec='nslookup -type=MX '.escapeshellarg($hostname);
    @exec($exec, $output);
    if (empty($output)) return;
    $i=-1;
    foreach ($output as $line) {
        $i++;
        if (preg_match("/^$hostname\tMX preference = ([0-9]+), mail exchanger = (.+)$/i", $line, $parts)) {
          $mxweight[$i] = trim($parts[1]);
          $mxhosts[$i] = trim($parts[2]);
        }
        if (preg_match('/responsible mail addr = (.+)$/i', $line, $parts)) {
          $mxweight[$i] = $i;
          $mxhosts[$i] = trim($parts[1]);
        }
    }
    return ($i!=-1);
}
// Define
if (!function_exists('getmxrr')) {
    function getmxrr($hostname, &$mxhosts, &$mxweight=false) {
        return win_getmxrr($hostname, $mxhosts, $mxweight);
    }
}
/* example */
$domain='php.net';
echo "<pre>";
getmxrr($domain,$mxhosts,$mxweight);
print_r($mxhosts);
print_r($mxweight);
?>`

[up](https://www.php.net/manual/vote-note.php?id=119994&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119994&page=function.getmxrr&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.getmxrr.php#119994) [¶](https://www.php.net/manual/en/function.getmxrr.php#119994)

**9 years ago**

`One small polyfill for the getmxrr function(even when it's missing from linux system)
function getmxrr($hostname, &$mxhosts, array &$mxweight=null)
                {
                   $mxhosts = array();
                   exec('nslookup -type=mx '.$hostname, $result_arr);
                   foreach($result_arr as $line)
                    {
                        if (preg_match("/.*mail exchanger = (.*)/", $line, $matches))
                        {
                            $s_xo=explode(' ', $matches[1]);
                            $mxhosts[] = $s_xo[1];
                            $mxweight[] = $s_xo[0];
                        }
                    }
                   return( count($mxhosts) > 0 );
                }`

[up](https://www.php.net/manual/vote-note.php?id=25472&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25472&page=function.getmxrr&vote=down "Vote down!")

1


[**_geoffbrisbine A T y a h o o DOT c o m_**](https://www.php.net/manual/en/function.getmxrr.php#25472) [¶](https://www.php.net/manual/en/function.getmxrr.php#25472)

**23 years ago**

`I was pretty disappointed that the Win32 build of PHP doesn't incorporate getmxrr so, since I'm a naive newbie, I decided to hack together my own (and I stress hack).  This has been tested on Win 2000 and Win XP.  There's no reason this shouldn't work on Win NT but it will not work on Win 9x (you need the nslookup command).  It will finish with the array $mx that will be a multidimensional array with the MX preference, host name and ip address. You can do a print_r ( $mx ) to see what it looks like.
-----------------------------------------------
<?php
$command = "nslookup -type=mx yahoo.com";
exec ( $command, $result );

$i = 0;
while ( list ( $key, $value ) = each ( $result ) ) {
    if ( strstr ( $value, "mail exchanger" ) ) { $nslookup[$i] = $value; $i++; }
}

while ( list ( $key, $value ) = each ( $nslookup ) ) {
    $temp = explode ( " ", $value );
    $mx[$key][0] = $temp[3];
    $mx[$key][1] = $temp[7];
    $mx[$key][2] = gethostbyname ( $temp[7] );
}
    array_multisort ( $mx );
?>`

[up](https://www.php.net/manual/vote-note.php?id=70575&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70575&page=function.getmxrr&vote=down "Vote down!")

0


[**_tomhutter at web dot de_**](https://www.php.net/manual/en/function.getmxrr.php#70575) [¶](https://www.php.net/manual/en/function.getmxrr.php#70575)

**18 years ago**

`Leonardt's code fails with multiple mx records with the same wight. You can easily change this by switching keys and values in the mxs array:
     for($i=0;$i<count($mx_records);$i++){
       $mxs[$mx_records[$i]] = $mx_weight[$i];
     }
     arsort ($mxs );
     reset ($mxs);
    while (list ($mx_host, $mx_weight) = each ($mxs) ) {
cheers
Tom`

[up](https://www.php.net/manual/vote-note.php?id=70401&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70401&page=function.getmxrr&vote=down "Vote down!")

0


[**_php dot net at oitc dot com_**](https://www.php.net/manual/en/function.getmxrr.php#70401) [¶](https://www.php.net/manual/en/function.getmxrr.php#70401)

**19 years ago**

`This function has some strange side effects when dealing with aliases...
My function:
        if (getmxrr($fqdn, $mx_records, $mx_weight)) {
            // copy mx records and weight into array $mxs
            // ignore multiple mx's at the same weight
            for ($i = 0; $i < count($mx_records); $i++) {
                $mxs[$mx_weight[$i]] = $mx_records[$i];
            }
            // sort array mxs to get servers with highest priority
            ksort ($mxs, SORT_NUMERIC);
            reset ($mxs);
        } else {
            // No MX so use A
            $mxs[0]= $fqdn;
        }
fails because a $fqdn containing an alias returns a true yet on return both $mx_records and $mx_weight contain nothing!
The solution until this gets fixed is to replace if (getmxrr($fqdn, $mx_records, $mx_weight)) with
        // Handle aliases etc.
        if ($result = getmxrr($fqdn, $mx_records, $mx_weight)) {
            if(!isset($mx_records) || (count($mx_records) == 0)) $result = false;
        }
        // Process MXs
        if ($result) {
Hope this helps others....  Tom`

[up](https://www.php.net/manual/vote-note.php?id=69869&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69869&page=function.getmxrr&vote=down "Vote down!")

0


[**_MagicalTux at ooKoo dot org_**](https://www.php.net/manual/en/function.getmxrr.php#69869) [¶](https://www.php.net/manual/en/function.getmxrr.php#69869)

**19 years ago**

`If you want to use getmxrr on windows, be careful as choward AT fast DOT net DOT NO SPAM PLZ's function has a security flaw.
It passes its argument to an external command without escaping it. If you don't validate the input, someone may manage to run nasty things on your system.
Here's a fixed version (just added escapeshellarg())
<?php
function getmxrr($hostname, &$mxhosts)
{
    $mxhosts = array();
    exec('%SYSTEMDIRECTORY%\\nslookup.exe -q=mx '.escapeshellarg($hostname), $result_arr);
    foreach($result_arr as $line)
    {
      if (preg_match("/.*mail exchanger = (.*)/", $line, $matches))
          $mxhosts[] = $matches[1];
    }
    return( count($mxhosts) > 0 );
}//--End of workaround
//test..
getmxrr('yahoo.com', $mxhosts);
print_r($mxhosts);
?>
This way you'll avoid a lot of nasty things ;)`

[up](https://www.php.net/manual/vote-note.php?id=61773&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61773&page=function.getmxrr&vote=down "Vote down!")

0


[**_off at NOSPAM dot abwesend dot de_**](https://www.php.net/manual/en/function.getmxrr.php#61773) [¶](https://www.php.net/manual/en/function.getmxrr.php#61773)

**19 years ago**

`Concerning the message by 'rolf at rowi dot net' (do a check on a address containing a subdomain) we could use:
$email = 'abc@etpc01.trier.fh-rpl.de';

$strDot      = '.';
$strAfterAt  = substr(strstr($email, '@'), 1);
$chunks      = explode($strDot, $strAfterAt);
$cntChunks   = count($chunks) - 1;
$strDomain = $chunks[($cntChunks-1)] . $strDot . $chunks[$cntChunks];
if (!getmxrr( $strDomain, $mxhosts )) {
    echo 'Mailserver not found';
}
// $strDomain is set to 'fh-rpl.de';`

[up](https://www.php.net/manual/vote-note.php?id=53182&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53182&page=function.getmxrr&vote=down "Vote down!")

0


[**_richard dot quadling at bandvulc dot co dot uk_**](https://www.php.net/manual/en/function.getmxrr.php#53182) [¶](https://www.php.net/manual/en/function.getmxrr.php#53182)

**20 years ago**

`Windows alternative for getmxrr without the need for PEAR.
<?php
define('DEFAULT_GATEWAY', 'nnn.nnn.nnn.nnn');
if (!function_exists('getmxrr'))
    {
    /*
        This function is a replacement for the missing Windows function getmxrr.

        The parameters are the same as those for the normal getmxrr function.

        The steps this function takes are :

        1 - Use NSLOOKUP.EXE to get the MX records for the supplied Host.
        2 - Use regular expressions to extract the mail servers and the preference.
        3 - Sort the results by preference.
        4 - Set the return arrays.
        5 - Return true or false.
    */
    function getmxrr($s_HostName, array &$a_MXHosts = NULL, array &$a_Weights = NULL)
        {
        // Simulate all the required network activity by executing windows' NSLOOKUP.
        $s_NSLookup = shell_exec("nslookup -q=mx {$s_HostName} 2>nul");
        preg_match_all("'^.*MX preference = (\d{1,10}), mail exchanger = (.*)$'simU", $s_NSLookup, $a_MXMatches);
        // If there is something to return ...
        if (count($a_MXMatches[2]) > 0)
            {
            // Produce output arrays if they have been requested.
            $i_ArgCount = func_num_args();
            if ($i_ArgCount > 1)
                {
                array_multisort($a_MXMatches[1], $a_MXMatches[2]);
                switch ($i_ArgCount)
                    {
                    case 3 :
                        $a_Weights = $a_MXMatches[1];
                    case 2 :
                        $a_MXHosts = $a_MXMatches[2];
                    }
                }
            return True;
            }
        else
            {
            return False;
            }
        }
    }
?>
You will need to know your default gateway (either it's IP address or its name).
To do this, run the program IPCONFIG /ALL at a cmd prompt and look for the Default Gateway.
Then replace the 'nnn.nnn.nnn.nnn' with the address.
Richard.`

[up](https://www.php.net/manual/vote-note.php?id=40236&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40236&page=function.getmxrr&vote=down "Vote down!")

 -1


[**_ng4rrjanbiah at rediffmail dot com_**](https://www.php.net/manual/en/function.getmxrr.php#40236) [¶](https://www.php.net/manual/en/function.getmxrr.php#40236)

**21 years ago**

`Here is a better workaround for Windows platform. Tested on Windows XP. Highly impressed by "geoffbrisbine A T y a h o o DOT c o m"'s idea of nslookup usage.
<?php
function getmxrr($hostname, &$mxhosts)
{
$mxhosts = array();
exec('nslookup -type=mx '.$hostname, $result_arr);
foreach($result_arr as $line)
    {
      if (preg_match("/.*mail exchanger = (.*)/", $line, $matches))
          $mxhosts[] = $matches[1];
    }
return( count($mxhosts) > 0 );
}//--End of workaround
//test..
echo getmxrr('yahoo.com', $mxhosts);
print_r($mxhosts);
?>
HTH,
R. Rajesh Jeba Anbiah`

[up](https://www.php.net/manual/vote-note.php?id=10675&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=10675&page=function.getmxrr&vote=down "Vote down!")

 -1


[**_paul at start dot co dot uk_**](https://www.php.net/manual/en/function.getmxrr.php#10675) [¶](https://www.php.net/manual/en/function.getmxrr.php#10675)

**24 years ago**

`Prevent your dns server from 'creating' a valid host name by appending the local domain to incomplete emails by appending to the domain a  trailing . both in the pattern match and mx checks:
<?php
if (eregi("^[0-9a-z_]([-_.]?[0-9a-z])*@[0-9a-z][-.0-9a-z]*\\.[a-z]{2,3}[.]?$", $string, $check)) {
    $host = substr(strstr($check[0], '@'), 1).".";
    if ( getmxrr($host, $validate_email_temp) )
        return TRUE;
    // THIS WILL CATCH DNSs THAT ARE NOT MX.
    if(checkdnsrr($host,"ANY"))
        return TRUE;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=48673&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48673&page=function.getmxrr&vote=down "Vote down!")

 -2


[**_siclawrence at gmail dot com_**](https://www.php.net/manual/en/function.getmxrr.php#48673) [¶](https://www.php.net/manual/en/function.getmxrr.php#48673)

**20 years ago**

`This code replicates online tools that let you check if an email address is valid. First it checks if the email format is correct, then looks up and prints the mx records. All nicely formatted with fancy words that in the end prints whether the email address valid or invalid.
<?php
$email = "email@domain.com";
print("Checking: $email<br>");
if (eregi("^[_a-z0-9-]+(\.[_a-z0-9-]+)*@[a-z0-9-]+(\.[a-z0-9-]+)+$", $email)) {
    print("Format Test: PASSED<br>");
    print("Online host verification Test...<br><br>");
    print("MX Records for: $email<br>");

    list($alias, $domain) = split("@", $email);

    if (checkdnsrr($domain, "MX")) {

        getmxrr($domain, $mxhosts);

        foreach($mxhosts as $mxKey => $mxValue){
            print("&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$mxValue<br>");
        }

        print("Online host verification Test: PASSED<br><br>");
        print("Email Status: VALID");

    } else {

        print("&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;No records found.<br>");
        print("Online host verification Test: FAILED<br><br>");
        print("Email Status: INVALID");

    }
} else {
    print("Format Test: FAILED<br><br>");
    print("Invalid email address provided.<br><br>");
    print("Email Status: INVALID");

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=64117&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64117&page=function.getmxrr&vote=down "Vote down!")

 -1


[**_Lennart Poot(www.twing.nl)_**](https://www.php.net/manual/en/function.getmxrr.php#64117) [¶](https://www.php.net/manual/en/function.getmxrr.php#64117)

**19 years ago**

`This script validates an e-mail adress using getmxrr and fsockopen
1. it validates the syntax of the address.
2. get MX records by hostname
3. connect mail server and verify mailbox(using smtp command RCTP TO:<email>)
When the function "validate_email([email])" fails connecting the mail server with the highest priority in the MX record it will continue with the second mail server and so on..
The function "validate_email([email])" returns 0 when it failes one the 3 steps above, it will return 1 otherwise
Grtz Lennart Poot
<?
function validate_email($email){
$mailparts=explode("@",$email);
$hostname = $mailparts[1];
// validate email address syntax
$exp = "^[a-z\'0-9]+([._-][a-z\'0-9]+)*@([a-z0-9]+([._-][a-z0-9]+))+$";
$b_valid_syntax=eregi($exp, $email);
// get mx addresses by getmxrr
$b_mx_avail=getmxrr( $hostname, $mx_records, $mx_weight );
$b_server_found=0;
if($b_valid_syntax && $b_mx_avail){
     // copy mx records and weight into array $mxs
     $mxs=array();
     for($i=0;$i<count($mx_records);$i++){
       $mxs[$mx_weight[$i]]=$mx_records[$i];
     }
     // sort array mxs to get servers with highest prio
     ksort ($mxs, SORT_NUMERIC );
     reset ($mxs);
     while (list ($mx_weight, $mx_host) = each ($mxs) ) {
       if($b_server_found == 0){
         //try connection on port 25
         $fp = @fsockopen($mx_host,25, $errno, $errstr, 2);
         if($fp){
           $ms_resp="";
           // say HELO to mailserver
           $ms_resp.=send_command($fp, "HELO microsoft.com");
           // initialize sending mail
           $ms_resp.=send_command($fp, "MAIL FROM:<support@microsoft.com>");
           // try receipent address, will return 250 when ok..
           $rcpt_text=send_command($fp, "RCPT TO:<".$email.">");
           $ms_resp.=$rcpt_text;

           if(substr( $rcpt_text, 0, 3) == "250")
             $b_server_found=1;
           // quit mail server connection
           $ms_resp.=send_command($fp, "QUIT");
         fclose($fp);
         }
       }
    }
}
return $b_server_found;
}
function send_command($fp, $out){
fwrite($fp, $out . "\r\n");
return get_data($fp);
}
function get_data($fp){
$s="";
stream_set_timeout($fp, 2);
for($i=0;$i<2;$i++)
    $s.=fgets($fp, 1024);
return $s;
}
// support windows platforms
if (!function_exists ('getmxrr') ) {
function getmxrr($hostname, &$mxhosts, &$mxweight) {
    if (!is_array ($mxhosts) ) {
      $mxhosts = array ();
    }
    if (!empty ($hostname) ) {
      $output = "";
      @exec ("nslookup.exe -type=MX $hostname.", $output);
      $imx=-1;
      foreach ($output as $line) {
        $imx++;
        $parts = "";
        if (preg_match ("/^$hostname\tMX preference = ([0-9]+), mail exchanger = (.*)$/", $line, $parts) ) {
          $mxweight[$imx] = $parts[1];
          $mxhosts[$imx] = $parts[2];
        }
      }
      return ($imx!=-1);
    }
    return false;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=62745&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62745&page=function.getmxrr&vote=down "Vote down!")

 -1


[**_jeff at pzenix dot com_**](https://www.php.net/manual/en/function.getmxrr.php#62745) [¶](https://www.php.net/manual/en/function.getmxrr.php#62745)

**19 years ago**

`I should point out that the below example won't work with some domains (.co.uk, .org.uk, .net.uk for example) because it assumes (possibly incorrectly) that the format is [ DOMAIN ].[ EXT ].`

[up](https://www.php.net/manual/vote-note.php?id=79782&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79782&page=function.getmxrr&vote=down "Vote down!")

 -2


[**_TZ at inpetho dot net_**](https://www.php.net/manual/en/function.getmxrr.php#79782) [¶](https://www.php.net/manual/en/function.getmxrr.php#79782)

**17 years ago**

`If greylisting is installed on the mx host then he send a "451 4.7.1 Please try again later"
My code fragment:
<?php
//...
foreach ($mx_records as $mx_host) {
    $code = CheckMX($mx_host, $eMail);
    if ($code == 0)    continue; // host not found
    if ($code == 451)    $code = CheckMX($mx_host, $eMail); // Greylisting
    if ($code == 250)    {
        $ok = true;
        break;
    }
}
//...
function CheckMX($mx_host, $eMail)
{
    $code = 0;
    $fp = @fsockopen($mx_host, 25, $errno, $errstr, 2);
    if ($fp)    {
        send_command($fp, 'HELO microsoft.com');
        send_command($fp, 'MAIL FROM:<support@microsoft.com>');
        $erg = send_command($fp, 'RCPT TO:<'.$eMail.'>');
        fclose($fp);
        $code = intval(substr($erg, 0, 3));
    }
    return $code;
}
//...
?>`

[up](https://www.php.net/manual/vote-note.php?id=49251&page=function.getmxrr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49251&page=function.getmxrr&vote=down "Vote down!")

 -2


[**_rolf at rowi dot net_**](https://www.php.net/manual/en/function.getmxrr.php#49251) [¶](https://www.php.net/manual/en/function.getmxrr.php#49251)

**20 years ago**

`Be aware that not just user@example.com ist a valid address, also user@subnet.example.com is valid (but maybe less common). Just got into trouble with this check...
Rolf`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getmxrr&repo=en&redirect=https://www.php.net/manual/en/function.getmxrr.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google