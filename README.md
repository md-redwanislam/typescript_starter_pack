# TypeScript + Node.js + Express Setup

## 1. Initialize Project

```bash
yarn init
```

## 2. Install Express

```bash
yarn add express
```

## 3. Install Development Dependencies

```bash
yarn add -D typescript nodemon @types/node @types/express ts-node
```

## 4. Initialize TypeScript Configuration

```bash
npx tsc --init
```

---

## tsconfig.json

Create or update `tsconfig.json`:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

---

## nodemon.json

Create a `nodemon.json` file in the project root:

```json
{
  "watch": ["src"],
  "ext": "ts,json",
  "ignore": ["src/**/*.spec.ts"],
  "exec": "ts-node ./src/index.ts"
}
```

---

## Project Structure

```text
project-root/
│
├── src/
│   └── index.ts
│
├── dist/
│
├── nodemon.json
├── tsconfig.json
├── package.json
└── yarn.lock
```

---

## Run Development Server

Add the following script to `package.json`:

```json
{
  "scripts": {
    "dev": "nodemon"
  }
}
```

Start the server:

```bash
yarn dev
```
