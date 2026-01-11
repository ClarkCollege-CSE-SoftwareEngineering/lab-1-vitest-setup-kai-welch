Kai Welch
***
# 1. Additional Tests
1. In 'slugify' row 28
```TypeScript
it('handles empty string', () => {
    expect(slugify('')).toBe('');
});
```
2. In 'truncate' row 51
```TypeScript
it('handles maxLength 0', () => {
  expect(truncate('Hello', 0, '')).toBe('');
});
```
3. In 'capitalize' row 70
```TypeScript
it('handles both lower and upper to toggle', () => {
  expect(capitalize('hello World')).toBe('Hello world');
});
```
4. In 'countWords' row 93
```TypeScript
it('Handles spaces before and after', () => {
  expect(countWords('  Hello  world  ')).toBe(2);
});
```

# 2. Reflection Answers
### Reflection Question on Step 2.3
> Look at the add tests. The first test uses explicit Arrange-Act-Assert comments. Why might this pattern be useful, especially for complex tests?

This test could be written `expect(add(2, 3)).toBe(5);`, instead of: 
```TypeScript
 // Arrange
  const a = 2;
  const b = 3;

 // Act
  const result = add(a, b);

// Assert
  expect(result).toBe(5);
```
However, this pattern is useful especially for complex tests because it breaks the test down into steps and makes it easier to recognize the condition, tested codes and expected result. 
### Reflection Question on Step 4.3
> 1. Looking at strings.test.ts and content.test.ts, which file contains unit tests and which contains integration tests? How can you tell the difference?

`strings.test.ts` contains unit tests, and `content.test.ts` contains integration tests. You can tell the difference by looking what each file is testing. `strings.test.ts` tests each functioin one by one. `content.test.ts` tests integrated functions by testing functions in `content.ts` that call multiple  functions that are in `string.ts`.
> 2. If the slugify function had a bug, which test files would have failing tests? Why does this happen?

Both `string.test.ts` and `content.test.ts` files will have failing tests. This happens because `string.test.ts` tests slugify function as a unit, and `content.test.ts` tests slugify function as a part of integrated functions.
> 3. What additional confidence do the integration tests give you that unit tests alone wouldn't provide?

Integration tests would give me confidence that each unit will work together correctly while unit tests only give confidence that specific function works correctly. 

# 3. Testing Trophy Connection
The testing trophy concept suggest 4 types of tests. Static, unit, integration and end-to-end, from bottom to top of the trophy. In this lab, syntax-checking by vi and type-checking by TypeScript represent static test, `string.test.ts` represent unit test, `content.test.ts` represent integration test, and github actions represent end-to-end test. Each test is built on the confidence of the test below itself. The inregration test is the test that resources need to be dedicated the most because it has the best balance between cost ant confidence as return. 