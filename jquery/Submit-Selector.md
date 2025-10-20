---
url: https://api.jquery.com/submit-selector/
scraped_at: 2025-10-20T03:30:01.684Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## submit selector

**Description:** Selects all elements of type submit.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":submit" )


The `:submit` selector typically applies to button or input elements. Note that some browsers treat `<button>` element as `type="submit"` implicitly while others (such as Internet Explorer) do not. To ensure that markup works consistently across all browsers and guarantee that it is possible to consistently select buttons that will submit a form, always specify a `type` property.

### Additional Notes:

- Because `:submit` is a jQuery extension and not part of the CSS specification, queries using `:submit` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `input[type="submit"], button[type="submit"]` instead.


Finds all submit elements that are descendants of a td element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69<br>70<br>71<br>72<br>73<br>74<br>75<br>76<br>77<br>78<br>79<br>80<br>81<br>82<br>83<br>84<br>85<br>86<br>87<br>88<br>89<br>90<br>91<br>92<br>93<br>94<br>95<br>96<br>97<br>98<br>99<br>100<br>101<br>102<br>103<br>104<br>105<br>106<br>107<br>108<br>109<br>110<br>111<br>112<br>113<br>114<br>115<br>116<br>117<br>118<br>119<br>120<br>121<br>122<br>123<br>124 | ```<br>``` |

#### Demo: