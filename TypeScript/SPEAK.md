# TypeScript 教育訓練講稿

## **上午課程：TypeScript 基礎**

### **1. TypeScript 介紹 (08:00 - 08:30)**

#### **講師開場白**
大家好，歡迎來到 TypeScript 教育訓練課程。我是 [講師姓名]，今天我們將一起學習 TypeScript，這是一種強型別的 JavaScript 超集，幫助我們在開發時提升程式碼品質與可維護性。

### **2. TypeScript 基本型別 (08:30 - 09:30)**

#### **講師講解**
在 TypeScript 中，我們有一些與 JavaScript 相同的基本型別，例如 `number`、`string` 和 `boolean`。此外，還有一些 TypeScript 特有的型別，例如 `enum`、`tuple`、`any` 等。

#### **範例程式碼**
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

### **3. 函式與型別 (09:30 - 10:30)**

#### **講師講解**
函式是 JavaScript 中非常重要的一部分，而在 TypeScript 中，我們可以為函式的參數與回傳值指定型別，確保程式碼的正確性。

#### **範例程式碼**
```ts
function add(x: number, y: number): number {
  return x + y;
}

function greet(name: string = "Guest"): string {
  return `Hello, ${name}!`;
}
```

### **4. 介面 (10:30 - 11:30)**

#### **講師講解**
介面 (`interface`) 是 TypeScript 的核心特性之一，它讓我們可以定義物件的結構，確保程式碼的一致性與可讀性。

#### **範例程式碼**
```ts
interface Person {
  name: string;
  age?: number;
}

let user: Person = { name: "Alice" };
```

### **5. 類別 (11:30 - 12:00)**

#### **講師講解**
TypeScript 支援物件導向程式設計，提供 `class` 來定義類別，並支援存取修飾符 (`public`, `private`, `protected`)，以及繼承與介面實作。

#### **範例程式碼**
```ts
class Animal {
  constructor(public name: string) {}
  move(distance: number) {
    console.log(`${this.name} moved ${distance}m.`);
  }
}
```

---

## **下午課程：TypeScript 進階**

### **6. 泛型 (13:00 - 14:00)**

#### **講師講解**
泛型 (`Generics`) 讓我們能夠撰寫更具彈性的程式碼，使函式、介面或類別可以適用於多種型別。

#### **範例程式碼**
```ts
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("Hello TypeScript");
```

### **7. TypeScript 模組與命名空間 (14:00 - 15:00)**

#### **講師講解**
TypeScript 支援 ES 模組 (`import` / `export`)，讓我們可以拆分程式碼，增強可維護性。

#### **範例程式碼**
```ts
// math.ts
export function add(x: number, y: number): number {
  return x + y;
}

// main.ts
import { add } from "./math";
console.log(add(2, 3));
```

### **8. 型別進階 (15:00 - 16:00)**

#### **講師講解**
在這個章節，我們將探討 TypeScript 的進階型別，如型別推論 (`infer`)、型別別名 (`type`)、交集與聯合型別。

#### **範例程式碼**
```ts
type Point = { x: number; y: number };
type Color = { color: string };
type ColoredPoint = Point & Color;

let cp: ColoredPoint = { x: 10, y: 20, color: "red" };
```

### **9. TypeScript 與 JavaScript 框架整合 (16:00 - 17:00)**

#### **講師講解**
最後，我們將看看如何在現代前端與後端框架中應用 TypeScript，例如 React、Vue 和 Node.js。

#### **範例程式碼 (React)**
```tsx
type ButtonProps = {
  label: string;
};

const Button: React.FC<ButtonProps> = ({ label }) => {
  return <button>{label}</button>;
};

export default Button;
```

---

### **結語與 Q&A (17:00 結束)**

感謝大家今天的參與，希望這次的 TypeScript 教育訓練能幫助大家更熟悉這門語言。如果有任何問題，歡迎提出！

