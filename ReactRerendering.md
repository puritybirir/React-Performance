## Unnecessary Renders: A Performance Bottleneck
In React applications, rendering can be an expensive operation, particularly when dealing with large and complex components. Unnecessary renders occur when a component re-renders even though its state or props have not changed. This can happen due to various reasons, such as incorrect use of hooks, improper implementation of shouldComponentUpdate (for class components), or not utilizing memoization techniques for functional components.


## Functional Components vs. Class Components
React components can be functional or class-based. Functional components are simpler and perform better. They don’t have the overhead of instances and lifecycle methods. With the introduction of React Hooks, functional components can now manage state and side-effects, making them the preferred choice for performance-oriented development.

### Example (Functional Component):
```jsx
const FunctionalComponent = () => {
  // Component logic
  return <div>Hello, Functional Component!</div>;
};
```

## React Hooks: Enhancing Performance
React Hooks allow functional components to manage state and side-effects without writing a class. They enhance performance by reducing the complexity of component logic. Hooks like useState for managing state and useEffect for managing side-effects enable more efficient and readable code.

## Example (useState and useEffect Hooks):
```jsx
import React, { useState, useEffect } from 'react';

const FunctionalComponentWithHooks = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
    return () => {
      // Cleanup logic
    };
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};

```

## Memoization and useMemo, useCallback

Memoization is the process of caching the results of expensive function calls and returning the cached result when the same inputs occur again. React provides useMemo and useCallback hooks to optimize performance by memoizing values and functions, preventing unnecessary recalculations.

Example (useMemo Hook):
```jsx
import React, { useMemo } from 'react';

const MemoizedComponent = ({ data }) => {
  const processedData = useMemo(() => processData(data), [data]);

  return <div>{processedData}</div>;
};

```

Example (useCallback hook ):
```jsx
import React, { useCallback } from 'react';

const MemoizedCallbackComponent = () => {
  const handleClick = useCallback(() => {
    // Handle click logic
  }, []); // No dependencies, callback will not be recreated on re-renders

  return <button onClick={handleClick}>Click Me</button>;
};
```

## Error Boundaries: Handling Performance Issues Gracefully

Error boundaries are React components that catch JavaScript errors anywhere in the component tree and log those errors. They allow the application to gracefully handle errors and provide fallback UI, preventing the entire app from crashing due to unhandled errors.

Example

```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children;
  }
}


<ErrorBoundary>
  {/* Components that might throw errors */}
  <ComponentWithError />
</ErrorBoundary>

```
