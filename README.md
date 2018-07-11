# ES6 import, export, default cheatsheet

Javascript ES6 hỗ trợ export và import functions, variable từ một module khác.
Có 2 loại export: Name export và Default export.

## Named Export:
Trong Javascript ES6, Named export thường được dùng để ẽport nhiều thứ từ một module khác bằng
cách thêm keyword export vào trong cái khai báo của nó. Những cái export này được phân biệt
bằng tên của nó. Khi chung ta import những cái tên này(functions hoặc variables), chúng ta có
thể sử dụng cùng cái tên đó để tham chiếu đến functions hoặc variables tương ứng trong file export.

Hãy xem ví dụ dưới đây. Tôi đã tạo ra một file có tên là functions.js:

```javascript
//functions.js
//Cách 1:
//exporting một function
export function plusNumber(a,b) {
  return a + b;
}
//exporting một biến
export const pi = 3.14;
// Cách 2:
function multiplyNumber(a,b) {
  return a * b;
}
const otherPi = 3.14;
export {multiplyNumber, otherPi};
```

Bây giờ các functions và variables  đã có thể import được rồi. Chúng ta 
tạo một file là main.js và sau đó sẽ import những thứ đã export ở bên trên.

```javascript
//main.js
//Cách 1:
import {plusNumber, pi} from "functions";
//Cách 2:
import * as mathFuncs from "functionsFile";
console.log(mathFuncs.plusNumber, mathFuncs.pi);
```

## Default Export
Default export trong javascript es6 chỉ cho phép export duy nhất một đối tượng mặc định
trong mỗi module. Một export default có thể là function, có thể là variables, objecs..Cách thức như sau:
```javascript
//functions.js
export default function(x) {
  return x * x;
}
```

Sau đó ta import vào file khác rất tường minh như sau:
```javascript
//main.js
import batCuCaiTenNao from "functions";
```

## Exporting a class
Trong Javavascript ES6, class cũng có thể được export như là function.Ví dụ:

```javascript
//class.js
export default class MyClass {
  ...
}
```

```javascript
//main.js
import MyClass from "class";
```
