## Constants

The constants directory contains files that define constants and configurations used throughout your application. These files typically store values that are reused frequently and may include configuration settings, API endpoints, error messages, and more.

Follow two examples of code for this directory:

```
// constants/api.ts

export const API_BASE_URL = 'https://api.example.com';
export const API_ENDPOINTS = {
  USERS: '/users',
  POSTS: '/posts',
  COMMENTS: '/comments',
};
```

```
// constants/colors.ts

export const COLORS = {
  PRIMARY: '#007bff',
  SECONDARY: '#6c757d',
  SUCCESS: '#28a745',
  DANGER: '#dc3545',
  WARNING: '#ffc107',
  INFO: '#17a2b8',
};
```
