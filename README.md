With classes we can create constructor function and the prototype in once:

class Hero {
  constructor(name, level, weapon) {
    this.name = name;
    this.level = level;
    this.weapon = weapon;
  }
  sayHello(){
    return `Hello. My name is ${this.name} and I have a ${this.weapon} to fight!`;
  }
}

const wonder = new Hero("Wonder Woman", 2, "lasso");
const thor = new Hero("Thor", 1, "hammer");

console.log(wonder.sayHello());
console.log(thor.sayHello());


//Hello. My name is Wonder Woman and I have a lasso to fight!
//Hello. My name is Thor and I have a hammer to fight! 
