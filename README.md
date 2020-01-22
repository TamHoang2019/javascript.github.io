# javascript.github.io
## Cách tách 1 file lớn thành các file chức năng nhỏ (ES5)
1/ Các file chức năng nhỏ được đặt trong 1 folder, đặt tên là ulti
2/ Trong folder **ulti** này sẽ có 1 file javascript chạy chính là **index.js** 
 - File index.js có nhiệm vụ import các file chức năng.
 - Để khi các file javascript nào cần sử dụng các file chức năng, thì chỉ cần require đến file index.js này là được.
3/ Như vậy, ở các file chức năng luôn phải có exports theo cú pháp là:
