# **Type Script**

## 🔷 Mục lục
- **[TypeScript Basic & Basic Types]**
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