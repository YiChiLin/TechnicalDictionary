---
title: JavaScript Promise
---
# Promise
## Understand promises before you start using async/await
- async/await is promise. They are the same thing basically.
- Every async function will return a promise.
- Every await will also be a promise.

## Promise
- It can be said like "this is going to be an async function, whether or not the return value is available now or later".
- Simple Promise
```js
function getFirstUser() {
    return getUsers().then(function(users) {
        return users[0].name;
    });
}
```
- To Catch Error
```js
function getFirstUser() {
    return getUsers().then(function(users) {
        return users[0].name;
    }).catch(function(err) {
        return {
          name: 'default user'
        };
    });
}
```

## async/await
- Any promise we have, using ES2016, we can await.
- Same thing like calling then(), but without require any callback.
- await will pause the execution of any method till the value is available from promise.
- Therefore, using async/await will be like this.
```js
async function getFirstUser() {
    let users = await getUsers();
    return users[0].name;
}
```

- The way to catch error
```js
async function getFirstUser() {
    try {
        let users = await getUsers();
        return users[0].name;
    } catch (err) {
        return {
            name: 'default user'
        };
    }
}
```
### Pitfall in async/await
1、 Not Awaiting 
- If I don't await. You will get a promise instead of a value when you are using it.
```js
async function getFirstUser() {
    let users = getUsers(); //without await
    return users[0].name; // it will get a promise or null instead of users.
}
```
2、awaiting multiple values
- Promise.all will wait every child promise until resolve.
```js
let [foo, bar] = await Promise.all([getFoo(), getBar()]);
```
