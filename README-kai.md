Kai Welch
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

> 2. If the slugify function had a bug, which test files would have failing tests? Why does this happen?

> 3. What additional confidence do the integration tests give you that unit tests alone wouldn't provide?


# 3. Testing Trophy Connection