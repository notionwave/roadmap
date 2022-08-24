This is a exercise module. In order to make the most out of it, please first try to answer the exercises (They should take between 1 mins to 15 mins) then check solutions. You can advance by group.

# Exercises

## Refactoring
### Exercise 1
How to change a variable, class, function, property, etc name in all the places that is used?  
We want to change `count` to `size` in all the 3 places that it is used.

```ts
// file: getCount.ts
export const count = 0;
export const getCount = () => {
  return count;
}
```

```ts
// file: useCount.ts
import { count } from './getCount.ts';
export const getCount = () => {
  return count;
}
```


<details markdown="1">
<summary><h1>Solutions</h1></summary>

### Exercise 1
use: `F2` to refactor variable, class, function, etc names.  
don't use: `ctrl+d` or `cmd+d` or `ctrl+f2` (multi cursor select) they are not safe and they are manual.

🙏🏻 to @ARHariri for mentioning that this exists in VSCode.

</details>
