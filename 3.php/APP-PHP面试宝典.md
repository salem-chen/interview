## 来源 app PHP面试宝典
###一.Yahoo PHP面试题
1.以下哪一句不会把John 新增到users 数组?

    a. $users[] = 'jonhn';
    b.array_add($users,'john);
    c.array_push($users,'john);
    d.$users ||= 'john';
    
    答案： a,c 正确，b没有array_add()这个方法，d语法错误
2. sort(),assort(),ksort()有什么分别?他们在什么情况下使用?
    
    答案：sort() 是根据数组的值做自然排序,索引的值得不到保留
         ksort() 根据数组的键做自然排序
         assort() 没有这个函数 和sort一样，但是索引的值得到保留
        
3. 以下代码会产生什么效果？为什么?

    $num = 10;
    function multiply(){
        $num = $num * 10;
    }
    multiply();
    echo $num;
    
    答案：报错 PHP Notice级别错误，函数multiply里面的局部变量$num没有声明赋值,
        但也能输出$num变量值为10，因为$num是全局变量，函数内部是局部变量修改
        
 4.一个引用变量和一个常规变量有什么分别，什么情况下用引用变量.

    答案：引用变量传的是变量的引用地址而不是变量的值，常规变量传的是值，在函数中改变引用变量的值时候会改变这个变量的值
 
 5.哪一些函数可以用来插入函数库？
    
    答案：include,inluce_once,require,require_once,com_load,dotnet_load
    
###二.6道php面试题
  1.不用新变量直接交换现有的两个变量的值.(考PHP基本功)
    
    答案：list($a,$b) = [$b,$a];
  2.PHP数字金额转大小写格式，同时说明思路（靠数组掌握）
  3.SQL 查询语句如下：
  
    select * from tableName where (id = 10) or (id = 32) or (id = 22) or (id = 76) or (id = 13) or (id = 44)
    让结果按10,32,22,76,13,14的顺序检索出来，请问如何书写？（SQL能力）
  4.简单写一个上传文件程序，要求同时上传文件数量可以认为控制（逻辑能力）
  5.php 同时调用3个数据库中的一个表的信息（假设A.a.aid = B.b.bid = C.c.cid） 请说明思路以及书写部分代码.
  6.现有一IM软件，使用id email作为注册条件，假设已注册1040人，有一zh_cn论坛注册200人，有一en_us论坛，已注册150人
    要求：将三者同步，使用统一的注册流程，写出设计思路

###三.10条PHP编程习惯帮你找工作
   1.使用单引号和双引号字符串的区别
    
     答案：当使用双引号时，PHP解析器会对其进行变量替换，转义扽操作，如果只是输出一些基本字符，使用单引号会快些。
   
   2.以下哪一条语句运行速度最快？
    
    a. print "Hi my name is $a. I am $b";
    b. echo "Hi my name is $a.I am $b";
    c. echo "Hi my name is ".$a." I am ".$b;
    d. echo 'Hi my name is ',$a,.'.I am ',$b;
    
    答案：d .print 是函数 而echo是语句，语句比函数要快，因为没有返回值。另外单引号比双引号要快，echo 使用逗号间隔输出，比.连接符要快
    
   1.字符串使用单引号比双引号要快。
   2.不要使用开始标识符缩写形式 <? 使用<?php
   3.尽量不要使用正则表达式
   4.尽量不要在循环中声明变量，和没循环一次调用一次sql查询
   5.不要使用register_global 和magic_quotes
   6.变量最好提前声明和初始化
   7.对代码进行注释
   8.遵循一个编程规范 代码的缩进换行注释等和团队保持一个规范

###四.如何使用PHP实现邮件发送？
###五.据说是腾讯PHP面试题
   1.请对POSIX 风格和兼容Perl风格两种正则表达式的主要函数进行类比说明
    
      ereg_preg_match
      ereg_replace preg_replace
      
   2.请说明在php.ini 中safe_mode 开启之后对PHP系统函数的影响
   
   3.PHP5中魔术方法函数有哪几个,请举例说明各自的用法
    
    __sleep
    __wakeup
    __toString
    __set_state
    __construct
    __destruct
    __call,
    __get,
    __set,
    __isset,
    __unset,
    __set_state,
    __clone,
    __autoload
   
   4.请写出，如何在命令行运行PHP脚本（写出两种形式），同时向脚本传递参数。
   5.PHP的垃圾回收机制是怎样的？
   6.使对象可以像数组一样进行foreach循环，要求属性必须是私有的。
        
     Iterator 模式的PHP5实现，写一个类实现Iterator接口.
     
   7.请写一段PHP代码，确保多个进程同时成功写入同一个文件。
   8.用PHP实现一个双向队列
   9.使用正则表达式提取一段标志语言（html或xml）代码段中指定的标签的指定的属性值。
   10.请使用socket 相关函数（非curl）实现如下功能:构造一个post请求，发送到指定http server 的指定端口的指定路径。
        而且该http server 需要用cookies来进行简单的用户动作跟踪。
   11.你用什么方法检查PHP脚本的执行效率（通常是PHP执行时间和内存消耗）和数据库sql的效率，并定位和分析脚本执行和数据库查询的瓶颈所在？
        
        1.脚本执行时间，启用xdebug,使用WinCacheGrind分析
        2.数据库查询,mysql使用explain分析查询，启用slow query log记录慢查询
   12.下面输出什么？
       
       <?php
        echo count("123");
       ?>
       a.3 b.false c.null d.1 e.0
   13.下面打印42保留两位小数点的是？
    
    a.printf("%.2d",42)
    b.printf("%1.2f",42)
    c.printf("%.2u",42)
    答案：b
   14.$text = 'Content-Type:text/xml';
    下面哪个打印出 'text/xml'?
    
    a.print substr($text,strchr($text,":"));
    b.print substr($text,strchr($text,":")+1);
    c.print substr($text,strpos($text,":")+1);
    d.print substr($text,strpos($text,":")+2);
    e.print substr($text,0,strchr($text,":"));
        答案：c
        
   15.$a = in_array('01',['1']) == var_dump('01' == 1) $a是多少？
    
        a.true
        b.false
        答案：a
   16.下面输出什么？
    
        setcookie('a','value');
        echo $_COOKIE['a'];
   17.用js实现trim函数
   18.下面输出什么？
        
        <script type='1.js'>alert(0)</script>
   
   
   
   