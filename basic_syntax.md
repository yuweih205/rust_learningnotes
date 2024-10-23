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

* 可变引用不能有多个 不可变可以  读写冲突 

* ```rust
  let a:&str = 'adasd';
  let b =String::from("hello world!")
  let c:&mut String= &mut b;//可变引用只有一个
  let d:&String =&b;//这个时候也不能借用 也就是可变不可变不能同时存在
  ```

* ```rust
  String
  &str
  String 是堆分配的、可变的，拥有数据的所有权。它适用于动态操作字符串的场景。
  str 是一种字符串的不可变切片，通常通过引用使用（&str），并且是静态或常量数据的引用。
  ？？？还没有理解
  ```
  
* 结构体很正常 可以用元组当结构体

  ```rust
  struct a(1,ad,3.2);
  //虽然不知道有什么用
  即便两个结构体AB类型一致  传参A也会报错 除非别名
  ```

*  ```
   //可变数组
   let mut v：Vec::new();
   let v =vec![1,2,3];//使用vec！宏
   push pop
   ```

* ```rust
  let mut a =HashMap::new();
  insert
  let b=a.get(&key).copied().unwrap_or(0);//copied将T复制一份  unwrap_or(0)用来提供默认值 如果是none就提供默认值
  ```

* 枚举类型
  
  ```rust
  enum Color{
    Red(i32);Green(String);Blue(f32);
  }//能放任何类型 不过实例成员就要加类型
  let a =Color::Red(i32);
  let b = Color::Green("hello worls".to_string());
  ```
  
  * Rust 中不推荐使用空指针  推荐使用Optional  用这个枚举来实现是否存在 用来代替空指针
  
  ```rust
  let player:Option<T:32>
  player = Some(10); //必须使用Some
  player = None;
  if let Some(a) = player{}else{};
  ```
  
  * 类似的还有
  
  ```rust
  Ok(result)//表示结果
  Err(error)
  Result<T: , E:>//成功了 没成功的类型
  
  fn a(num:i32)->Result<T:i32,E:String>{
    OK(s);
  }
  fn main(){
    let result = a(0);
    if let Ok(value)=result {};//取出Ok的值并拿出value  ？？？？？
  }
  ```
  
* 模式匹配  match

  ```rust
  enum Color{
    Red(i32);Green(String);Blue(f32);
  }
  fn color(color:Color) -> u8{
    match color{
      Color::Red(_)=>1,
      Color::Green(_)=>2,
      Color::Blue(value)=>{
        if let value =1.0 
        { }
        else{}
      }
    }
  }
  
  //
  fn main() {
      let age = 25;
      match age {
          0..=18 => println!("Underage"),
          19..=65 => println!("Adult"),
          _ => println!("Senior"),
      }
  }
  //_ 通配符
  //
  fn main() {
      let pair = (0, -2);
      match pair {
          (0, y) => println!("First is zero, y is {}", y),
          (x, 0) => println!("x is {}, second is zero", x),
          _ => println!("Neither are zero"),
      }
  }
  //如果第一个值是0  匹配成功 并将第二个值绑到y上 ？？？？
  //不理解怎么实现的
  ```

* 语法糖是什么？

* 闭包 解包 打包

* ```rust
  //collect 格式转换 但是只能转换
  //待补充 不是很懂
  ```

* 



