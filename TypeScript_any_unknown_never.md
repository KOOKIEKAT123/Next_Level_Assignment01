#How TypeScript hierchy work with any,unknown and never#

In Typescript type hierchy both unknown and any sits at the top. In both unknown and any type all type can be used. difference is with any type there is no type checking and unknown type have strict type checking. More details about them are written in the paragraph below. On the other hand never sits at the bottom of the type hierchy. In the never type we cannot assign anything.


With any type we can use any type of value.it can be number,string,boolean anything. With any type we are turning off type check. One of the main reason for using typescript over javascipt is typechecking so we dont get any  error down the line. For example if we write
------------------
let var:any=10;
var=undefined;
var.foo();
-------------------
it wont show any errors. So it is highly not recomened to use any type. We can only consider to use it if there are dynamic values if value type keeps changing in that case we can consider it. On the other hand unknown is kind of like an alternative to any type. With unknown type we can just write unknown we dont need to enforce string,number. But with unknown even if with unknown we dont need to give any type at first. But without giving any type it will throw us a error and we cant do any kind of operations. We mainly use if we are not sure what type will it be. Later we can use typeof to find the type. So unknown is typesafe.  Thats why unknown is always preferred over any.
