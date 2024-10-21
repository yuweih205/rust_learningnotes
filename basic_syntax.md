* isize和usize在不同平台有所区别

* 单位类型 () 空白类型 表示返回空 即不返回任何值

* 数组和元组 

  * 数组必须同类型  let a：[1,2,3]  数组这样可以计算很快 放在**栈上**空间 自动推导大小和长度 在栈上分配的已知固定大小的单个内存块  不能插入删除（固定空间）
  * 元组  tuple   let v:(1,a,3.4)

* 函数采取snake_case规范风格

* const要用upper_case

* ```rust
  if {} else {}
  ```

* ```rust
  let number = if condition {5} else {6}  //函数式编程 表达式语法  Rust 是一种强调表达式的语言，几乎所有的东西都是表达式。
  ```

* ```rust
  loop{ } 
  //会一直循环 直到看到break     
  let mut counter =0;
  let result = loop{ counter + = 1;
    if count ==10{
      break couter*2 }};
  //赋值了
  #循环标签 
  ‘q：loop{
    loop{
      break 'q;
    }
  }//跳出最外层循环 只能在循环里写标签
  ```

* ```
  let b = [1,2,3,4]
  for a in b{
  }
  for a in 1..=10{}//从一到十
  ```

* ```
  while condition {
  }
  ```

* ```rust
  //所有权
  值在任何时候有且只有一个所有者 当所有者离开作用域 值被丢弃
  {
    a
  } 括号外无法访问a的值
  //？？ 不清楚底层是怎么实现的
  let x =123;
  let y = x;//x将被丢弃 
  为了简便 此时会发生x的值复制 复制给y 自动复制 此时x其实不会被丢弃 即所有权不会被转移 但对于较复杂的类型就会先前变量被丢弃 但如果后者先消亡 先前变量在后者消亡周期内依旧持有该值 即所有权转移
  //函数参数
  trait(copy,clone) 复制就不会夺走前面的所有权
  即对于简单类型的数据 rust对于’=‘已经实现了复制 而复杂数据没有 ’=‘会转移所有权
  ```

* 如果定义一个同名变量 第一个变量会被第二个变量隐藏 （shadowing）

* ```rust
  to_string 
  String
  &str
  ```

  
