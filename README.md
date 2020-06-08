## 1. Giới thiệu : CSS Preprocessor
- Cung cấp các quy tắc: nested rule, variable, mixin
- Viết mã CSS nhanh, chuyên nghiệp
- Tiết kiệm thời gian, giảm việc lặp code
- Dễ bảo trì, phát triển
- Tái sử dụng dễ dàng
- Cho dự án lớn
- Trang chủ sass-lang.com
- Có 2 cách viết SASS và SCSS

## 2. Cài đặt môi trường
- extention: sass, beautiful css/sass/scss

## 3. Chuyển đổi scss (sass) => css (biên dịch)
- Trang chủ sass https://sass-lang.com/install 
- Dùng tool : Koala, Scount => sau khi cài đặt chọn **compiled** để phiên dịch
- Dùng cmd : `npm install -g sass`<br>
Nếu dùng lệnh thì run `sass --watch input.scss output.css` để biên dịch <br>
(**input.scss** là file cần biên dịch, **output.css** là file sau khi compiled)

>Nếu chạy trong thư mục thì run `sass --watch 1-nested-rules/css:1-nested-rules `

## 4. Giới thiệu Output (trên koala tool)
- Nesting (mặc định) : viết lồng nhau
- Expanded - Format: cách viết css thông thường
- Compact: các định dạng css sẽ nằm trên 1 dòng
- Compressed: tất cả css nằm trên 1 đòng - tối ưu hóa

## 5. Nested Rules
- nested phân cấp thuộc tính cụ thể
- Dành cho thuộc tính css có cùng tiền tố

## 6. Referencing Parent

