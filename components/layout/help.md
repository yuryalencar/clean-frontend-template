## Layout Components

The components/layout folder contains reusable layout components that define the overall structure and visual appearance of your application's pages. These components typically include elements such as headers, footers, sidebars, or any other layout-specific elements that are shared across multiple pages.

Follow an example of code for this directory:

```
// components/layout/MainLayout.tsx

import React from 'react';
import Header from '../Header';
import Footer from '../Footer';

const MainLayout: React.FC = ({ children }) => {
  return (
    <div className="flex flex-col min-h-screen">
      <Header />
      <main className="flex-grow">{children}</main>
      <Footer />
    </div>
  );
};

export default MainLayout;
```
