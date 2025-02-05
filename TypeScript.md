# **Type Script**

## 🔷 Mục lục
- **[TypeScript Basic & Basic Types](#typescript--basic-types)**
- **[The TypeScript Compiler (and its Configuration)]**
- **[ Next-generation JavaScript & TypeScript]**
- **[ Classes & Interfaces]**
- **[ Advanced Types]**
- **[ Generics]**
- **[ Decorators]**

### TypeScript & Basic Types

- **TypeScript** là một ngôn ngữ lập trình mã nguồn mở được phát triển bởi Microsoft. Nó là một siêu tập của JavaScript, có nghĩa là bất kỳ mã JavaScript hợp lệ nào cũng đều là mã TypeScript hợp lệ. TypeScript bổ sung thêm một số tính năng mới, với điểm nổi bật là hệ thống kiểu tĩnh.TypeScript hỗ trợ các khái niệm lập trình hướng đối tượng như lớp, kế thừa, và giao diện.
 - **Basic Types:** 

    + **Number** : dùng để đại diện cho các giá trị số.
        ```TypeScript
        let age: number = 25;  

        ```

    + **String** : dùng để đại diện cho các chuỗi văn bản.
        ```TypeScript
        let name: string = "Cong Thanh";  

        ```

    + **Boolean** : dùng để đại diện cho các giá trị đúng (true) hoặc sai (false).
        ```TypeScript
       let isActive: boolean = true;

        ```

    + **Array** : dùng để đại diện cho các mảng. Bạn có thể lưu trữ nhiều giá trị cùng kiểu trong một mảng.
        ```TypeScript
       let numbers: number[] = [1, 2, 3, 4, 5];

        ```

    + **Tuple** : cho phép bạn định nghĩa một mảng với các kiểu khác nhau.
        ```TypeScript
       let person: [string, number] = ["Cong Thanh", 30];

        ```

    + **Enum** : cho phép bạn định nghĩa một tập hợp các hằng số có tên.
        ```TypeScript
       enum Direction {  
            Up,  
            Down,  
            Left,  
            Right  
        }  

        let move: Direction = Direction.Up;

        ```

    + **Any** : cho phép biến có thể chứa bất kỳ loại dữ liệu nào. Tuy nhiên, việc sử dụng any có thể làm giảm tính an toàn của mã.
        ```TypeScript
        let variable: any = 5;  
        variable = "Now I'm a string";  

        ```

    + **Void** : thường được sử dụng để chỉ rằng một hàm không trả về giá trị.
        ```TypeScript
       function logMessage(message: string): void {  
            console.log(message);  
        }  

        ```

    + **Null & Undefined** : là các kiểu có thể được sử dụng để chỉ ra trạng thái không có giá trị.
       ```TypeScript
        let nullableVar: null = null;  
        let undefinedVar: undefined = undefined;  

        ```

    + **Never** : được sử dụng để chỉ những hàm không bao giờ trả về giá trị (ví dụ: ném lỗi hoặc vòng lặp vô hạn).
       ```TypeScript
        function throwError(message: string): never {  
            throw new Error(message);  
        } 

        ```

### The TypeScript Compiler (and its Configuration)

- **The TypeScript Compiler** : Trình biên dịch TypeScript  là công cụ giúp biên dịch mã TypeScript thành mã JavaScript. `tsc` chuyển đổi mã TypeScript sang JavaScript mà trình duyệt hoặc môi trường thực thi có thể hiểu được.

- **Setting TypeScript**: Có thể cài đặt TypeScript toàn cầu hoặc trong một dự án cụ thể thông qua npm (Node Package Manager).
    ```bash
        # Cài đặt TypeScript toàn cầu  
        npm install -g typescript  
        
        # Cài đặt TypeScript trong dự án  
        npm install --save-dev typescript  
    ```

- **Configuration** : có thể tạo một tệp cấu hình cho `tsc` để định nghĩa các tùy chọn biên dịch trong một dự án. Tệp cấu hình này thường được đặt tên là `tsconfig.json`
    + Dưới đây là một số tùy chọn phổ biến trong tệp `tsconfig.json`:
     ```json
        {  
        "compilerOptions": {  
            "target": "ES6",                      // Chọn phiên bản ECMAScript mà bạn muốn biên dịch  
            "module": "commonjs",                 // Chọn hệ thống module  
            "outDir": "./dist",                   // Thư mục đầu ra cho các tệp JavaScript  
            "rootDir": "./src",                   // Thư mục gốc chứa mã TypeScript  
            "strict": true,                        // Bật tất cả các tùy chọn kiểm tra nghiêm ngặt  
            "esModuleInterop": true,               // Cung cấp tính tương thích với các module ES  
            "skipLibCheck": true,                  // Bỏ qua kiểm tra kiểu cho các thư viện  
        },  
        "include": [  
            "src/**/*"                             // Đường dẫn tới mã nguồn TypeScript  
        ],  
        "exclude": [  
            "node_modules",                        // Thư mục loại trừ  
            "**/*.spec.ts"                         // Loại trừ các tệp thử nghiệm  
        ]  
        }  
     ```
- **Một số Tùy chọn Quan trọng trong `tsconfig.json`** :
    + `target`: Xác định phiên bản ECMAScript mà bạn muốn biên dịch đến (ví dụ: `ES5`, `ES6`, `ESNext`)
    + `module`: Chọn hệ thống module (ví dụ: `commonjs`, `esnext`, `amd`).
    + `outDir`: Xác định thư mục để lưu các tệp JavaScript đã biên dịch.
    + `rootDir`: Đặt thư mục gốc cho mã nguồn TypeScript.
    + `strict`: Bật tất cả các cài đặt hệ thống kiểu nghiêm ngặt
    + `esModuleInterop`: Giúp để tương thích với mã JavaScript truyền thống.