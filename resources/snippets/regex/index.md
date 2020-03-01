# 常用正则表达式

## 通用类型

* 验证E-mail地址

`PHP`

```
$email = "test@ansoncheung.tk";
if (preg_match('/^[^0-9][a-zA-Z0-9_]+([.][a-zA-Z0-9_]+)*[@][a-zA-Z0-9_]+([.][a-zA-Z0-9_]+)*[.][a-zA-Z]{2,4}$/',$email)) {
    echo "Your email is ok.";
} else {
    echo "Wrong email address format";
}
```

`PHP`

```
if (filter_var('test+email@ansoncheung', FILTER_VALIDATE_EMAIL)) {
    echo "Your email is ok.";
} else {
    echo "Wrong email address format.";
}
```


* 验证用户名

>   包括字母、数字（A-Z，a-z，0-9）、下划线以及最低5个字符，最大20个字符

```
$username = "thisIsAUserName_1";
if (preg_match('/^[a-z\d_]{5,20}$/i', $username)) {
    echo "Your username is ok.";
} else {
    echo "Wrong username format.";
}
```


* 验证电话号码

>   这是一个验证美国电话号码的实例

```
$phone = "(021)423-2323";
if (preg_match('/\(?\d{3}\)?[-\s.]?\d{3}[-\s.]\d{4}/x', $phone)) {
    echo "Your phone number is ok.";
} else {
    echo "Wrong phone number.";
}
```

* 验证IP地址(IPv4)

`PHP`

```
$IP = "198.168.1.78";
if (preg_match('/^(([1-9]?[0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5]).){3}([1-9]?[0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$/',$IP)) {
    echo "Your IP address is ok.";
} else {
    echo "Wrong IP address.";
}
```

* 验证邮政编码

```
$zipcode = "12345-5434";
if (preg_match("/^([0-9]{5})(-[0-9]{4})?$/i",$zipcode)) {
    echo "Your Zip code is ok.";
} else {
    echo "Wrong Zip code.";
}
```

* 验证SSN（社会保险号）

>   一个验证美国SSN的实例

```
$ssn = "333-23-2329";
if (preg_match('/^[\d]{3}-[\d]{2}-[\d]{4}$/',$ssn)) {
    echo "Your SSN is ok.";
} else {
    echo "Wrong SSN.";
}
```


* 验证信用卡号

```
$cc = "378282246310005";
if (preg_match('/^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14}|6011[0-9]{12}|3(?:0[0-5]|[68][0-9])[0-9]{11}|3[47][0-9]{13})$/', $cc)) {
    echo "Your credit card number is ok.";
} else {
    echo "Wrong credit card number.";
}
```


* 验证域名

```
$url = "http://ansoncheung.tk/";
if (preg_match('/^(http|https|ftp):\/\/([A-Z0-9][A-Z0-9_-]*(?:\.[A-Z0-9][A-Z0-9_-]*)+):?(\d+)?\/?/i', $url)) {
    echo "Your url is ok.";
} else {
    echo "Wrong url.";
}
```

* 将文中关键词高亮显示

```
$text = "Sample sentence from AnsonCheung.tk, regular expression has become popular in web programming. Now we learn regex. According to wikipedia, Regular expressions (abbreviated as regex or regexp, with plural forms regexes, regexps, or regexen) are written in a formal language that can be interpreted by a regular expression processor";

$text = preg_replace("/\b(regex)\b/i", '<span style="background:#5fc9f6">\1</span>', $text);

echo $text;
```


## 参考文档

* [C语言中文网 - 正则表达式](http://c.biancheng.net/cpp/html/1406.html)
