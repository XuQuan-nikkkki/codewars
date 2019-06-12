### First Non-repeating Character

#### Question
Write a function named first_non_repeating_letter that takes a string input, and returns the first character that is not repeated anywhere in the string.

For example, if given the input 'stress', the function should return 't', since the letter t only occurs once in the string, and occurs first in the string.

As an added challenge, upper- and lowercase letters are considered the same character, but the function should return the correct case for the initial letter. For example, the input 'sTreSS' should return 'T'.

If a string contains all repeating characters, it should return an empty string ("") or None -- see sample tests.

[Link](https://www.codewars.com/kata/52bc74d4ac05d0945d00054e/train/javascript)

#### My Answer

```javascript
function firstNonRepeatingLetter(s) {
  // Add your code here
  let result = ''
  let previousStr = ''
  let postStr = ''
  for(let i = 0; i < s.length; i ++) {
    previousStr = s.slice(0, i)
    postStr = s.slice(i+1)
    if(previousStr.toLowerCase().indexOf(s[i].toLowerCase()) < 0 && postStr.toLowerCase().indexOf(s[i].toLowerCase()) < 0) {
      result = s[i]
      break
    }
  }
  return result
}
```

#### Recommended Answer
```javascript
function firstNonRepeatingLetter(s) {
  for(var i in s) {
    if(s.match(new RegExp(s[i],"gi")).length === 1) {
      return s[i];
    }
  }
  return '';
}

```

```javascript
function firstNonRepeatingLetter(s) {
  var t=s.toLowerCase();
  for (var x=0;x<t.length;x++){
    if(t.indexOf(t[x]) === t.lastIndexOf(t[x])){
      return s[x];
    }
  }
  return "";
}

```
