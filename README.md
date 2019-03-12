# demo
## new Date()相关获取当月天数和当月第一天
var  myDate = new Date();

### 获取本月第一天周几
var monthFirst = new Date(myDate.getFullYear(), parseInt(myDate.getMonth()), 1).getDay(); </br>
### 获取本月天数(获取后一个月的0日即前一月的最后一日)
var totalDay=(new Date(myDate.getFullYear(), parseInt(myDate.getMonth() + 1), 0)).getDate();</br>

## 关于继承
  ### 构造函数的继承

  // function Parent1(){</br>
  //     this.name='parent',</br>
  //     this.arr=[1,2,3];</br>

  // }
  // Parent1.prototype.say=function(){console.log('hello world')}</br>
  // function Child1(){</br>
  //   Parent1.call(this);</br>
  //   this.age=10;</br>
  //   this.name='child'</br>
  // }
  // var objc1=new Child1();</br>
  // var objp1=new Parent1();</br>
  // console.log(objp1)</br>
  // console.log(objc1)</br>
  // objc1.say(); //报错  </br>
  //构造函数继承是部分继承 父级原型没有继承</br>
  // -----------------------------------------------------------------------------</br>
  ### 原型继承
  // function Parent1(){</br>
  //     this.name='parent',</br>
  //     this.arr=[1,2,3];</br>

  // }</br>
  // Parent1.prototype.say=function(){console.log('hello world')}</br>
  // function Child1(){</br>
  //   // Parent1.call(this);</br>
  //   this.age=10;</br>
  //   this.name='child'</br>
  // }</br>
  // Child1.prototype=new Parent1();  //就是把子级 的原型 指向父级的实例；缺点就是当 一个child实例修改 父级属性的时候相当于更改了原型</br>
  // var objc1=new Child1();</br>
  // var objp1=new Parent1();</br>
  // console.log(objp1)</br>
  // console.log(objc1.constructor) //造成实例的 构造函数是 Parent1;</br>
  // objc1.say(); </br>
  //-----------------------------------------------------------------------------------</br>
  ### 组合继承
  // function Parent1(){</br>
  // this.name='parent',</br>
  // this.arr=[1,2,3];</br>

  // }</br>
  // Parent1.prototype.say=function(){console.log('hello world')}</br>
  // function Child1(){</br>
  //   Parent1.call(this);</br>
  //   this.age=10;</br>
  //   this.name='child'</br>
  // }
  // // Child1.prototype=Parent1.prototype;  //缺点还是无法判断构造函数</br>
  // //优化代码为 ：
  // Child1.prototype= new Object(Parent1.prototype); //Object.create()也可以</br>
  // Child1.prototype.constructor=Child1;</br>
  // var objc1=new Child1();</br>
  // var objp1=new Parent1();</br>
  // console.log(objc1) </br>
  // console.log(objp1.constructor)</br>
  // objc1.say(); </br>
  ### es6 继承

  class Parent {</br>
    constructor(name) {</br>
      this.name = name;</br>
    }</br>
    say() {</br>
      console.log(this.name)</br>
    }</br>
  }</br>
  let parent = new Parent('kaka');</br>
  parent.say();</br>

  class Child extends Parent {</br>
    constructor(props) {</br>
      super(props)</br>
    }</br>
    fn() {</br>
      console.log(super.constructor)</br>
    }</br>
  }</br>
  let child = new Child('yiyi');</br>
  child.fn()</br>
