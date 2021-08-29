# JS数据类型
   * JS中，数字是用64位浮点数的形式存储的
   * JS中，字符是用类似UTF-8形式存储的
   * 字符串能表示电话号码，数字不行

## JS中的数据类型
   1. 数字（number）、字符串（String）、布尔（Boolean）、符号（symbol）、空（undefined）、空（null）和对象（object）
   2. 数组，函数和日期都是对象，不是数据类型。

## 数字（64位浮点数）
   * 常用：整数：1，小数：0.1，科学记数法：1.23e4
   * +0/-0都等于0； 1/+0 infinity(无穷大)；1/-0 -infinity。
   * 无法表示的数字（NaN）,例：NaN=0/0,但NaN也是一个数字；由于NaN所代表的值是不确定的，所以NaN!=NaN。
   * JS数字的存储形式：
        1. 符号占1位，指数占11位（-1023~1024），有效数字占52位（省掉第一个1）
        2. 例：0.625=0.5+0.125=0.101=1.01*2的负1次方，0|-1|01
        3. 范围：指数拉满，有效数字全是1，Number.MAX_VALUE:1.79769...e+308;指数负方向拉满，有效数字最小1，得到最小值，
           Number.MIN_VALUE:5e-324
        4. 精度（有效数字）：最多只能到52+1个二进制位表示有效数字；2^53对应的十进制是9后面15个0，15位有效数字能精确表示，
           16位如果小于90开头，也能精确表示

## 字符串（String）
   * 转义字符：\;例：\'表示'，\n表示换行，\r表示回车，\t表示tab制表符，\\表示\，\uFFFF表示对应的Unicode字符，\xFF表示前
     256个Unicode字符。
   * 字符串的属性：长度：'123'.length //3，'\n\t\r'.length //3，''.length //0，' '.length //1
   * base 64转码：window.atob('邮箱');//隐藏简历邮箱
## 布尔 Boolean
   * 1==2 //false ，1<=2 //true
   * 五个falsy值：相当于false但又不是false的值，分别是：undefined、null、0、NaN、''
## undefined与null的区别
   1. 没有本质区别
   2. 如果一个变量声明了，但没赋值，那么默认值是undefined，而不是null
   3. 如果一个函数，没有写return，默认return undefined，而不是null
   4. 习惯上，非对象的空值写为undefined，对象的空值写为null
## 声明变量
   * 有三种声明方式：var a=1,let a=1,const a=1
   * var是过时的，不好用的；let是新的，更合理的（变量声明）；const是声明时必须赋值，且不能再改的方式（常量声明）
## let声明
   1. 规则：遵循块作用域，即作用范围不能超过{}
   2. 不能重复声明，例：let a=1;let a=2;//error
   3. 可以赋值也可以不赋值
   4. 必须先声明再使用，否则报错
   5. 全局声明的let变量，不会变成window的属性
## const声明
   * 规则：跟let几乎一样，只有一条不一样：声明时就要赋值，赋值后不能改
## 类型转换
   * number=>String: var n=1 String(n) //"1",n+'' //"1"
   * String=>number: var s="123" Number(s) //123,s-0 //123,+s //123,ParseInt('123') //123
   * x=>boolean: Boolean(1) //true, Boolean(0) //false, !!0 //0, !!1 //1
   * x=>string: true.toString() //"true", 1.toString() //error, (1).toString() //"1", 1..toString() //"1",
     1 .toString() //"1"
     