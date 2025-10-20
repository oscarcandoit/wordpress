---
url: https://www.php.net/manual/en/ref.tidy.php
scraped_at: 2025-10-20T02:36:52.858Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Tidy Functions [¶](https://www.php.net/manual/en/ref.tidy.php\#ref.tidy)

## Table of Contents [¶](https://www.php.net/manual/en/ref.tidy.php\#ref.tidy)

- [ob\_tidyhandler](https://www.php.net/manual/en/function.ob-tidyhandler.php) — ob\_start callback function to repair the buffer
- [tidy\_access\_count](https://www.php.net/manual/en/function.tidy-access-count.php) — Returns the Number of Tidy accessibility warnings encountered for specified document
- [tidy\_config\_count](https://www.php.net/manual/en/function.tidy-config-count.php) — Returns the Number of Tidy configuration errors encountered for specified document
- [tidy\_error\_count](https://www.php.net/manual/en/function.tidy-error-count.php) — Returns the Number of Tidy errors encountered for specified document
- [tidy\_get\_output](https://www.php.net/manual/en/function.tidy-get-output.php) — Return a string representing the parsed tidy markup
- [tidy\_warning\_count](https://www.php.net/manual/en/function.tidy-warning-count.php) — Returns the Number of Tidy warnings encountered for specified document

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/tidy/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.tidy%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.tidy&repo=en&redirect=https://www.php.net/manual/en/ref.tidy.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=62342&page=ref.tidy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62342&page=ref.tidy&vote=down "Vote down!")

2


[**_patatraboum at nospam dot fr_**](https://www.php.net/manual/en/ref.tidy.php#62342) [¶](https://www.php.net/manual/en/ref.tidy.php#62342)

**19 years ago**

`<?php
//
//The tidy tree of your favorite !
//For PHP 5 (CGI)
//Thanks to john@php.net
//
$file=" [http://www.php.net](http://www.php.net/)";
//
$cns=get_defined_constants(true);
$tidyCns=array("tags"=>array(),"types"=>array());
foreach($cns["tidy"] as $cKey=>$cVal){
    if($cPos=strpos($cKey,$cStr="TAG")) $tidyCns["tags"][$cVal]="$cStr : ".substr($cKey,$cPos+strlen($cStr)+1);
    elseif($cPos=strpos($cKey,$cStr="TYPE")) $tidyCns["types"][$cVal]="$cStr : ".substr($cKey,$cPos+strlen($cStr)+1);
}
$tidyNext=array();
//
echo "<html><head><meta http-equiv='Content-Type' content='text/html; charset=windows-1252'><title>Tidy Tree :: $file</title></head>";
echo "<body><pre>";
//
tidyTree(tidy_get_root(tidy_parse_file($file)),0);
//
function tidyTree($tidy,$level){
    global $tidyCns,$tidyNext;
    $tidyTab=array();
    $tidyKeys=array("type","value","id","attribute");
    foreach($tidy as $pKey=>$pVal){
        if(in_array($pKey,$tidyKeys)) $tidyTab[array_search($pKey,$tidyKeys)]=$pVal;
    }
    ksort($tidyTab);
    foreach($tidyTab as $pKey=>$pVal){
        switch($pKey){
            case 0 :
                if($pVal==4) $value=true; else $value=false;
                echo indent(true,$level).$tidyCns["types"][$pVal]."\n"; break;
            case 1 :
                if($value){
                    echo indent(false,$level)."VALEUR : ".str_replace("\n","\n".indent(false,$level),$pVal)."\n";
                }
                break;
            case 2 :
                echo indent(false,$level).$tidyCns["tags"][$pVal]."\n"; break;
            case 3 :
                if($pVal!=NULL){
                    echo indent(false,$level)."ATTRIBUTS : ";
                    foreach ($pVal as $aKey=>$aVal) echo "$aKey=$aVal "; echo "\n";
                }
        }
    }
    if($tidy->hasChildren()){
        $level++; $i=0;
        $tidyNext[$level]=true;
        echo indent(false,$level)."\n";
        foreach($tidy->child as $child){
            $i++;
            if($i==count($tidy->child)) $tidyNext[$level]=false;
            tidyTree($child,$level);
        }
    }
    else echo indent(false,$level)."\n";
}
//
function indent($tidyType,$level){
    global $tidyNext;
    $indent="";
    for($i=1;$i<=$level;$i++){
        if($i<$level||!$tidyType){
            if($tidyNext[$i]) $str="|  "; else $str="   ";
        }
        else $str="+--";
        $indent=$indent.$str;
    }
    return $indent;
}
//
echo "</pre></body></html>";
//
?>`

[up](https://www.php.net/manual/vote-note.php?id=47001&page=ref.tidy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47001&page=ref.tidy&vote=down "Vote down!")

0


[**_bill dot mccuistion at qbopen dot com_**](https://www.php.net/manual/en/ref.tidy.php#47001) [¶](https://www.php.net/manual/en/ref.tidy.php#47001)

**20 years ago**

`Installing tidy on Fedora Core 2 required three libraries:
tidy...
tidy-devel...
libtidy...
All of which I found at [http://rpm.pbone.net](http://rpm.pbone.net/)
Then, finally, could "./configure --with-tidy"
Hope this helps someone out.  This was "REALLY" hard (for me) to figure out as no where else was clearly documented.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.tidy&repo=en&redirect=https://www.php.net/manual/en/ref.tidy.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google