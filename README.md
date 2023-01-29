# Getters-and-setters

class MyClass {
 constructor() {
 this.names_ = [];
 }
 set name(value) {
 this.names_.push(value);
 }
 get name() {
 return this.names_[this.names_.length - 1];
 }
}
const myClassInstance = new MyClass();
myClassInstance.name = 'Joe';
myClassInstance.name = 'Bob';
console.log(myClassInstance.name); // logs: "Bob"
console.log(myClassInstance.names_); // logs: ["Joe", "Bob"]
If you only define a setter, attempting to access the property will always return undefined.
const classInstance = new class {
 set prop(value) {
 console.log('setting', value);
 }
};
classInstance.prop = 10; // logs: "setting", 10
console.log(classInstance.prop); // logs: undefined
If you only define a getter, attempting to assign the property will have no effect.
const classInstance = new class {
 get prop() {
 return 5;
 }
};
classInstance.prop = 10;
console.log(classInstance.prop); // logs: 5
