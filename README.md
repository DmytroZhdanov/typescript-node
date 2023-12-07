# TypeScript Node.js Express.js backend

This repository contains a TypeScript-based Node.js backend built on the Express.js framework, leveraging object-oriented programming through classes. The project structure is organized around classes to enhance modularity and maintainability. It includes predefined setups for various endpoints, middleware, and services, all written in TypeScript to ensure strong typing and scalability.

## Set up new project

First of all create a new folder for your project:
```bash
mkdir [project-name]
cd [project-name]
```

Install all neccessary libraries:
```bash
npm install express routing-controllers reflect-metadata class-transformer class-validator cors
```

Install types for libraries to ensure their correct operation with TypeScript:
```bash
npm install --save-dev @types/express @types/node ts-node tsconfig-paths typescript nodemon
```

Set up `tsconfig.json`. It should looks like this:
```json
{
  "compilerOptions": {
    "allowJs": false,
    "allowSyntheticDefaultImports": true,
    "emitDecoratorMetadata": true,
    "esModuleInterop": true,
    "experimentalDecorators": true,
    "isolatedModules": true,
    "lib": ["ES2021"],
    "module": "CommonJS",
    "moduleResolution": "node",
    "baseUrl": "./src",
    "outDir": "./dist",
    "skipLibCheck": true,
    "sourceMap": true,
    "strictNullChecks": true,
    "target": "es2019"
  }
}
```

Create a `main.ts` application file, you can describe it later.  
Let the main folder of the project be `src`, so add `main.ts` there.  
The full path will be `src/main.ts`.

It is convenient to use `nodemon` for development. Create and describe the `nodemon.json` configuration file:
```json
{
  "watch": ["src"],
  "ext": "ts",
  "exec": "ts-node -r tsconfig-paths/register src/main.ts"
}
```

Add a few scripts in `package.json`:
```json
"scripts": {
    "start": "node -r tsconfig-paths/register ./dist/main.js",
    "dev": "nodemon",
    "build": "tsc -p tsconfig.json"
  }
```

It should looks like this: 
```json
{
  "name": "ts-course-node",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "scripts": {
    "start": "node -r tsconfig-paths/register ./dist/main.js",
    "dev": "nodemon",
    "build": "tsc -p tsconfig.json"
  },
  "dependencies": {
    "class-transformer": "^0.5.1",
    "class-validator": "^0.14.0",
    "cors": "^2.8.5",
    "express": "^4.18.2",
    "reflect-metadata": "^0.1.13",
    "routing-controllers": "^0.10.4"
  },
  "devDependencies": {
    "@types/express": "^4.17.17",
    "@types/node": "^20.2.5",
    "nodemon": "^2.0.22",
    "ts-node": "^10.9.1",
    "tsconfig-paths": "^4.2.0",
    "typescript": "^5.1.3"
  }
}
```

You should have the following structure:
```
my-project/
├── src/
│   └── main.ts
├── node_modules/
├── nodemon.json
├── package.json
└── tsconfig.json
```
