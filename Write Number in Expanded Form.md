### Write Number in Expanded Form

You will be given a number and you will need to return it as a string in [Expanded Form](https://www.mathplacementreview.com/arithmetic/whole-numbers.php#expanded-form). For example:

```javascript
expandedForm(12); // Should return '10 + 2'
expandedForm(42); // Should return '40 + 2'
expandedForm(70304); // Should return '70000 + 300 + 4'
```

NOTE: All numbers will be whole numbers greater than 0.





#### My Answer：

```js
function expandedForm() {
  let result = [];
  let len = (num+"").length;
  for(let i = len; i >=0; i --) {
    if(num / Math.pow(10, i) >= 1) {
      let partRes = Math.floor(num/Math.pow(10, i))*Math.pow(10,i);
      result.push(partRes);
      num -= partRes;
    }
  }
  return result.join(" + ");
}
```





#### Recommended Answers:

```js
const expandedForm = n => n.toString()
                            .split("")
                            .reverse()
                            .map( (a, i) => a * Math.pow(10, i))
                            .filter(a => a > 0)
                            .reverse()
                            .join(" + ");
```

