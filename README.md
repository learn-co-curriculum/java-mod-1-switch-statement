# Switch Statements

## Learning Goals

- Explain what a switch statement is

## What is a Switch Statement?

A **switch statement** is multiway branch that is more efficient than nested
`if` statements in that it can have multiple execution paths. To help understand
more what goes into a switch statement, let us look at the syntax:

```java
switch(expression) {
        // case statements
        // values must be the same data type as the expression
        case value1:
        // statement sequence
        break;    // breaks out of the case statement
        
    case value2:
        // statement sequence
        break;    // breaks out of the case statement

    // There can be multiple case statements
    // and the default case statement is executed if none of the above
    // cases are true
    default:
        // statement sequence
        // no break is needed in the default case
}
```

The `switch` expression must result in a `byte`, `int`, `char` or a
`String` and each `case` statement must have a unique constant that is
the same data type as the expression. Duplicate cases are not allowed in
switch statements.

The `break` statement is optional, although most programmers tend to use it to
show that they have finished writing the code needed within the case and that it
can get out of the `switch`. When the code reaches a `break`, it will exit from
the `switch` and continue on with the next statement outside the `switch`. If
the `break` is not present, then it will "fall through" and the code will
continue onto the next case until it sees a `break` statement.

`default` statements are also optional and usually appear at the end of the
`switch`. The `default` statement sequence is executed if no `case` matches. If
the `default` statement is omitted, then no action will take place.

The advantage of switch statements are that they tend to be more efficient than
a typical if-else-if block. Let's look at an example of an if-else-if block
that could benefit from being a switch statement:

```java
char grade = 'B';
if (grade == 'A') {
    System.out.println("Wow! You got an A!");
} else if (grade == 'B') {
    System.out.println("Great job!");
} else if (grade == 'C') {
    System.out.println("Congrats! You passed!");
} else if (grade == 'D') {
    System.out.println("Whew! You just passed!");
} else if (grade == 'F') {
    System.out.println("Oops! Better luck next time!");
} else {
    System.out.println("Invalid letter grade");
}
```

Now let us use a `switch` instead of the if-else-if cascade:

```java
char grade = 'B';
switch(grade) {
    case 'A':
        System.out.println("Wow! You got an A!");
        break;
    case 'B':
        System.out.println("Great job!");
        break;
    case 'C':
        System.out.println("Congrats! You passed!");
        break;
    case 'D':
        System.out.println("Whew! You just passed!");
        break;
    case 'F':
        System.out.println("Oops! Better luck next time!");
        break;
    default:
        System.out.println("Invalid letter grade");
}
```

The switch statement tends to look cleaner and more readable than the if-else-if
block. It also can avoid repetitive code.

The disadvantages of a switch statement would be that it cannot have an
expression with an object or fractional numeric data types like `float` or
`double`. It also must have a constant as the `case` - it cannot have a
plain variable.
