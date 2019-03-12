# demo
## new Date()相关获取当月天数和当月第一天
var  myDate = new Date();

### 获取本月第一天周几
var monthFirst = new Date(myDate.getFullYear(), parseInt(myDate.getMonth()), 1).getDay(); </br>
### 获取本月天数(获取后一个月的0日即前一月的最后一日)
var totalDay=(new Date(myDate.getFullYear(), parseInt(myDate.getMonth() + 1), 0)).getDate();</br>

## 关于继承
  ### 构造函数的继承

  // function Parent1(){
  //     this.name='parent',
  //     this.arr=[1,2,3];

  // }
  // Parent1.prototype.say=function(){console.log('hello world')}
  // function Child1(){
  //   Parent1.call(this);
  //   this.age=10;
  //   this.name='child'
  // }
  // var objc1=new Child1();
  // var objp1=new Parent1();
  // console.log(objp1)
  // console.log(objc1)
  // objc1.say(); //报错  
  //构造函数继承是部分继承 父级原型没有继承
  // -----------------------------------------------------------------------------
  ### 原型继承
  // function Parent1(){
  //     this.name='parent',
  //     this.arr=[1,2,3];

  // }
  // Parent1.prototype.say=function(){console.log('hello world')}
  // function Child1(){
  //   // Parent1.call(this);
  //   this.age=10;
  //   this.name='child'
  // }
  // Child1.prototype=new Parent1();  //就是把子级 的原型 指向父级的实例；缺点就是当 一个child实例修改 父级属性的时候相当于更改了原型
  // var objc1=new Child1();
  // var objp1=new Parent1();
  // console.log(objp1)
  // console.log(objc1.constructor) //造成实例的 构造函数是 Parent1;
  // objc1.say(); 
  //-----------------------------------------------------------------------------------
  ### 组合继承
  // function Parent1(){
  // this.name='parent',
  // this.arr=[1,2,3];

  // }
  // Parent1.prototype.say=function(){console.log('hello world')}
  // function Child1(){
  //   Parent1.call(this);
  //   this.age=10;
  //   this.name='child'
  // }
  // // Child1.prototype=Parent1.prototype;  //缺点还是无法判断构造函数
  // //优化代码为 ：
  // Child1.prototype= new Object(Parent1.prototype); //Object.create()也可以
  // Child1.prototype.constructor=Child1;
  // var objc1=new Child1();
  // var objp1=new Parent1();
  // console.log(objc1) 
  // console.log(objp1.constructor)
  // objc1.say(); 
  ### es6 继承

  class Parent {
    constructor(name) {
      this.name = name;
    }
    say() {
      console.log(this.name)
    }
  }
  let parent = new Parent('kaka');
  parent.say();

  class Child extends Parent {
    constructor(props) {
      super(props)
    }
    fn() {
      console.log(super.constructor)
    }
  }
  let child = new Child('yiyi');
  child.fn()
