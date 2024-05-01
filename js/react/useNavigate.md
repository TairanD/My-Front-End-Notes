# useNavigate

## 1 - Introduction
`useNavigate` is a hook function in the React Router library, which is used to achieve pages navigation function in 
React components. It returns a function used to navigate to different url. It's used to replace `<Link>` or `history.push`.

For example:
```javascript
import { useNavigate } from 'react-router-dom';

function MyComponent() {
  const navigate = useNavigate();

  function handleClick() {
    // 导航到 '/other-page'
    navigate('/other-page');
  }

  return (
    <div>
      <button onClick={handleClick}>Go to other page</button>
    </div>
  );
}
```
## 2 - Why use useNavigate?
`useNavigate` can replace `<Link>` components or `history.push` method for programmatic navigation because it provides a 
convenient way to perform navigation within functional components **without the need to render additional components or 
access the history object**, both of which can sometimes lead to complex code structures, especially when navigating within functional components.