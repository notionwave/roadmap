# Tips and Tricks and Best Practises to develop a Remix apps

## Lazy Loading Data
One of Remix biggest challenges for use was how to load data lazily e.g. pagination in a search page or loading tree structures branches.  

> TL;DR: multiple source of truth is BAD :)) try avoid it and completely be aware of where you store and how many time you store your data  

The further you go in the following list least less maintainable and anti-pattern your implementation will be:

  1. Use the current page loader to load the page's initial page data.  
     If data should be loaded when a user visits the page you should definitely use that page's native loader.
  2. Use Resource Loaders to lazily load data into your Remix
  3. Rely on Remix loader cache as much as possible (Try your best to put loaders' required parameters in their URLs as params or query params)
  4. Use components state to cache loader data (Instead of Jotai or State Management Libs). At least when user's change the page your data cache in state would be deleted.
  5. Avoid Jotai and State Management stores as much as possible, only use them if the data is only stored on store and not on Remix loader caches OR if you know the maintainance consequences of having multiple sources of truth for a data.
  6. Avoid using query libraries (like `React Query`, `Apollo Client`, `URQL` and even browser `fetch`) in the client and always define a new loader if you need to load some data. These libraries introduce multiple sources of truth using their cache. Even if they don't have builtin cache (like `fetch` or `axios`) they'll encourage you to store data in state and leave all the caching benefits of Remix.
