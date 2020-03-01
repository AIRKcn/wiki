# PHP 注释规范

## 规范说明

### 文件注释 {Annotation of File}

    文件注释置于文件开头用于描述文件的作用与版本信息

```php
/**
 * simple description（必须）
 *
 * more description....... （必须）
 *
 * @package     user （必须）
 * @author      cnwangyl （必须）
 * @version     user.php    add by cnwangyl Y-m-d H:i （必须）
 * @version     user.php    modify by cnwangyl Y-m-d H:i
 */
```

### 类注释 {Annotation of Class}

    类注释置于类开头, 主要描述类的作用,  必要时要加实例说明

```php
/**
 * Enter description here... （必须）
 *
 * [example]
 * $user = new User ();
 * $user->init();
 * $userInfo = $user->getUserInfoByUid($uid);  *
 * [/example]
 *
 */
class User {

}
```

### 函数及方法注释 {Annotation of Method}

    函数及方法注释置于函数或方法开头, 主要描述函数或方法的作用, 及参数说明, 必要时要加使用说明

```php
/**
 * Enter description here... （必须）
 *
 * @param int $uid  //用户uid （必须）
 * @return bool （必须）
 * [example]
 * $user = new User ();
 * $user->init();
 * $userInfo = $user->getUserInfoByUid($uid);  *
 * [/example]
 *
 */
function  getUserInfoByUid($uid){
	return  false;
}
```

### 块注释 {Annotation of Logic-Block}

    块注释通常用于提供对一大段数据结构和算法的功能代码的描述。

```php
// =====================================
// description…
//
// =====================================
if ( true ) { // 条件 1 时的描述 condition 1
    // something to do
} else { // 非条件 1 时的描述 not condition 1
    // something to do
}
```

### 变量注释 {Annotation of Variable}

	描述变量信息, 与变量申明置于同一行, 注释尽可能的对齐

```php
public $username;       //用户uid
public $tel;            //用户电话
```

### 引入文件注释 {Annotation of Include}

    描述引入文件的功能与含义

```php
// 模块配置信息,  包含必须的模块配置信息
include ( SERVER_ROOT.'/config/compontentConfig.php' );
```

## 使用PHPDoc

    __标记__: 注释应该详细表述程序所实现的功能, 而非语言翻译

### PHPDoc规范

针对PHP程序, 使用PHPDoc规范, 可以通过自动化工具 PHPDocumenter 等工具, 生成项目 API 文档, 方便开发者查阅。

PHPDoc 中约定, 仅当

```php
/**
 *
 *
 */
```

此例中的注释时, 才认为是PHPDoc注释块, 以下情形将被规范忽略, 但可被其它开发者通过阅读源码参考

```php
/*
 注释块
*/
// 这是行注释
# 行注释
```

### 文档标记参考

* `@access` 该标记用于指明关键字的存取权限
    * 使用范围: class, function, var, define, module
    * 可用值: private、public 或 proteced
* `@author` 指明作者
    * 参数类型: 字符串
* `@copyright` 指明版权信息
    * 使用范围: class, function, var, define, module, use
    * 参数类型: 字符串
* `@example` 该标记用于解析一段文件内容, 并将他们高亮显示。Phpdoc会试图从该标记给的文件路径中读取文件内容
    * 参数类型: 字符串
* `@filesource` 和 `example` 类似, 只不过该标记将直接读取当前解析的php文件的内容并显示。
    * 参数类型: 字符串
* `@const` 用来指明 php 中 define 或 const 的常量
    * 使用范围: define, const
* `@global` 指明在此函数中引用的全局变量
    * 参数类型: 字符串
* `@ingore` 用于在文档中忽略指定的关键字
    * 参数类型: 字符串
* `@license` 设定源代码遵循的代码发布协议
    * 参数类型: 字符串, 相当于html标签中的`<a>`, 首先是URL, 接着是要显示的内容
    * 例如: `<a href="http://www.baidu.com">百度</a>`, 可以写作 `@license http://www.baidu.com 百度`
* `@link` 类似于license 但还可以通过link指到文档中的任何一个关键字
    * 参数类型: 字符串
* `@name` 为关键字指定一个别名。
* `@static` 指明关建字是静态的。
* `@deprecated` 指明不用或者废弃的关键字
    * 使用范围: class, function, var, define, module, constent, global, include
* `@final` 指明关键字是一个最终的类、方法、属性，禁止派生、修改。
    * 使用范围: class, function, var
* `@package` 代码包组织定义 用于逻辑上将一个或几个关键字分到一组。
    * 使用范围: 页面级别的-> define, function, include
    类级别的->class, var, methods
    用于逻辑上将一个或几个关键字分到一组。
* `@abstrcut` 说明当前类是一个抽象类
* `@param` 指明一个函数的参数
    * 使用范围: function
    * 参数类型: 字符串
    * 格式: `@param 参数类型 参数变量名称(形参) 参数说明文本`
* `@return` 指明一个方法或函数的返回值类型
    * 使用范围: function
    * 参数类型: 字符串
    * 格式: `@return 返回值类型`
* `@var` 指明变量类型
    * 参数类型: 字符串
* `@version` 指明版本信息
    * 参数类型: 字符串
* `@todo` 指明应该改进或没有实现的地方
    * 举例: `@todo: 待改进或需实现的功能说明文本`
* `@throws` 指明此函数可能抛出的错误异常,极其发生的情况

上面提到过, 普通的文档标记标记必须在每行的开头以@标记, 除此之外, 还有一种标记叫做inline tag,用{@}表示, 具体包括以下几种:

* `{@link}` 用法同@link
* `{@source}` 显示一段函数或方法的内容
