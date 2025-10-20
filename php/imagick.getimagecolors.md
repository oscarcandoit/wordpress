---
url: https://www.php.net/manual/en/imagick.getimagecolors.php
scraped_at: 2025-10-20T02:59:35.518Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Imagick::getImageColors

(PECL imagick 2, PECL imagick 3)

Imagick::getImageColors — Gets the number of unique colors in the image

### Description [¶](https://www.php.net/manual/en/imagick.getimagecolors.php\#refsect1-imagick.getimagecolors-description)

public**Imagick::getImageColors**(): [int](https://www.php.net/manual/en/language.types.integer.php)

Gets the number of unique colors in the image.


### Parameters [¶](https://www.php.net/manual/en/imagick.getimagecolors.php\#refsect1-imagick.getimagecolors-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/imagick.getimagecolors.php\#refsect1-imagick.getimagecolors-returnvalues)

Returns an [int](https://www.php.net/manual/en/language.types.integer.php), the number of unique colors in the image.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagick/getimagecolors.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagick.getimagecolors%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.getimagecolors&repo=en&redirect=https://www.php.net/manual/en/imagick.getimagecolors.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=108203&page=imagick.getimagecolors&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108203&page=imagick.getimagecolors&vote=down "Vote down!")

3


[**_holdoffhunger at gmail dot com_**](https://www.php.net/manual/en/imagick.getimagecolors.php#108203) [¶](https://www.php.net/manual/en/imagick.getimagecolors.php#108203)

**13 years ago**

`I've had difficulty getting this function to return the number of unique colors.  Also, I wanted to be able to have an array with each $key value being the RGB of the pixel, and each $value value being the number of times that pixel occurs.  Basically, a frequency list.  For example, you would have "1 / 0 / 0" for red as a $key value, and "25" for the number of times that pixel color was in the image.  So, I wrote some code to do that, using a combination of readImageFile, getImageWidth, getImageHeight, getImagePixelColor, and a simple x/y parser, like so :
<?php
        // Test File
        // ---------------------------------------------
            // Note: This file was just a picture of a 5x5 red square
            //    inside of a gigantic 521x512 black square, and
            //    then I did a bunch of random, yellow zigzags.
    $file_to_grab_with_location = "test.bmp";
    $imagick_type = new Imagick();

        // Open File
        // ---------------------------------------------

    $file_handle_for_viewing_image_file = fopen($file_to_grab_with_location, 'a+');
    $imagick_type->readImageFile($file_handle_for_viewing_image_file);

        // Preset Information
        // ---------------------------------------------
    $frequency_list_of_values = array();

        // Parse Pixels
        // ---------------------------------------------

    $image_resolution_width = $imagick_type->getImageWidth();
    $image_resolution_height = $imagick_type->getImageHeight();

    print("Image Resolution:  Width - $image_resolution_width / Height - $image_resolution_height<br><br>");

        // Parse Image Top-to-Bottom (Y-Variable)
        // ---------------------------------------------

    for($y = 0; $y < $image_resolution_height; $y++)
    {
            // Parse Image Left-to-Right (X-Variable)
            // ---------------------------------------------

        for($x = 0; $x < $image_resolution_width; $x++)
        {

                // Image Pixel Color
                // ---------------------------------------------

            $pixel_to_examine = $imagick_type->getImagePixelColor($x,$y);

            $pixel_to_examine_color_value_red = $pixel_to_examine->getColorValue(imagick::COLOR_RED);
            $pixel_to_examine_color_value_green = $pixel_to_examine->getColorValue(imagick::COLOR_GREEN);
            $pixel_to_examine_color_value_blue = $pixel_to_examine->getColorValue(imagick::COLOR_BLUE);
                // Set Key Value
                // ---------------------------------------------

            $key_value =    $pixel_to_examine_color_value_red    .    " / "    .
                    $pixel_to_examine_color_value_green    .    " / "    .
                    $pixel_to_examine_color_value_blue            ;

                // Increment Array Entry for Color
                // ---------------------------------------------

            if(isset($frequency_list_of_values[$key_value]) == TRUE)
            {
                $temp = $frequency_list_of_values[$key_value];
                $temp++;
                $frequency_list_of_values[$key_value] = $temp;
            }
            else
            {
                $frequency_list_of_values[$key_value] = 1;
            }
        }
    }

        // Print Out Array of Values
        // ---------------------------------------------

    print("<pre>");
    print_r($frequency_list_of_values);
    print("</pre>");
/*
    Results:
    ------------------
Image Resolution: Width - 521 / Height - 512
Array
(
    [1 / 0 / 0] => 25
    [0 / 0 / 1] => 264107
    [1 / 1 / 0] => 2620
)
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=122583&page=imagick.getimagecolors&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122583&page=imagick.getimagecolors&vote=down "Vote down!")

 -4


[**_amaral dot regis at hotmail dot com_**](https://www.php.net/manual/en/imagick.getimagecolors.php#122583) [¶](https://www.php.net/manual/en/imagick.getimagecolors.php#122583)

**7 years ago**

`O exemplo anterior apresentou números fracionados nas chaves da variável $frequency_list_of_values:
Array
(
    [1 / 0 / 1] => 157295
    [0.83529411764706 / 0.87843137254902 / 0.82352941176471] => 1
    [0.80392156862745 / 0.84705882352941 / 0.7843137254902] => 2
    [0.8156862745098 / 0.84705882352941 / 0.78823529411765] => 1
...
Então eu fiz uma alteração que melhora o resultado para quem esta buscando saber quais as cores dominantes na imagem, mostrando a chave com o valor rgb exato:
<?php
        $file_to_grab_with_location = $imagepath; //caminho relativo ao arquivo de imagem
        $imagick_type = new \Imagick();
        $file_handle_for_viewing_image_file = fopen($file_to_grab_with_location, 'a+');
        $imagick_type->readImageFile($file_handle_for_viewing_image_file);
        $frequency_list_of_values = array();
        $image_resolution_width = $imagick_type->getImageWidth();
        $image_resolution_height = $imagick_type->getImageHeight();
        print("Image Resolution:  Width - $image_resolution_width / Height - $image_resolution_height<br><br>");
        for($y = 0; $y < $image_resolution_height; $y++)
        {
            for($x = 0; $x < $image_resolution_width; $x++)
            {
                $pixel_to_examine = $imagick_type->getImagePixelColor($x,$y);
                if(isset($frequency_list_of_values[$pixel_to_examine->getColorAsString()]) == TRUE)
                {
                    $temp = $frequency_list_of_values[$pixel_to_examine->getColorAsString()];
                    $temp++;
                    $frequency_list_of_values[$pixel_to_examine->getColorAsString()] = $temp;
                }
                else
                {
                    $frequency_list_of_values[$pixel_to_examine->getColorAsString()] = 1;
                }
            }
            arsort($frequency_list_of_values);
        }
        print("<pre>");
        print_r($frequency_list_of_values);
        print("</pre>");
?>
Resultado:
Image Resolution: Width - 1965 / Height - 998
Array
(
    [srgba(255,0,255,0)] => 451654
    [srgb(54,52,53)] => 281069
    [srgb(177,51,54)] => 130449
    [srgb(236,50,55)] => 64001
...
O método é demorado para imagens muito grandes, pois ele analisa pixel a pixel.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.getimagecolors&repo=en&redirect=https://www.php.net/manual/en/imagick.getimagecolors.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google