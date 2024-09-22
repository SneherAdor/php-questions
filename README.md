###### 1. What does this print?

```php
echo 2 + '2abc';
```

- A: `4`
- B: `2abc`
- C: `2`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, when adding `2 + '2abc'`, PHP converts the string `'2abc'` to the integer `2` (since it reads until the first non-numeric character). The operation becomes `2 + 2`, resulting in `4` (Answer A).

PHP automatically converts strings to numbers in numeric contexts. See the [PHP Manual](https://www.php.net/manual/en/language.types.string.php#language.types.string.conversion) for more details.

</p>
</details>

---

###### 2. What is the output?

```php
echo '012' == 12;
```

- A: `true`
- B: `false`
- C: `Error`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

PHP uses **loose comparison** (`==`), meaning it automatically converts the string `'012'` to a number. Since `'012'` is treated as an integer `12`, the comparison becomes `12 == 12`, which is `true`.

PHP's type juggling in loose comparisons is explained in the [PHP Manual on Type Comparisons](https://www.php.net/manual/en/types.comparisons.php).

</p>
</details>

---

###### 3. What does this print?

```php
$a = '1';
$a += 1;
echo $a;
```

- A: `11`
- B: `'2'` (as a string)
- C: `Syntax Error`
- D: `2`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

PHP first assigns the string `'1'` to `$a`. Then, the `+=` operator adds the integer `1` to `$a`. PHP automatically converts the string `'1'` to the integer `1` for the addition, making the result `1 + 1 = 2`. However, the value of `$a` becomes `2` as an **integer**.

PHP's automatic type conversion during arithmetic operations is explained in the [PHP Manual on Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php).

</p>
</details>

---

###### 4. What does this output?

```php
$a = 0;
if ($a == 'a') {
    echo "Equal";
}
```

- A: `Equal`
- B: `Error`
- C: `Nothing` (prints blank)
- D: `Warning`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The loose comparison (`==`) in PHP converts `'a'` to `0`, so `0 == 0` evaluates to `true`, printing "Equal". After that, "Not Equal" is printed on the same line, resulting in "EqualNot Equal".

</p>
</details>

---

###### 5. What will this code print?

```php
echo '10' + 5 . '5';
```

- A: `155`
- B: `105`
- C: `15`
- D: `1055`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

PHP processes the expression step-by-step:

1. **Type Juggling**: When PHP encounters the expression `'10' + 5`, it applies type juggling. According to the [PHP Manual on Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php), PHP automatically converts strings to numeric types during arithmetic operations if the strings contain valid numeric values.

2. **Evaluate the Addition**: The string `'10'` is converted to the integer `10`. Therefore, the addition becomes `10 + 5`, which results in `15`.

3. **Concatenation**: After the addition, PHP concatenates the result `15` with the string `'5'`. This occurs using the `.` operator, which combines two strings.

4. **Final Output**: The final result of concatenating `15` and `'5'` produces `155`.

</p>
</details>

---

###### 6. What will this code output?

```php
echo true + true;
```

- A: `1`
- B: `2`
- C: `true`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, boolean values are treated as integers in arithmetic operations: `true` is equivalent to `1` and `false` to `0`.

In the expression `true + true`, both `true` values convert to `1`, so it simplifies to `1 + 1`, resulting in `2`.

</p>
</details>

---

###### 7. What does this print?

```php
echo null == '';
```

- A: `true`
- B: `false`
- C: `1`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In PHP, when using loose comparison (`==`), type juggling occurs, meaning PHP attempts to convert the values to a common type for comparison. In this case, `null` is considered equivalent to an empty string (`''`) during the comparison, so `null == ''` evaluates to `true`. When `true` is echoed, it is represented as `1` in PHP.

</p>
</details>

---

###### 8. What will this code print?

```php
echo 1 . 2 * 3;
```

- A: `123`
- B: `36`
- C: `16`
- D: `15`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In PHP, operations follow a specific order of precedence. Here, the multiplication (`*`) has a higher precedence than concatenation (`.`). Therefore, the expression is evaluated as follows: first, `2 * 3` is calculated, which results in `6`. After that, the concatenation operation occurs, where `1` is concatenated with `6`, resulting in `16`.

</p>
</details>

---

###### 9. What does this print?

```php
$a = '5 apples';
$b = 10;
echo $a + $b;
```

- A: `15`
- B: `5 apples10`
- C: `10`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

When performing arithmetic operations, type juggling occurs. Here, the string `$a` contains `'5 apples'`. During the addition operation, PHP extracts the numeric part from the string, which is `5`, and ignores the rest (the text "apples").

Thus, the operation becomes `5 + 10`, resulting in `15`

</p>
</details>

---

###### 10. What is the output of this code?

```php
echo 1 == true;
```

- A: `true`
- B: `false`
- C: `Error`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In PHP, the loose comparison operator `==` checks if the two values are equal after performing type juggling. The boolean value `true` is treated as `1` when compared in a numeric context. Therefore, the comparison `1 == true` evaluates to `true`. When `true` is echoed, it is represented as `1` in PHP. Thus, the final output is `1`.

</p>
</details>

---

###### 11. What does this output?

```php
echo '5' == 5.0;
```

- A: `true`
- B: `false`
- C: `Error`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In PHP, the loose comparison operator `==` checks for equality while allowing type juggling. The string `'5'` is converted to a number during the comparison, and `5.0` is already a numeric value. Since both represent the same value, the comparison evaluates to `true`. When `true` is echoed, it is represented as `1` in PHP.

</p>
</details>

---

###### 12. What is the output?

```php
$a = true;
$b = false;
echo $a - $b;
```

- A: `1`
- B: `0`
- C: `Error`
- D: `false`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, boolean values are treated as integers in arithmetic operations: `true` is equivalent to `1` and `false` to `0`. Therefore, the expression `1 - 0` evaluates to `1`.

</p>
</details>

---

###### 13. What does this print?

```php
$foo = 'bar';
$bar = 'baz';
echo $$foo;
```

- A: `bar`
- B: `baz`
- C: `Error`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, `$$` is a variable variable. It means that the name of the variable is determined by the value of another variable. In this case, `$foo = 'bar'`, so `$$foo` translates to `$bar`. Since `$bar = 'baz'`, `echo $$foo;` prints `'baz'`.

For more on variable variables, see the [PHP Manual - Variable Variables](https://www.php.net/manual/en/language.variables.variable.php).

</p>
</details>

---

###### 14. What is the output of this code?

```php
$a = 3;
$b = &$a;
$a = 5;
$b = 10;
echo $a;
```

- A: `3`
- B: `5`
- C: `10`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In the code, `$b` is a reference to `$a` (`$b = &$a`), meaning both variables point to the same memory location. When `$a` is set to `5`, both `$a` and `$b` become `5`. Later, when `$b` is assigned `10`, it also changes `$a` to `10` since they are linked.

Thus, when `echo $a;` is executed, the output is `10`.

For more on PHP references, check the [PHP Manual - References](https://www.php.net/manual/en/language.references.php).

</p>
</details>

---

###### 15. What does this return?

```php
return 'apple' > 'banana';
```

- A: `true`
- B: `false`
- C: `1`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, string comparison is done **lexicographically** (based on the ASCII values of characters). Since `'apple'` comes alphabetically **before** `'banana'`, the comparison `'apple' > 'banana'` evaluates to `false`.

For more on string comparisons, refer to the [PHP Manual - String Comparison](https://www.php.net/manual/en/language.operators.comparison.php).

</p>
</details>

---

###### 16. What is printed here?

```php
echo 10 . 5 / 2;
```

- A: `105`
- B: `102.5`
- C: `10`
- D: `1052.5`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In this expression, PHP follows **operator precedence** rules. Division (`/`) has higher precedence than concatenation (`.`).

- First, `5 / 2` is evaluated, which results in `2.5`.
- Then, the result `2.5` is concatenated with the string `'10'`, giving `102.5`.

Thus, the final output is `102.5`.

For more on operator precedence, refer to the [PHP Manual - Operator Precedence](https://www.php.net/manual/en/language.operators.precedence.php).

</p>
</details>

---

###### 17. What is the result of this?

```php
$values = [1, 2, 3];
foreach ($values as &$value) {
    $value += 2;
}
echo $values[0];
```

- A: `1`
- B: `3`
- C: `4`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In the `foreach` loop, each value of the array `$values` is referenced by `&$value`, allowing direct modification of the original array values. The loop adds `2` to each element:

- `$values[0]` becomes `1 + 2 = 3`
- `$values[1]` becomes `2 + 2 = 4`
- `$values[2]` becomes `3 + 2 = 5`

Thus, when `echo $values[0];` is executed, the output is `3`.

</p>
</details>

---

###### 18. What does this print?

```php
echo 5 == '5.0';
```

- A: `true`
- B: `false`
- C: `Error`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In PHP, when using the loose comparison operator (`==`), type juggling occurs. The string `'5.0'` is converted to the number `5` during the comparison. Since `5 == 5`, the comparison evaluates to `true`. When `true` is echoed, it is represented as `1` in PHP.

Thus, the final output is `1`.

For more information, refer to the [PHP Manual - Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php).

</p>
</details>

---

###### 19. What will this code print?

```php
echo (int) ( (0.1 + 0.7) * 10 );
```

- A: `7`
- B: `8`
- C: `1`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, floating-point numbers are not always perfectly precise due to how they are represented in memory.

- The expression `(0.1 + 0.7)` might not result in exactly `0.8` but something slightly less, like `0.799999...` due to floating-point precision errors.
- Multiplying that by `10` gives `7.9999...`.
- Casting this result to an integer using `(int)` truncates the decimal part, yielding `7`.

Thus, the final output is `7`.

For more details, see the [PHP Manual - Floating Point Numbers](https://www.php.net/manual/en/language.types.float.php).

</p>
</details>

---

###### 20. What will this output?

```php
function test() {
    static $count = 0;
    $count++;
    echo $count;
}
test();
test();
```

- A: `11`
- B: `12`
- C: `22`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, a `static` variable inside a function retains its value between function calls. Here's how it works:

- The first time `test()` is called, `$count` is initialized to `0`, incremented to `1`, and then `1` is printed.
- The second time `test()` is called, `$count` retains its previous value (`1`), is incremented to `2`, and then `2` is printed.

Thus, the combined output is `12`.

For more details, refer to the [PHP Manual - Static Variables](https://www.php.net/manual/en/language.variables.scope.php#language.variables.scope.static).

</p>
</details>

---

###### 21. What is printed by this code?

```php
$var = "Hello World";
echo isset($var[5]);
```

- A: `true`
- B: `false`
- C: `1`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In this code, `$var[5]` refers to the **6th character** of the string `"Hello World"`, which is a **space**. The `isset()` function checks if this character exists, and since it does, `isset($var[5])` returns `true`. In PHP, `true` is printed as `1`.

Thus, the output is `1`.

For more information on string offsets, see the [PHP Manual - String Access and Modification by Character](https://www.php.net/manual/en/language.types.string.php#language.types.string.substr).

</p>
</details>

---

###### 22. What does this print?

```php
echo strlen(null);
```

- A: `0`
- B: `1`
- C: `Error`
- D: `Warning`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, the `strlen()` function calculates the length of a string. When `null` is passed to `strlen()`, PHP treats it as an empty string. Since the length of an empty string is `0`, `strlen(null)` returns `0`.

Thus, the output is `0`.

For more details, refer to the [PHP Manual - strlen()](https://www.php.net/manual/en/function.strlen.php).

</p>
</details>

---

###### 23. What is the output?

```php
echo 10 % 0;
```

- A: `10`
- B: `0`
- C: `Error`
- D: `Warning`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In PHP, performing a modulo operation with zero (as in `10 % 0`) results in a **warning**. This is because division or modulus by zero is mathematically undefined. While the code itself does not produce a fatal error and will continue executing, PHP issues a warning about the invalid operation.

Thus, the output is a warning message regarding the attempt to divide by zero.

For more information, see the [PHP Manual - Error Handling](https://www.php.net/manual/en/errorfunc.constants.php).

</p>
</details>

---

###### 24. What will this code output?

```php
$var = 5;
echo ++$var + $var++;
```

- A: `10`
- B: `11`
- C: `12`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In this code, we have both pre-increment (`++$var`) and post-increment (`$var++`):

1. **Pre-increment**: `++$var` increases `$var` from `5` to `6`. The expression now evaluates as `6 + $var++`.
2. At this point, `$var` is still `6` for the current calculation, but `$var++` will increment it after the expression is evaluated.
3. Now, evaluating `6 + 6` results in `12`.
4. After this calculation, `$var` is incremented to `7` due to the post-increment.

Therefore, the final output of the expression is `12`.

For more details, refer to the [PHP Manual - Pre-Increment and Post-Increment](https://www.php.net/manual/en/language.operators.increment.php).

</p>
</details>

---

###### 25. What is the output of this code?

```php
echo "Hello" || 0;
```

- A: `Hello`
- B: `1`
- C: `true`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, the `||` operator returns `true` if either of its operands is truthy. Here's how it works:

- The string `"Hello"` is considered **truthy**.
- The number `0` is considered **falsy**.

Since the first operand (`"Hello"`) is truthy, the whole expression evaluates to `true`. When `true` is echoed in PHP, it is printed as `1`.

Thus, the output is `1`.

For more details, refer to the [PHP Manual - Logical Operators](https://www.php.net/manual/en/language.operators.logical.php).

</p>
</details>

---

###### 26. What is printed?

```php
echo false ?? 'default';
```

- A: `false`
- B: `default`
- C: Program will not output anything
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

In PHP, the null coalescing operator (`??`) returns the first operand if it is not `null`; otherwise, it returns the second operand.

In this case:

- `false` is **not null**.
- Since `false` is a valid value (even though it is falsy), the expression returns `false` instead of the string `'default'`.

Thus, the output is `false`, but since `false` is printed as an empty value in PHP, it appears as though nothing is printed.

For more information, see the [PHP Manual - Null Coalescing Operator](https://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.coalesce).

</p>
</details>

---

###### 27. What will this code output?

```php
$var = 5;
function test() {
    global $var;
    echo $var;
}
test();
```

- A: `5`
- B: `Error`
- C: `null`
- D: `Warning`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, the `global` keyword allows a function to access a variable that is defined in the global scope. Here's how it works in this case:

- `$var` is defined globally with the value `5`.
- Inside the `test()` function, the `global $var;` statement makes the global `$var` accessible within the function.
- Therefore, when `echo $var;` is executed, it prints the value of the global `$var`, which is `5`.

Thus, the output is `5`.

For more details, refer to the [PHP Manual - Global Variables](https://www.php.net/manual/en/language.variables.scope.php#language.variables.scope.global).

</p>
</details>

---

###### 28. What is the output?

```php
echo 'A' + 1;
```

- A: `A1`
- B: `Error`
- C: `1`
- D: `66`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In PHP, when a string is used in an arithmetic operation, it is first converted to a number. If the string starts with a character, PHP converts that character to its ASCII value:

- The ASCII value of `'A'` is `65`.
- Therefore, `'A' + 1` becomes `65 + 1`, which equals `66`.

Thus, the output is `66`.

For more details, see the [PHP Manual - String Conversion to Numbers](https://www.php.net/manual/en/language.types.string.php#language.types.string.conversion).

</p>
</details>

---

###### 29. What is printed by this code?

```php
$var = 'hello';
$$var = 'world';
echo $hello;
```

- A: `hello`
- B: `world`
- C: `Error`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP, `$$var` is a variable variable, meaning it refers to the variable whose name is the value of `$var`. Here's what happens:

- `$var = 'hello';` assigns the string `'hello'` to the variable `$var`.
- `$$var = 'world';` means that PHP will create a variable named `$hello` (since `$var` contains `'hello'`), and assign it the value `'world'`.

Therefore, when `echo $hello;` is executed, it prints `'world'`.

For more details, refer to the [PHP Manual - Variable Variables](https://www.php.net/manual/en/language.variables.variable.php).

</p>
</details>

---

###### 30. What will this output?

```php
echo (true + false) * 2;
```

- A: `1`
- B: `2`
- C: `3`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

In PHP:

- `true` is treated as `1`.
- `false` is treated as `0`.

The expression `(true + false)` becomes `1 + 0`, which equals `1`. Then, multiplying by `2` gives `1 * 2 = 2`.

The output is `2`.

For more on type conversion, see the [PHP Manual - Boolean Type Juggling](https://www.php.net/manual/en/language.types.boolean.php#language.types.boolean.casting).

</p>
</details>

---

###### 31. What will this code output?

```php
echo 2 ** 3 ** 2;
```

- A: `64`
- B: `8`
- C: `512`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The exponentiation operator (`**`) is **right-associative** in PHP. This means the expression is evaluated as:

```php
2 ** (3 ** 2)
```

1. First, `3 ** 2` is evaluated, which results in `9`.
2. Then, `2 ** 9` is calculated, which equals `512`.

The final output is `512`.

</p>
</details>

---

###### 32. What does this code print?

```php
echo (10 <=> 10);
```

- A: `1`
- B: `0`
- C: `-1`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The spaceship operator (`<=>`) compares two values and returns:

- `-1` if the left value is less than the right,
- `0` if both values are equal, and
- `1` if the left value is greater than the right.

In this case, `10 <=> 10` compares two equal values, so it print `0`.

</p>
</details>

---

###### 33. What is printed by this code?

```php
$var = 2.5;
echo ++$var * $var++;
```

- A: `6`
- B: `7.5`
- C: `5.25`
- D: `12.25`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

Let's break down the expression:

1. **Pre-increment (`++$var`)**:

   - `$var` starts as `2.5`.
   - After pre-increment, it becomes `3.5`.

2. **Post-increment (`$var++`)**:
   - This will return the current value of `$var` (which is `3.5`) for the multiplication and then increment it to `4.5` after this operation.

Now the expression becomes:

- `3.5 * 3.5`, which equals `12.25`.

Thus, the final output is `12.25`.

</p>
</details>

---

###### 34. What does this print?

```php
echo '5' . '5' - '5';
```

- A: `55`
- B: `50`
- C: `Error`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The expression starts with two string concatenations: `'5' . '5'` results in the string `'55'`. Then, the subtraction operation `55 - '5'` takes place. In PHP, when performing arithmetic with strings, the string is converted to a number. So, `'5'` becomes `5`. Therefore, the expression becomes `55 - 5`, which equals `50`.

</p>
</details>

---

###### 35. What will this code output?

```php
$a = [1, 2, 3];
$b = &$a;
$b[] = 4;
echo count($a);
```

- A: `3`
- B: `4`
- C: `Error`
- D: `Warning`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

1. The array `$a` is initialized with the values `[1, 2, 3]`.
2. The variable `$b` is a reference to `$a`, meaning any modifications to `$b` will also affect `$a`.
3. When `4` is added to `$b` using `$b[] = 4;`, it also updates `$a` to `[1, 2, 3, 4]`.
4. Finally, `count($a)` counts the number of elements in the array, which is now `4`.

</p>
</details>

---

###### 36. What will this code output?

```php
class Test {
    public static $value = 5;
}
echo Test::$value++;
```

- A: `5`
- B: `6`
- C: `Error`
- D: `5 and then 6`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The static property `Test::$value` is initialized to `5`. When `echo Test::$value++` is executed, the current value (`5`) is printed first. The post-increment operator (`++`) increments the value of `Test::$value` after its current value has been used in the output. Therefore, the output is `5`, and after this line, `Test::$value` becomes `6`, but this change is not reflected in the output.

You can refer to the [PHP Manual on Increment Operators](https://www.php.net/manual/en/language.operators.increment.php) for more details on how post-increment works.

</p>
</details>

---

###### 37. What will this code print?

```php
function foo(&$x) {
    $x++;
}
$a = 5;
foo($a);
echo $a;
```

- A: `5`
- B: `6`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

1. The function `foo` takes a parameter by reference (`&$x`), meaning any changes to `$x` will directly affect the variable passed into the function.
2. The variable `$a` is initialized to `5`.
3. When `foo($a)` is called, it increments `$x` (which is a reference to `$a`) by `1`.
4. As a result, `$a` is updated to `6`.
5. Finally, `echo $a` prints the updated value, which is `6`.

You can refer to the [PHP Manual on Functions](https://www.php.net/manual/en/functions.arguments.php) for more information on passing parameters by reference.

</p>
</details>

---

###### 38. What is the output of this code?

```php
$a = 'Hello';
$b = 'World';
echo $a <=> $b;
```

- A: `1`
- B: `-1`
- C: `0`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

1. The spaceship operator `<=>` compares two values.
2. When comparing strings lexicographically, it determines their order based on their ASCII values.
3. In this case, `'Hello'` comes before `'World'`, so the comparison results in `-1`.
4. Thus, the output of the code is `-1`, indicating that the first string is less than the second.

For further details on string comparison and the spaceship operator, you can refer to the [PHP Manual on Comparison Operators](https://www.php.net/manual/en/language.operators.comparison.php).

</p>
</details>

---

###### 39. What is the output of this code?

```php
function check($x) {
    return $x ?: 'default';
}
echo check('');
```

- A: `default`
- B: `null`
- C: `Error`
- D: `''`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The function `check($x)` uses the shorthand ternary operator `?:`. This operator evaluates the expression on the left (`$x`). If `$x` is falsy (like an empty string, `0`, or `null`), it returns the value on the right side, which is `'default'`. Since the argument passed to the function is an empty string (`''`), which is considered falsy in PHP, the function returns `'default'`.

</p>
</details>

---

###### 40. What does this code print?

```php
echo implode(',', [1, 2, 3]);
```

- A: `1,2,3`
- B: `123`
- C: `Error`
- D: `1 2 3`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `implode()` function in PHP takes two arguments: a string to use as the separator (in this case, a comma `','`) and an array of elements to join (here, `[1, 2, 3]`). It concatenates the elements of the array into a single string, using the specified separator. Therefore, `implode(',', [1, 2, 3])` produces the string `1,2,3`, which is then printed by the `echo` statement.

</p>
</details>

---

###### 41. What will this output?

```php
function test() {
    return 'Hello ' . (yield 'World');
}
echo test()->current();
```

- A: `Hello World`
- B: `Hello `
- C: `Error`
- D: `World`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

This code uses a generator function, but the `yield` keyword does not execute until the generator is iterated over. Thus, `current()` returns the initial value of the string concatenation, which is just `'Hello '`.

For a detailed explanation of generators, refer to the [yield keyword](https://www.php.net/manual/en/language.generators.syntax.php#control-structures.yield).

</p>
</details>

---

###### 42. What is the output of this code?

```php
function foo() {
    return [1, 2, 3];
}
list($a, $b, $c) = foo();
echo $c;
```

- A: `1`
- B: `2`
- C: `3`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The `list()` function in PHP assigns variables to values from an array. In this code, the `foo()` function returns an array containing the values `[1, 2, 3]`. The `list($a, $b, $c)` statement extracts these values, assigning `1` to `$a`, `2` to `$b`, and `3` to `$c`. Therefore, when `echo $c;` is executed, it outputs `3`.

For more information on `list()`, see the [PHP Manual](https://www.php.net/manual/en/functions.list.php).

</p>
</details>

---

###### 43. What does this code output?

```php
class MyClass {
    public function __toString() {
        return "MyClass Object";
    }
}

$obj = new MyClass();
echo $obj;
```

- A: `MyClass Object`
- B: `Object`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `__toString()` magic method allows an object to be treated as a string. Thus, when `echo` is called on `$obj`, it outputs `MyClass Object`.

For more on magic methods, refer to the [PHP Manual](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring).

</p>
</details>

---

###### 44. What is the output of this code?

```php
$a = ['a', 'b', 'c'];
$b = &$a;
$b[1] = 'changed';
echo $a[1];
```

- A: `b`
- B: `changed`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Here, `$b` is a reference to `$a`, so modifying `$b[1]` also modifies `$a[1]`. Thus, the output is `changed`.

For further details on references, check the [PHP Manual](https://www.php.net/manual/en/language.references.php).

</p>
</details>

---

###### 45. What does this code output?

```php
$a = [1, 2, 3];
array_unshift($a, 0);
echo end($a);
```

- A: `0`
- B: `3`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`array_unshift()` adds `0` to the beginning of the array, but `end()` returns the last element, which is still `3`.

For more on `end()`, check the [PHP Manual](https://www.php.net/manual/en/function.end.php).

</p>
</details>

---

###### 46. What is the output of this code?

```php
function bar(&$var) {
    $var += 10;
}
$a = 5;
bar($a);
echo $a;
```

- A: `5`
- B: `10`
- C: `15`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The function `bar()` takes a parameter by reference, allowing it to modify the original variable directly. When `$a` is passed to `bar()`, its value of `5` is increased by `10`, resulting in `$a` being updated to `15`. Therefore, the output is `15`.

For more about passing by reference, see the [PHP Manual](https://www.php.net/manual/en/language.references.php#language.references.pass-by-reference).

</p>
</details>

---

###### 47. What will this code print?

```php
$a = ['a' => 1, 'b' => 2];
$b = $a;
$b['a'] = 3;
echo $a['a'];
```

- A: `1`
- B: `2`
- C: `3`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

In PHP, arrays are copied by value, not by reference. Therefore, changing `$b['a']` does not affect `$a`, so it outputs `1`.

For more on array assignment, see the [PHP Manual](https://www.php.net/manual/en/language.types.array.php).

</p>
</details>

---

###### 48. What will this output?

```php
class A {
    const VALUE = 5;
}

echo A::VALUE + 1;
```

- A: `5`
- B: `6`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Constants are accessed using the `::` operator and can be used in expressions. Here, it outputs `5 + 1`, resulting in `6`.

For more about constants, see the [PHP Manual](https://www.php.net/manual/en/language.constants.php).

</p>
</details>

---

###### 49. What is the output of this code?

```php
class MyClass {
    public $value;
    public function __construct($value) {
        $this->value = $value;
    }
}

$obj = new MyClass(10);
echo $obj->value++;
```

- A: `10`
- B: `11`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The post-increment operator returns the original value before incrementing, so it outputs `10`. The value is then incremented to `11`, but that change is not reflected in the output.

For more on increment operators, see the [PHP Manual](https://www.php.net/manual/en/language.operators.increment.php).

</p>
</details>

---

###### 50. What does this code print?

```php
class A {
    public static $count = 1;

    public static function increment() {
        self::$count++;
    }
}

echo A::increment();
```

- A: `1`
- B: `2`
- C: `Error`
- D: Nothing will print

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The code defines a class `A` with a static property `$count` and a static method `increment()`. The `increment()` method increases `$count` by `1`, but it does not return any value. When `A::increment()` is called, it increments `$count` to `2`, but since the method does not have a return statement, nothing is printed. Therefore, the output is nothing.

</p>
</details>

---

###### 51. What does this code output?

```php
function test($a = 1, $b = 2) {
    return $a + $b;
}
echo test(null);
```

- A: `1`
- B: `2`
- C: `3`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Passing `null` to `$a` is treated as `0`, thus the output is `0 + 2`, which equals `2`.

For more on default arguments, refer to the [PHP Manual](https://www.php.net/manual/en/functions.arguments.php).

</p>
</details>

---

###### 52. What does this code print?

```php
function bar() {
    return function() {
        return 'Inner Function';
    };
}
echo bar();
```

- A: `Inner Function`
- B: `Error`
- C: `undefined`
- D: `Bar`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The code defines a function `bar()` that returns an anonymous function (a closure). However, when `bar()` is called, it is echoed directly, which is not valid because the returned value is a function, not a string. Therefore, the code produces an error when trying to echo the function itself.

For more details on anonymous functions and closures in PHP, you can refer to the [PHP Manual on Anonymous Functions](https://www.php.net/manual/en/functions.anonymous.php).

</p>
</details>

---

###### 53. What will this code print?

```php
$a = new stdClass();
$a->prop = 'Hello';
$b = $a;
$b->prop = 'World';
echo $a->prop;
```

- A: `Hello`
- B: `World`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Objects in PHP are assigned by reference. When `$b->prop` is modified, it also changes `$a->prop`. Thus, the output is `World`.

For more on object assignment, see the [PHP Manual](https://www.php.net/manual/en/language.objects.php).

</p>
</details>

---

###### 54. What will this output?

```php
$a = 0;
function test() {
    static $a = 0;
    return $a++;
}
echo test() + test();
```

- A: `0`
- B: `1`
- C: `2`
- D: `3`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The function `test()` has a static variable `$a`, which retains its value between function calls. Initially, `$a` is `0`.

1. The first call to `test()` returns `0` (the current value of `$a`), and then `$a` is incremented to `1`.
2. The second call to `test()` returns `1` (the new value of `$a`), and then `$a` is incremented to `2`.

When you sum the two returned values (`0 + 1`), the output is `1`.

For more information about static variables in PHP, see the [PHP Manual on Static Variables](https://www.php.net/manual/en/functions.variable.php#functions.variable.static).

</p>
</details>
