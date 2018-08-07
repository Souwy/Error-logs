# error_missing_bracket_after_argument_list

This is the error message:
```js
SyntaxError: missing ) after argument list
```

This is the code that triggered it on PythonTutor (so V8) (on the two console.log's):
```js
let input = "a string";
let expected = "see";
let output;

console.log("Output should be a string "see"");

"a string".charAt(2) + "ee"

{ //  ("a string") -> ("see")
     const step_1 = "a string".charAt(2); 
     // str: "s"
     const step_2 = step_1 + "ee"; 
     // str: "see"
     output = step_2;
};

console.log(expected" should be equal to " output);
```
This is the fixed version, which fixes two separate problems:
```js
let input = "a string";
let expected = "see";
let output;

console.log("output should be a string \"see\"");

"a string".charAt(2) + "ee"

{ //  ("a string") -> ("see")
     const step_1 = "a string".charAt(2); 
     // str: "s"
     const step_2 = step_1 + "ee"; 
     // str: "see"
     output = step_2;
};

console.log("expected should be equal to output");
```

The first issue was with the escape character. 
The second was because I wanted to include the actual variables `expected` and `output` with a string between them, but I didn't use the proper syntax. My 'fix' just abandoned that idea, but it would be good to know how to do that. 

Here is the fully fixed version which does what I originally wanted the second console.log to do:
```js
let input = "a string";
let expected = "see";
let output;

console.log("output should be a string \"see\"");

"a string".charAt(2) + "ee"

{ //  ("a string") -> ("see")
     const step_1 = "a string".charAt(2); 
     // str: "s"
     const step_2 = step_1 + "ee"; 
     // str: "see"
     output = step_2;
};

console.log("if " + expected + " equals " + output + " then all is well.");
```
The issue was that I needed to use `+` between the various parts.
