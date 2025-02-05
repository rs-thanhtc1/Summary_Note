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
    + **Number** :
        ```TypeScript
        let age: number = 25;  

        ```
    + **String** :
        ```TypeScript
        let name: string = "Cong Thanh";  

        ```
    + **Boolean** :
        ```TypeScript
       let isActive: boolean = true;

        ```
    + **Array** :
        ```TypeScript
       let numbers: number[] = [1, 2, 3, 4, 5];

        ```
    + **Tuple** : 
        ```TypeScript
       let person: [string, number] = ["Alice", 30];

        ```
    + **Enum** 
        ```TypeScript
       enum Direction {  
            Up,  
            Down,  
            Left,  
            Right  
        }  

        let move: Direction = Direction.Up;
        
        ```
    + **Any** :
        ```TypeScript
        let variable: any = 5;  
        variable = "Now I'm a string";  

        ```