# How to share flow types?

See: http://stackoverflow.com/questions/42911949/how-to-share-the-same-type-definition-in-two-files


To reproduce issue run:

```
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