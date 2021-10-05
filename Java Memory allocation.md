# Array Memory Allocation
>[数组内存 Link](https://www.cnblogs.com/rookiemzl/p/10547089.html)
- a a
> ### A. 基本内存分配概念图解

![PIC](https://i.imgur.com/2ggv69i.png)

> ### G. 对象数组的内存图

![PIC1](https://img2018.cnblogs.com/blog/1269192/201903/1269192-20190319224041670-1907201387.png)
```html
- 首先方法区会有 Student.class(里面有成员变量、构造方法、成员方法)、StudentDemo.class(里面有 main函数)。main 方法执行，
  栈中开辟空间创建 Student[ ] students，堆内存中会 new Student[3] ,默认值都是 null,通过地址值001 指向栈。
- 然后创建学生对象 Student s1,同样通过地址值002指向堆内存为002的对象，而对象的方法(包括构造方法和成员方法)也有
  地址值 0001，堆内存通过地址值 0001 指向 方法区对象的方法 0001，进行赋值覆盖。

  (Student s2,Student s3同理。此时创建完对象并赋值完成时，这3个对象还和 students 数组没有关联。)

- 最后把学生对象作为元素赋值给学生数组：students[0]=s1,其实就是拿着 s1 的地址值 002 指向数组的第一个元素，数组
  中的 null 就被 002替代。students[1]=s2；students[2]=s；同理可得！！

赋值完毕后，进行遍历操作时，如果使用 System.out.println(s); 打印出来的是地址值001、002、003。
  ```
