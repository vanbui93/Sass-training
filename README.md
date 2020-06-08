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
Nếu dùng lệnh chạy trực tiếp trên folder css <br>
thì run `sass --watch input.scss output.css` để biên dịch <br>
(**input.scss** là file cần biên dịch, **output.css** là file sau khi compiled)

>Nếu chạy trong thư mục **lession03-css-extensions** thì run `sass --watch 1-nested-rules/css:1-nested-rules `

## 4. Giới thiệu Output (trên koala tool)
- Nesting (mặc định) : viết lồng nhau
- Expanded - Format: cách viết css thông thường
- Compact: các định dạng css sẽ nằm trên 1 dòng
- Compressed: tất cả css nằm trên 1 đòng - tối ưu hóa

## 5. Nested Rules
- nested phân cấp thuộc tính cụ thể
- Dành cho thuộc tính css có cùng tiền tố

## 6. Parent Selector
- Nested property

```css
p.content {
  margin: 20px;
  padding: 20px;
  border: {
    top: solid 3px red;
    bottom: solid 3px blue;
    left: solid 3px green;
    right: solid 3px pink;
  }
}
```
- Reference parent : tham chiếu đến thành phần cha

```css
div.container {
  button {
    background-color: red;
    color: white;
    border: none;
    
    //thao tác với button ==>   &:hover = button:hover
    
    &:hover, &:active, &:focus {
      background-color: yellowgreen;
    }
  }
```
- Adding Suffixes - Thêm hậu tố

scss

```css
#content {
  width: 200px;
  color: white;

  //& = #content-left

  &-left{
    width: 50px;
    height: 50px;
    background-color: black;
  }
}
```
css

```css
div.container #content {
  width: 200px;
  color: white;
}
div.container #content-left {
  width: 50px;
  height: 50px;
  background-color: black;
}
```

## 7. In SassScript
- Thực hiện ghi chú: các đoạn mã lệnh không được thực thi
- Cú pháp : <br>
 --Single line: //ghi chú trên 1 dòng<br>
 --Multi line : /*Nội dung có thể xuống dòng*/
> Lưu ý: chỉ Multi line mới được dịch và hiển thị tại css

## SassScript : Variables (Biến)
- Cú pháp: $name: value
- Tái sử dụng
- Giảm thiểu việc lặp code
- Phạm vi : Toàn cục và cục bộ

```css
$primary_color: #0097A7;
p.content {
  background-color: $primary_color;
}
```

- Sử dụng biến cục bộ (trong 1 selector riêng) cho toàn cục dùng thêm !global
```css
$text-color: pink !global;
```

## 8. SassScript : Data Types & Operator
- numbers: 1.2, 14, 10px, 15em,...
- string: "value", 'value', value
- colors: red, #cccccc, rgba(255,0,0,0)
- booleans: true, false
- nulls
- lists
- maps (key1: value1, key2: value2)

**Sử dụng toán tử cộng để nối chuỗi**
```css
$background-url: "../images/";
div.bg {
  background-url: $background-url + "div-bg.png";
}
```

**Sử dụng toán tử nhân**
```css
$size: 16;
$text_size: $size*2px;
$text_size_string: 15+ px;

p {
  font: {
    size: $text_size;
  };
}
p.description {
  font: {
    size: $text_size_string;
  }
}
```
## 9. SassScript: Interpolation
- Lấy giá trị các biến lưu trữ
- Áp dụng: selector
- cú pháp : `#{$name}`

```css
$name: content;
div.#{$name} {
  background-color: red;
}
```