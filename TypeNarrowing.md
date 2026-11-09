#Type Narrowing#

In typescript we can write type with union for example like number|string. Or in casy of unknown we cant know the type. But with the help of type narrowing we can find out the type.

An example of typeof can be found in our 2nd question of the coding assingment.
-------------------------------------------------------------------
function processInput(value:string|number|boolean):string|number{
  if (typeof value==="string"){
    return value.trim().toLowerCase()
  }
  else if(typeof value=="number"){
    return value*10
  }
  else{
    return value? "Active" : "Inactive"
  }
}
-------------------------------------------------------------------
Here value can be string,number or boolean. but we are not sure becauuse it can be only one. But with the help of typeof we can be sure if its a string,number or a boolean.


On the otherhand instance is very helpful in classes. instance of helps us finding in which class a object belongs to. for example
-------------------------------------------------------------------
class student{
  constructor(public name:string,public grade:number){}
}

class teacher{
  constructor(public name:string,public subject:string){}
}

function intro(person:student|teacher):string{
  if (person instanceof sttudent){
    return `${person.name} studies in ${person.grade}`
  }
  else{
    return `${person.name} teaches in ${person.subject}`
  }
}
---------------------------------------------------------------------
Without instanaceof it is not possible to know if teacher or student.we had to write multiple functions which is not feasable.but the help of instanceof we can easily identify in which class the object belongs to.


Finally the in operator check if a property exists in an object. We use in for plain objects and interfaces. The reason is interfaces dont exist in runtime. Becuase of this instanceof cant check them and we have to use the in operator.
---------------------------------------------------------------------
interface course{
  title:string;
  students:number;
}

interface prodcut{
  name:string;
  price:number;
}

function ItemInfo(item:course|product):string{
  if ("students" in item){
    return `${item.title} has ${item.students} students`
  }
  return `${item.name} costs {item.price} taka`
}
---------------------------------------------------------------------
In the code above inside the if typescript knows that item is a course because only course have student and after the if typescript knows it must be a product because there are not any more interfaces.


So in conclusion it can be said that operators like typeof,instanceof and in allow to check type and properties.So there are less chance for type releated erros and easier to maintain by decreasing the amount of type related errors.
