## Contexts

The contexts directory contains files that define React Contexts used for managing state and providing data to components within your application. Contexts are a powerful tool for sharing data across multiple components without manually passing props through each level of the component tree.

Follow two examples of code for this directory:

```
// contexts/AuthContext.tsx

import React, { createContext, useContext, useState } from 'react';

interface AuthContextProps {
  isAuthenticated: boolean;
  login: () => void;
  logout: () => void;
}

const AuthContext = createContext<AuthContextProps | undefined>(undefined);

export const useAuthContext = () => {
  const context = useContext(AuthContext);
  if (!context) {
    throw new Error('useAuthContext must be used within an AuthContextProvider');
  }
  return context;
};

export const AuthContextProvider: React.FC = ({ children }) => {
  const [isAuthenticated, setIsAuthenticated] = useState(false);

  const login = () => {
    // Perform login logic here
    setIsAuthenticated(true);
  };

  const logout = () => {
    // Perform logout logic here
    setIsAuthenticated(false);
  };

  return (
    <AuthContext.Provider value={{ isAuthenticated, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
};
```

```
// contexts/DataContext.tsx

import React, { createContext, useContext, useState } from 'react';

interface DataContextProps {
  // Define the type of your global data here
  // For example, you can have user data, settings, etc.
  userData: {
    name: string;
    email: string;
  };
  updateUserData: (newUserData: { name: string; email: string }) => void;
}

// Create a new context
const DataContext = createContext<DataContextProps | undefined>(undefined);

// Custom hook to access the DataContext
export const useDataContext = () => {
  const context = useContext(DataContext);
  if (!context) {
    throw new Error('useDataContext must be used within a DataContextProvider');
  }
  return context;
};

// Provider component to wrap your application with
export const DataContextProvider: React.FC = ({ children }) => {
  const [userData, setUserData] = useState({ name: '', email: '' });

  const updateUserData = (newUserData: { name: string; email: string }) => {
    setUserData(newUserData);
  };

  return (
    <DataContext.Provider value={{ userData, updateUserData }}>
      {children}
    </DataContext.Provider>
  );
};

```
