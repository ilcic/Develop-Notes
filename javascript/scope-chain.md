# Scope Chain

Scope: where a variable is available in code

Scope Chain: the searching path of a variable

When a variable is not exist in the current scope, it will reference to the **outer environment **which is related to lexical environment generated by syntax parser.

```javascript
function b() {
    console.log(myVar);
}

function a() {
    var myVar = 2;
    b();
}

var myVar = 1;
a();
```

```
app.js:2 1
```

![](/assets/scope_chain_01.png)

```javascript
function a() {
    function b() {
        console.log(myVar);
    }
    var myVar = 2;
    b();
}

var myVar = 1;
a();
```

```
app.js:3 2
```

![](/assets/scope_chain_02.png)
