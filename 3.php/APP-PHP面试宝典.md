## 来源 app PHP面试宝典
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
    