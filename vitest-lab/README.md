# 1. Setup Instructions
1. In the directory you work on the project, initialize the Node.js project by typing `npm init -y`
2. Open `package.json` file and update it to the following sections to enable ES modules
```json
{
  "name": "vitest-lab",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "test": "vitest",
    "test:run": "vitest run",
    "test:coverage": "vitest run --coverage"
  }
}
```
3. Install dependencies by typing `npm install -D typescript vitest @vitest/coverage-v8a`
4. Create `tsconfig.json` file contains following
```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ESNext",
    "moduleResolution": "bundler",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",
    "rootDir": "./src",
    "declaration": true,
    "types": ["vitest/globals"]
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist"]
}
```
5. Create `vitest.config.ts` file contains following
```TypeScript
import { defineConfig } from 'vitest/config';

export default defineConfig({
  test: {
    globals: true,
    environment: 'node',
    include: ['src/**/*.{test,spec}.{js,ts}'],
    coverage: {
      provider: 'v8',
      reporter: ['text', 'html'],
      exclude: ['node_modules/', 'vitest.config.ts']
    }
  }
});
```
6. Create the source directory structure by typing following (Linux/macOS/PowerShell)
```
mkdir -p src/utils
mkdir -p src/services
```
7. You project structure should look like this
``` 
vitest-lab/
├── node_modules/
├── src/
│   ├── utils/
│   └── services/
├── package.json
├── tsconfig.json
└── vitest.config.ts
```
8. Run `npm test`. If you see `No test files found`, you are on the right track!
9. The test file of `filename.ts` should look like `filename.test.ts`
10. To run the test, say `npm test` or `npm run test:coverage` to see the coverage report
# 2. Reflection Answers
### Reflection Question 2.3
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
### Reflection Question 4.3

# 3. Additional Tests

# 4. Testing Trophy Connection