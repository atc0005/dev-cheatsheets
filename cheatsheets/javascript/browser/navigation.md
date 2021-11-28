# Navigation 


## Reload

Use cached page with false or full reload with true.

```javascript 
window.location.reload(false)
```

e.g. in React

```jsx
function refreshPage() {
  window.location.reload(false);
}

function App() { 
  return (
    <div>
      <button onClick={refreshPage}>
        Click to reload!
      </button>
    </div>
  );
}

export default App;
```


## Redirect 

Simulate a mouse click:

```javascript 
window.location.href = "https://example.com";
```

Simulate an HTTP redirect:

```javascript 
window.location.replace("https://example.com");
```

Using replace also removes the old URL from the history so you cannot click Back.

Source [W3 Schools](https://www.w3schools.com/howto/howto_js_redirect_webpage.asp)