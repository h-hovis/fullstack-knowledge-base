
    TypeScript Fundamentals

    What is it?

    TypeScript is a “superset” to JavaScript. It extends JS and adds more features to the JS syntax. It adds static typing to JS.

    Why is it useful?

    Static typing can enhance you code and prevent errors.

    Basic types of TypeScript:

    Primitives: string, number, boolean (these are the core primitive value types)
    Complex: arrays, objects
    Function types and parameters

    Primitive:

    Add a colon after your variable to specify what value should be stored in the variable:
    Ex: 
    let age: number;
    age is your variable and you want a number value
    OR: 
    let userName: string;
    userName is your variable and you want the value to be a string

    Complex:

    If you want an array of strings, put square brackets after the value:
    Ex: 
    let hobbies: string[];

    If you want your variable to store an object:
    Ex: 
    let person: {}; - insert your values between the curly braces
    let person: {
    name: string;
    age: number;
    };

    If you want to have both, add the square brackets after the curly braces:
    Ex:

        let person: {
        name: string;
        age: number;
        } [] ;

    Type Inference

    By default, typescript tries to infer as many types as possible.
    So if you say:

    let course = ‘React - The Complete Guide’;

    TypeScript infers that this variable (course) has a string type, so if you tried to pass a number later in your code, you would get an error:

    Ex: 
    let course = 1234; - would not work
    With this, you wouldn’t need to go the extra step of assigning the type with the colon, type inference has already done it for you.

    Union Types

    Allows more than one type to be assigned to the variable. You do this by adding a pipe symbol ( | ) between your types:
    Ex: 
    let course: string | number;
    You can have as many types as you want assigned to the variable as long as you have the pipe symbol between each type.

    Type Aliases

    This is used to avoid type duplication. Use the type keyword:
    Ex: 
    type Person = {
    name: string;
    age: number;
    };
    Then you can use your Person alias later on in your code instead of assigning the object type again:
    Ex: 
    let person: Person;
    OR: 
    let people: Person[];
    This saves a lot of typing work and makes your code more concise and easier to maintain.

    Functions and types

    You can set types for parameters in your function:
    Ex:
    function add(a: number, b: number) {
    return a + b;
    }
    Type inference makes the return value a number because of the types set in the parameters.

    Generics

    With a Generics feature, we can convert a function to a generic function using <>. In here, we can define a generic type which will only be available inside this function. Typically that’s called T for type, but any identifier of your choice is okay.

    Example:
    function insertAtBeginning<T>(array: T[], value: T) {};

    Because of the generic type feature, we’re telling TypeScript that the type is actually not any type, it’s not any kind of value. Instead, we tell it that the type of this array and of this value should be the same, just that there is an array, but it’s an array full of the same types of values as this single value has.

    Classes

    class Student {
    firstName: string;
    lastName: string;
    age: number;
    courses: string[];

    constructor(first: string, last: string, age: number, courses: string[]) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.courses = courses;
     }
    }
    const student = new Student(‘Heather’, ‘Slape’, 37, [Angular]);

    You can also add a method to a class:

    enrol(courseName: string) {
    this.courses.push(courseName);
    }

    ^^^This would go inside of the class from the previous ex.

    With TypeScript you can determine whether a property is public (can be accessed outside of the class) or private (can only be accessed within the class). Add public or private before the property - private courses.

    Interfaces

    In their most basic form, interfaces are really just object type definitions. Use the interface keyword

    interface Human {
    firstName: string;
    age: number;
    greet: () => void;
    }
    let max: Human;
    max = {
    firstName: ‘Max’,
    age: 32,
    greet () {
    console.log(‘Hello!’);
     };
    };

    Interfaces can be implemented by classes and when they are, they force classes to have that structure defined by the interface.
    For example: to ensure that a new class in the code implements the interface Human, you write it like this:

    class Instructor implements Human {};

    This ensures that the new class Instructor will have all the values from the Human interface from before: firstName: string, age: number, etc.
    If it’s not coded with the same values, you will get an error.

    Configuring the TypeScript Compiler

    In your file, in VS code, go to the terminal & run:
       ~ # npx tsc (your file name here) - this is for a specific file

        To configure all of your files:
       ~ # npx tsc --init
        This adds a tsconfig.json file

    You can then configure the typescript and adjust some of the settings, if you’d like, although you probably won’t need to.

