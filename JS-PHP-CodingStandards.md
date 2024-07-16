# Research on Coding Standards for PHP and JavaScript 

## Introduction 
JavaScript and PHP are two of the most widely used programming languages in web development. This report explores and compares the best practices, style guides, and common conventions in JavaScript and PHP coding.

### JavaScript 
It is a scripting or programming language used to implement complex features on web pages. It is the third layer of the standard web technologies after HTML, which is a markup language used to structure web content, and CSS, a language of style rules used to apply styling to HTML content. JavaScript allows you to create dynamically updating content, animate images, and implement many other amazing features.

### PHP 
It is a self-referentially acronym for "PHP: Hypertext Preprocessor". Original it supposedly meant personal home page. It is powerful enough to serve as the core of the largest blogging system on the web (WordPress), robust enough to support large social networks, and simple enough to be a beginner's first server-side language.

## JavaScript Coding Standards 

### Best Practices 
1. **Avoid Global Variables** : Minimize the use of global variables, including all data types, objects, and functions.
2. **Always Declare Local Variables**: Local variables should be declared using var, let, or const; otherwise, they will default to global variables.
3. **Declarations on Top**: Best practice dictates placing all declarations at the top of each script or function. This approach promotes cleaner code, provides a single location to locate local variables, helps prevent unintended global variables and reduces the risk of accidental redeclarations.
4. **Initialize Variables**: It is a good coding practice to initialize variables when you declare them. This will promote cleaner code and avoid undefined values. 
5. **Declare Objects with const**: Declaring objects with const ensures that their type cannot be accidentally changed.
   
### Style Guides 
- **Airbnb JavaScript Style Guide**: One of the most popular JavaScript style guides.
- **Google JavaScript Style Guide**: A comprehensive style guide by Google.
- **StandardJS**: A JavaScript style guide, linter, and formatter.

### Common Conventions
 - **Indentation**: Always try to indent your code using two spaces and it must not end with trailing whitespaces. 
 - **Spaces and Brackets**: Ensure consistent use of blank spaces in keywords. Keywords followed by '(' or ')' should be surrounded by spaces, while keywords like 'function' and 'typeof' should be followed by a space for clarity and readability.
 - **Camel Casing for Identifier Names**: It is mostly used for identifiers. In camelCase, the first letter of each identifier should be lowercase, with subsequent words starting with a capital letter.

### Examples 
#### Good Practice


```javascript
// Declaration and Initialization
function calculateArea(radius) {
    const pi = 3.14; // Initialized constant variable
    let area; // Declared local variable

    // Calculate area
    area = pi * radius * radius;

    return area;
}

console.log(calculateArea(5)); // Output: 78.5

// Using const for Immutable Objects
const person = {
    name: 'John',
    age: 30
};

person.age = 31; // Modifying property of const object is allowed
console.log(person); // Output: { name: 'John', age: 31 }

// CamelCase for Identifier Names
function calculateRectangleArea(length, width) {
    let rectangleArea = length * width;
    return rectangleArea;
}
```

#### Bad Practice 

```javascript
// Using Global Variables
let result; // Global variable

function calculateArea(radius) {
    pi = 3.14; // Global variable (undeclared)
    result = pi * radius * radius; // Modifying global variable
}

calculateArea(5);
console.log(result); // Output: 78.5

// Missing Variable Declaration
function calculateArea(radius) {
    area = 3.14 * radius * radius; // Implicit global variable declaration
    return area;
}

console.log(calculateArea(5)); // Output: 78.5
console.log(area); // Output: 78.5 (unexpected global variable)

// Improper Use of Naming Conventions
function Calculate_Rectangle_Area(length, Width) {
    let rectangleArea = length * Width; // Non-camelCase identifiers
    return rectangleArea;
}
```

## PHP Coding Standards 

### Best Practices

1. **Learn the DRY Approach**: DRY, which stands for "Don't Repeat Yourself," is a fundamental programming principle applicable across all programming languages. It emphasizes the importance of avoiding redundancy in code.
2. **Structuring Your Code**: Structuring your applications involves dividing different components of the code into separate parts. This approach facilitates future code modifications.
3. **Always Use `<?php ?>`**: Programmers often try to take shortcuts when declaring PHP.
4. **Comment**: These comments serve as helpful annotations, aiding future navigation and understanding of the code, particularly when revisiting it or clarifying the purpose of specific functions.
5. **Documentation**: Use PHPDoc to document code.

### Style Guides

- **PSR-1: Basic Coding Standard**: Focuses on basic coding elements such as PHP tags, character encoding, and naming conventions.
- **PSR-2: Coding Style Guide**: Provides a detailed coding style guide.
- **PSR-12: Extended Coding Style**: Extends and expands the PSR-2 guidelines.

### Common Conventions

- **File Structure**: Organize files by their functionality to improve code organization and maintainability.
- **Namespace Usage**: Following the PSR-4 autoloading standard ensures consistent and efficient class loading in PHP applications. PSR-4 specifies a standardized way to organize PHP classes into namespaces and directories, facilitating automatic class loading without the need for manual require or include statements.
- **Class Declarations**: Adopting the practice of declaring one class per file enhances code clarity and maintainability. This convention promotes a clear separation of concerns by encapsulating each class's functionality in its own file. 

### Examples 
#### Good Practice


```javascript
<?php
// Structuring code with proper use of namespaces and class per file

namespace App\Controllers;

// Example of a class declaration following PSR-4 standard
class UserController {
    // Example method with comments and PHPDoc
    /**
     * Get user details by ID.
     *
     * @param int $userId User ID to retrieve details for.
     * @return array User details.
     */
    public function getUserDetails($userId) {
        // Business logic to fetch user details
        return [
            'id' => $userId,
            'name' => 'John Doe',
            'email' => 'john@example.com',
        ];
    }
}
?>
```
#### Bad Practice

```javascript
<?php
// Mixing HTML and PHP without proper structure

// No namespace or class separation, lack of comments and documentation
class UserController {
    public function getUserDetails($userId) {
        return ['id' => $userId, 'name' => 'John Doe', 'email' => 'john@example.com'];
    }
}
?>
```
## Conclusion

In conclusion, mastering coding standards in JavaScript and PHP is crucial for ensuring maintainable, efficient, and readable codebases. JavaScript's emphasis on avoiding global variables, consistent indentation, and proper variable initialization promotes cleaner code and reduces potential bugs. Meanwhile, PHP's adherence to the DRY principle, structured file organization, and clear documentation through PHPDoc enhances code clarity and facilitates future scalability. By implementing these best practices and following established style guides like PSR and JavaScript Airbnb, developers can streamline development processes, collaborate effectively, and deliver robust web applications. Embracing these standards not only improves code quality but also contributes to a more sustainable and productive development environment.

## References

- [What is JavaScript?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)
- [PHP Introduction](https://www.w3schools.com/PHP/php_intro.asp)
- [JavaScript Best Practices](https://www.w3schools.com/js/js_best_practices.asp)
- [JavaScript | Style Guide and Coding Conventions](https://www.geeksforgeeks.org/javascript-style-guide-and-coding-conventions/)
- [30+ PHP Best Practices for Beginners](https://code.tutsplus.com/30-php-best-practices-for-beginners--net-6194t)
- [Which Coding convention to follow for PHP?](https://stackoverflow.com/questions/139427/which-coding-convention-to-follow-for-php)
