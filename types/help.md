## Types

The types directory contains TypeScript type definitions and interfaces used throughout your application. TypeScript types help improve code quality and maintainability by providing compile-time type checking and enforcing type safety.

Follow an example of code for this directory:

```
// types/user.ts

// Define a TypeScript interface for user data
interface User {
  id: number;
  username: string;
  email: string;
  role: UserRole;
}

// Define a TypeScript enum for user roles
enum UserRole {
  ADMIN = 'admin',
  USER = 'user',
}

export { User, UserRole };
```
