## Utils

The utils folder contains utility functions, helper classes, and other reusable code snippets that provide common functionality used throughout your application. These utilities serve as building blocks for your application logic and encapsulate common tasks or operations that can be reused across multiple parts of your codebase.

The utils folder typically contains more general-purpose utility functions or helper classes that provide common functionality used throughout the application. Here are some characteristics of the utils folder:

1. General-Purpose Functionality: Utilities in the utils folder are often more generic and reusable across different parts of the application. They may include functions for data manipulation, string formatting, date handling, or other common tasks.

2. No External Dependencies: Utilities in the utils folder usually do not depend on external libraries or services. They encapsulate basic or commonly used functionality that does not require interactions with external systems.

3. Lower Level of Abstraction: Utilities in the utils folder tend to provide a lower level of abstraction compared to libraries in the lib folder. They focus on providing simple and generic functionality that can be easily reused in different contexts within the application.

Follow an example of code for this directory:

```
// utils/formatDate.ts

/**
 * Format a date object into a string using the specified format.
 * @param date The date object to format.
 * @param format The format string to use (e.g., 'yyyy-MM-dd', 'MM/dd/yyyy HH:mm:ss').
 * @returns The formatted date string.
 */
export const formatDate = (date: Date, format: string): string => {
  const options: Intl.DateTimeFormatOptions = {
    year: 'numeric',
    month: '2-digit',
    day: '2-digit',
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
  };

  const formattedDate = new Intl.DateTimeFormat('en-US', options).format(date);
  return format.replace(/(yyyy|MM|dd|HH|mm|ss)/g, (match) => {
    switch (match) {
      case 'yyyy':
        return String(date.getFullYear()).padStart(4, '0');
      case 'MM':
        return String(date.getMonth() + 1).padStart(2, '0');
      case 'dd':
        return String(date.getDate()).padStart(2, '0');
      case 'HH':
        return String(date.getHours()).padStart(2, '0');
      case 'mm':
        return String(date.getMinutes()).padStart(2, '0');
      case 'ss':
        return String(date.getSeconds()).padStart(2, '0');
      default:
        return match;
    }
  });
};

```
