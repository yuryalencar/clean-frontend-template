## Components

The components folder houses reusable UI components that encapsulate specific functionality or visual elements within your application. These components are modular, self-contained units that can be easily reused across different pages and sections of your application.

Follow an example of code for this directory:

```
// components/Button.tsx

import React from 'react';

interface ButtonProps {
  onClick?: () => void;
  children: React.ReactNode;
  className?: string;
}

const Button: React.FC<ButtonProps> = ({ onClick, children, className }) => {
  return (
    <button
      className={`px-4 py-2 bg-blue-500 text-white rounded-md shadow-md hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 ${className}`}
      onClick={onClick}
    >
      {children}
    </button>
  );
};

export default Button;
```
