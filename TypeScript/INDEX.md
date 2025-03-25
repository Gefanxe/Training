# TypeScript 教育訓練課程

## 課程時間安排
- **上午 08:00 - 12:00**：TypeScript 基礎
- **下午 13:00 - 17:00**：TypeScript 進階

<div style="page-break-before: always"></div>

# 上午課程：TypeScript 基礎

## 1. TypeScript 介紹 (08:00 - 08:30)
- TypeScript 是什麼？
- 與 JavaScript 的區別
- 為什麼要使用 TypeScript？
- 安裝與設定 TypeScript

**示例程式碼**
```sh
npm install -g typescript
```

```ts
// 檢查 TypeScript 版本
ts --version
```

<div style="page-break-before: always"></div>

## 2. TypeScript 基本型別 (08:30 - 09:30)
- 基本型別：`number`, `string`, `boolean`
- 陣列與元組
- 枚舉 (`enum`)
- `any`、`unknown`、`void`、`never`

**示例程式碼**
```ts
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let tuple: [string, number] = ["hello", 10];

enum Direction {
  Up,
  Down,
  Left,
  Right
}
let dir: Direction = Direction.Up;
```

<div style="page-break-before: always"></div>

## 3. 函式與型別 (09:30 - 10:30)
- 函式型別
- 選擇性參數與預設參數
- Rest 參數

**示例程式碼**
```ts
function add(x: number, y: number): number {
  return x + y;
}

function greet(name: string = "Guest"): string {
  return `Hello, ${name}!`;
}

function sum(...numbers: number[]): number {
  return numbers.reduce((a, b) => a + b, 0);
}
```

<div style="page-break-before: always"></div>

## 4. 介面 (10:30 - 11:30)
- 介面 (`interface`)
- 可選與唯讀屬性
- 函式型別

**示例程式碼**
```ts
interface Person {
  name: string;
  age?: number;
}

let user: Person = { name: "Alice" };
```

<div style="page-break-before: always"></div>

## 5. 類別 (11:30 - 12:00)
- 類別 (`class`)
- 存取修飾符 (`public`, `private`, `protected`)
- 繼承與介面實作

**示例程式碼**
```ts
class Animal {
  constructor(public name: string) {}
  move(distance: number) {
    console.log(`${this.name} moved ${distance}m.`);
  }
}

class Dog extends Animal {
  bark() {
    console.log("Woof! Woof!");
  }
}

const dog = new Dog("Buddy");
dog.bark();
dog.move(10);
```

<div style="page-break-before: always"></div>

# 下午課程：TypeScript 進階

## 6. 泛型 (13:00 - 14:00)
- 泛型函式
- 泛型介面與類別
- 泛型約束

**示例程式碼**
```ts
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("Hello TypeScript");
```

<div style="page-break-before: always"></div>

## 7. TypeScript 模組與命名空間 (14:00 - 15:00)
- ES 模組 (`import` / `export`)
- 命名空間 (`namespace`)

**示例程式碼**
```ts
// math.ts
export function add(x: number, y: number): number {
  return x + y;
}

// main.ts
import { add } from "./math";
console.log(add(2, 3));
```

<div style="page-break-before: always"></div>

## 8. 型別進階 (15:00 - 16:00)
- 型別推論 (`infer`)
- 型別別名 (`type`)
- 交集與聯合型別
- 映射型別

**示例程式碼**
```ts
type Point = { x: number; y: number };
type Color = { color: string };
type ColoredPoint = Point & Color;

let cp: ColoredPoint = { x: 10, y: 20, color: "red" };
```

<div style="page-break-before: always"></div>

## 9. TypeScript 與 JavaScript 框架整合 (16:00 - 17:00)
- TypeScript 與 React
- TypeScript 與 Vue
- TypeScript 在 Node.js 的應用

**示例程式碼 (React)**
```tsx
type ButtonProps = {
  label: string;
};

const Button: React.FC<ButtonProps> = ({ label }) => {
  return <button>{label}</button>;
};

export default Button;
```


