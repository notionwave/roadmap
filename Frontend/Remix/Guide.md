# Tips and Tricks and Best Practises to develop a Remix apps

## Lazy Loading Data
One of our challenges in using Remix was how to load data **lazily** e.g. pagination in a search page or loading tree structures branches.  

> TL;DR: multiple sources of truth is BAD :)) try avoiding them and completely beware of where and how many times you store your data. Beware that caches are also considered a data storage.  

The further you go in the following list less maintainable and anti-pattern your implementation will be:

  1. Use the current **page's loader function** to load the initial page data. If data should already be loaded when a user visits the page you should definitely use that page's native loader to load data.
  2. Use **Resource Loaders** and `useFetcher` to lazily load data into your Remix app.
  3. Rely on Remix **loader cache** as much as possible (Try your best to put loaders' required parameters in their URL params)
  4. Use **components state** to cache loader data (Instead of Jotai or State Management Libs). At least when user's change the page your data cache (that lives in state) will be deleted.
  5. **Avoid Jotai and State Management stores** as much as possible, only use them if the data is only stored on store and not on Remix loader caches OR if you know the maintainance consequences of having multiple sources of truth for a data. Simple rule of thumb is: if it is stored server-side use Remix Loaders!
  7. **Avoid using query libraries** (like `React Query`, `Apollo Client`, `URQL` and even browser `fetch`) in the client and always define a new loader if you need to load some data. These libraries introduce multiple sources of truth using their cache. Even if they don't have builtin cache (like `fetch` or `axios`) they'll encourage you to store data in state and leave all the caching benefits of Remix.
