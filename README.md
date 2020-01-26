# Node-Typescript
Get node and npm (https://nodejs.org/en/)

1. Setup a Node.js project package.json: 
```bash 
npm init -y
```

2. Add TypeScript and node.d.ts 
```bash 
npm install typescript  @types/node -D  
```
3. Init a tsconfig.json for TypeScript options with a few key options in your tsconfig.json
```bash
#if needed (run npm install -g npx)
npx tsc --init --rootDir src --outDir lib --esModuleInterop --resolveJsonModule --lib es6,dom --module commonjs
```

4. Create source files dir:
```
mkdir src && echo "console.log('Hello world')" >> src/index.ts
```

5. Add tsc and nodemon :
(https://www.npmjs.com/package/nodemon)

```bash
npm install ts-node -D #or -g
npm install nodemon -D 
```

6. Configure package.json scripts:
```js
...
"scripts": {
    "start": "npm run build:watch",
    "build": "tsc -p .",
    "build:watch": "nodemon --watch 'src/**/*.ts' --exec 'ts-node' src/index.ts"
},
...
```

## Testing
1. Install Jest for typescript
(https://www.npmjs.com/package/ts-jest)
```bash
   npm i -D jest ts-jest @types/jest

   npx ts-jest config:init

   mkdir __tests__
   
```

2. edit package.json 
```js
  ...
    "scripts": {
    ...
    "test": "jest"
  },
  ...
```

## Bonus 

### Node version manager
https://github.com/tj/n

```bash
npm i -g n 
```

