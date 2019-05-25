### Format a string of names like ‘Bart, Lisa & Maggie’

#### Question

Given: an array containing hashes of names

Return: a string formatted as a list of names separated by commas except for the last two names, which should be separated by an ampersand.

Examples:

```js
list([ {name: 'Bart'}, {name: 'Lisa'}, {name: 'Maggie'} ])
// returns 'Bart, Lisa & Maggie'

list([ {name: 'Bart'}, {name: 'Lisa'} ])
// returns 'Bart & Lisa'

list([ {name: 'Bart'} ])
// returns 'Bart'

list([])
// returns ''
```

Note: all the hashes are pre-validated and will only contain A-Z, a-z, '-' and '.'.



#### My Answer

```js
function list(names){
  const finalNames = names.map(name => name.name)
  return finalNames.slice(0, finalNames.length-2).concat(finalNames.slice(finalNames.length-2).join(' & ')).join(', ')
}
```



#### Recommended Answer

```js
function list(names){
  return names.reduce(function(prev, current, index, array){
    if (index === 0){
      return current.name;
    }
    else if (index === array.length - 1){
      return prev + ' & ' + current.name;
    } 
    else {
      return prev + ', ' + current.name;
    }
  }, '');
 }
```





