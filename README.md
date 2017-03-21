# How to share flow types?

See: http://stackoverflow.com/questions/42911949/how-to-share-the-same-type-definition-in-two-files


To reproduce issue run:

```
yarn
yarn run flow
```

## Problem

Flow returns this as the output:

```
src/file_a.js:3
  3: const randomVariable: MySharedType = {thing: true};
                           ^^^^^^^^^^^^ identifier `MySharedType`. Could not resolve name

src/file_b.js:3
  3: const anotherRandomVariable : MySharedType = {thing: true};
                                   ^^^^^^^^^^^^ identifier `MySharedType`. Could not resolve name

```

How do I get flow to allow me to use the `MySharedType` inside the `/flow/typeExtensions` directory?


## Solution

Flow doesn't recognize changes to shared `[libs]` files. So to fix this you simply need to restart the flow server:

```
./node_modules/.bin/flow stop
./node_modules/.bin/flow start
```