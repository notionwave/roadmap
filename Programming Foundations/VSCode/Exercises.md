This is a exercise module. In order to make the most out of it, please first try to answer the exercises (They should take between 1 mins to 15 mins) then check solutions. You can advance by group.

# Exercises

## Refactoring
### Exercise 1.1
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

## Navigation
### Exercise 2.1
As you work on a codebase more and more, you'll start to build a memory of file names and functions and components inside them.  
For example you remember that you had a Storybook Story called `DisabledMode` inside the `Button.stories.tsx`.  
Try to jump to a file and function inside the file with minimum keystrokes!!
This editor skill is very crucial when working with large codebases. It can significantly increase your development speed.  


<details markdown="1">
<summary><h1>Solutions</h1></summary>

## Refactoring
### Exercise 1.1
use: `F2` to refactor variable, class, function, etc names.  
don't use: `ctrl+d` or `cmd+d` or `ctrl+f2` (multi cursor select) they are not safe and they are manual.

🙏🏻 to @ARHariri for mentioning that this exists in VSCode.

## Navigation
### Exercise 2.1
Use `ctrl+p` or `cmd+p` to open `Go To File` prompt.  
Type your file name until it is the first suggested file in the prompt.  
The VSCode file search uses fuzzy search algorithm so typing `btn.st` would be enough to find `Button.stories.tsx` file.  
Now to jump to `DisabledMode` component type `@` and search the component.  
So by simply typing `btn.st @ Dis` and hitting Enter, you'll find the file.


</details>
