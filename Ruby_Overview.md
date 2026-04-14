# **Ruby**

## 🔶 Mục lục
- **[Ruby cơ bản](#ruby-cơ-bản)**
- **[Cấu trúc dữ liệu và xử lý chuỗi](#cấu-trúc-dữ-liệu-và-xử-lý-chuỗi)**
- **[Lập trình hướng đối tượng trong Ruby](#lập-trình-hướng-đối-tượng-trong-ruby)**
- **[Chủ đề nâng cao và hệ sinh thái](#chủ-đề-nâng-cao-và-hệ-sinh-thái)**

---

## Ruby cơ bản

### Variables
- Ruby là ngôn ngữ dynamic typing, không cần khai báo kiểu trước.
- Tên biến thường dùng `snake_case`.

```ruby
name = "Thanh"
age = 24
price = 19.99
is_active = true
```

### Object Methods
- Trong Ruby, gần như mọi thứ đều là object.
- Bạn có thể gọi method trực tiếp trên object.

```ruby
puts "ruby".upcase        # RUBY
puts 10.next              # 11
puts 3.14159.round(2)     # 3.14
```

### Booleans and Predicate Methods
- Ruby có `true` và `false`.
- Predicate methods thường kết thúc bằng `?`, trả về boolean.

```ruby
puts 5.even?              # false
puts "".empty?            # true
puts "ruby".include?("u") # true
```

### Methods
- Định nghĩa method bằng `def ... end`.
- Có thể có giá trị trả về ngầm định (dòng cuối).

```ruby
def greet(name)
  "Xin chao, #{name}!"
end

puts greet("Thanh")
```

### Blocks
- Block là đoạn code truyền vào method, rất phổ biến trong Ruby.

```ruby
[1, 2, 3].each do |n|
  puts n * 2
end
```

### Conditionals
- Dùng `if`, `elsif`, `else`, `unless`, `case`.

```ruby
score = 8

if score >= 9
  puts "Xuat sac"
elsif score >= 7
  puts "Tot"
else
  puts "Can co gang"
end
```

### Strings
- String hỗ trợ interpolation với `#{}` khi dùng dấu `"`.

```ruby
name = "Thanh"
puts "Hello, #{name}"
puts 'Hello, #{name}' # khong interpolation
```

### Loops
- Ruby có `while`, `until`, `for`, và iterator như `times`, `each`.

```ruby
3.times { |i| puts "Lan #{i + 1}" }
```

### Debugging
- Dùng `puts`, `p`, và `pp` để debug nhanh.
- Ruby 3+ thường dùng `debug` gem (`require "debug"` và `binding.break`).

```ruby
require "debug"

value = 10
binding.break
puts value
```

---

## Cấu trúc dữ liệu và xử lý chuỗi

### Arrays I: Creation and Access
- Tạo mảng bằng `[]`, truy cập qua index.

```ruby
numbers = [10, 20, 30, 40]
puts numbers[0]   # 10
puts numbers[-1]  # 40
```

### Ranges
- Range biểu diễn khoảng giá trị: `1..5` (bao gồm 5), `1...5` (không gồm 5).

```ruby
puts (1..5).to_a.inspect
puts ("a".."d").to_a.inspect
```

### Arrays II: Iteration and Various Methods
- Các method quan trọng: `map`, `select`, `reject`, `reduce`, `uniq`, `sort`.

```ruby
arr = [1, 2, 2, 3, 4]
puts arr.uniq.inspect
puts arr.map { |n| n * 10 }.inspect
```

### Strings II
- Nâng cao với `split`, `strip`, `gsub`, `start_with?`, `end_with?`.

```ruby
text = "  Ruby,JavaScript,Python  "
languages = text.strip.split(",")
puts languages.inspect
puts "hello world".gsub("world", "Ruby")
```

### Object References and Copies
- Gán object tạo tham chiếu, không phải bản sao.
- Dùng `dup` hoặc `clone` khi cần copy.

```ruby
a = [1, 2, 3]
b = a
b << 4
puts a.inspect  # [1, 2, 3, 4]

c = a.dup
c << 5
puts a.inspect  # [1, 2, 3, 4]
puts c.inspect  # [1, 2, 3, 4, 5]
```

### Hashes I
- Hash lưu cặp `key => value`, tương tự dictionary/map.

```ruby
user = { name: "Thanh", age: 24 }
puts user[:name]
user[:city] = "HCM"
puts user.inspect
```

### Arrays III: Bonus Methods
- Một số method hữu ích: `flatten`, `zip`, `sample`, `count`, `bsearch`.

```ruby
nested = [1, [2, 3], [4, [5]]]
puts nested.flatten.inspect
puts [1, 2, 3].sample
```

### Blocks, Procs, and Lambdas
- `Proc` và `lambda` đều đóng gói block, nhưng khác về kiểm tra tham số và `return`.

```ruby
my_proc = Proc.new { |x| x * 2 }
my_lambda = ->(x) { x * 2 }

puts my_proc.call(3)
puts my_lambda.call(3)
```

---

## Lập trình hướng đối tượng trong Ruby

### Classes I: The Basics
- Tạo class bằng `class ... end`, khởi tạo bằng `initialize`.

```ruby
class Person
  attr_accessor :name, :age

  def initialize(name, age)
    @name = name
    @age = age
  end
end
```

### Classes II
- Dùng instance methods và class methods (`self.method_name`).

```ruby
class MathTool
  def self.square(n)
    n * n
  end
end

puts MathTool.square(5)
```

### Keyword Arguments
- Keyword arguments giúp code rõ ràng và linh hoạt.

```ruby
def register(name:, email:, admin: false)
  { name: name, email: email, admin: admin }
end

puts register(name: "Thanh", email: "thanh@example.com").inspect
```

### Classes III: Inheritance
- Kế thừa bằng `<`, gọi `super` để tái sử dụng logic lớp cha.

```ruby
class Animal
  def speak
    "Some sound"
  end
end

class Dog < Animal
  def speak
    "Woof!"
  end
end

puts Dog.new.speak
```

---

## Chủ đề nâng cao và hệ sinh thái

### Input and Output
- Nhập dữ liệu bằng `gets`, xuất bằng `puts`, `print`.

```ruby
print "Nhap ten: "
name = gets.chomp
puts "Xin chao, #{name}"
```

### Modules and Mixins
- `module` dùng để tổ chức code và mixin hành vi vào class.

```ruby
module Walkable
  def walk
    "Dang di bo..."
  end
end

class Robot
  include Walkable
end

puts Robot.new.walk
```

### Sets
- `Set` thuộc thư viện chuẩn (`require "set"`), dùng khi cần phần tử duy nhất.

```ruby
require "set"

tags = Set.new(["ruby", "rails", "ruby"])
puts tags.to_a.inspect # ["ruby", "rails"]
```

### Datetimes
- Ruby hỗ trợ `Time`, `Date`, `DateTime` (`require "date"`).

```ruby
require "date"

puts Time.now
puts Date.today
puts DateTime.now
```

### Regular Expressions
- Regex trong Ruby rất mạnh cho tìm kiếm và thay thế chuỗi.

```ruby
email = "user@example.com"
puts !!(email =~ /\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i)
```

### Exceptions
- Xử lý lỗi bằng `begin/rescue/ensure`.

```ruby
begin
  result = 10 / 0
rescue ZeroDivisionError => e
  puts "Loi: #{e.message}"
ensure
  puts "Ket thuc xu ly."
end
```

### Gems
- Gems là package trong Ruby ecosystem.
- Dùng `gem install` hoặc quản lý qua Bundler (`Gemfile` + `bundle install`).

```bash
gem install bundler
bundle init
bundle add rspec
bundle install
```

---

## Gợi ý lộ trình học nhanh
- Bước 1: Nắm vững `Variables`, `Methods`, `Conditionals`, `Loops`, `Strings`, `Arrays`, `Hashes`.
- Bước 2: Thành thạo `Blocks`, `Procs/Lambdas`, `Classes`, `Inheritance`, `Modules`.
- Bước 3: Học `Regex`, `Exceptions`, `IO`, `Datetime`, `Gems` để làm dự án thực tế.
- Bước 4: Làm project nhỏ (CLI app) để áp dụng tổng hợp.

