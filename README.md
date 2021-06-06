With classes we can create constructor function and the prototype in once:

# class Hero {
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

# ----------------------------------------------------------------------------------

# class Enemy{
	constructor(name, level, emoji, attackName){
		this.name = name;
		this.level = level;
		this.emoji = emoji;
		this.attackName = attackName;
		this.enemy = true;
	}
	attack(){
		return `${this.name} ${this.attackName} you!`
	}
}

const spider = new Enemy("spider", 1, "🕷", "bites");
const bear = new Enemy("bear", 20, "🐻", "scratches");
const sname = new Enemy("snake", 6, "🐍", "bites");

console.log(spider.attack());

# ----------------------------------------------------------------------------------

# class Enemy and class Hero share some properties (level and name). To make code clean, we can avoid repeating those properties in both classes creating a big class called Character. Then we will use the class Character in class Enemy and Hero using the keyword extends:

class Character{
	constructor(name, level){
		this.name = name;
		this.level = level;
	}
}

class Enemy extends Character{
	constructor(name, level, emoji, attackName){
		super(name, level);
		this.emoji = emoji;
		this.attackName =  attackName;  
		this.enemy = true;
	}
	attack(){
		return `${this.name} ${this.attackName} you!`;
	}
}

const spider = new Enemy("spider", 1, "🕷", "bites");
console.log(spider.name);


class Hero extends Character{
  constructor(name, level, weapon){
    super(name, level);
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
