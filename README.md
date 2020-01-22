# javascript.github.io
## Cách tách 1 file lớn thành các file chức năng nhỏ (theo cú pháp của ES5)
1. Giả sử các file chức năng nhỏ được đặt trong 1 folder tên là **ulti**
2. Mỗi file chức năng sau khi hoàn tất nhiệm vụ, đều bắt buộc phải truyền giá trị của mình cho các file khác sử dụng thông qua object có sẵn là **module.exports**, cú pháp được viết như sau: <br>
  <code>module.exports = tênBiến; </code>
  tênBiến là cái mà chúng ta muốn các file khác sử dụng, nó có thể là 1 giá trị primative như string, number, boolean, cũng có thể là object, mảng, hàm ....
3. File javascript nào muốn sử dụng file chức năng thì sử dụng cú pháp: <br>
<code> let tênBiến = require('đường-dẫn-đến-tên-file-chức-năng'); </code>
  tênBiến đặt tuỳ ý, có thể trùng hoặc không trùng với tênBiến ở các file con exports ra. 
  Giá trị của tên Biến nhận được là nội dung của biến tênBiến trong file con exports ra.
4. Trong folder **ulti** này tạo 1 file javascript chạy chính là **index.js** 
 * File index.js có nhiệm vụ import tất cả các file chức năng.
 
   <code> var tênBiến = require('./tênFile'); </code>
  
 * Và cuối cùng là exports ra toàn bộ các biến vào trong 1 object.

   <code> module.exports = {
              tênBiến:tênBiến
  } </code>

5. Lúc này, các file khác sử dụng folder ulti này bằng cú pháp sau: 
 <code> var tênBiến = require('./ulti').tênBiến; </code>


> Lưu ý: 
Nếu trong 1 file chức năng muốn exports ra nhiều giá trị được lưu trữ trong nhiều biến khác nhau. Thì mỗi biến sẽ trở thành 1 key trong object exports, cú pháp ghi như sau:

module.exports.a = a;
module.exports.b = b;

hoặc viết gọn là

module.exports = { a: a, b:b }

Vậy thì, khi file khác sử dụng file này sẽ require 2 lần: 

var a = require('./tên-file-có-export').a;

var b = require('./tên-file-có-export').b;
