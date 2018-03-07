# Interface 

## Interface là gì?

- Interface là một Template, nó không phải là một đối tượng mà chỉ là một bề nhìn bên ngoài mà nhìn vào đó ta có thể biết được tất cả hàm của đối tượng implement nó
 
1. Cách khai báo Interface 

   - Để khai báo một Interface ta dùng từ khóa **interface** để thay cho từ khóa **class**. Tất cả các hàm trong interface đểu ở dạng khai báo và **không được định nghĩa** (giống lớp abstract). Nếu một đối tượng implement một interface thì nó phải khai báo và định nghĩa tất cả các hàm trong Interface.

2. Phân biệt Interface và Abstract 
    - Bản chất của Interface và Abstract là khác nhau
 
        Interface | Abstract 
        --- | ---
        Không phải là lớp cụ thể mà là khuân mẫu để cho một đối tượng implement nó | Là một lớp cụ thể, có đầy đủ tính chất của một đối tượng, có thể gọi, định nghĩa các hàm trong nó 
        Không thể tạo biến interface | Không thể tạo biến abstract
 
 3. Ví dụ
    - Định nghĩa hằng số bị sai 
    
        ````
        interface A
        {
        const ConstA = 'Freetuts.net';
        }
   
        // Lớp này sai vì không thể định nghĩa lại hằng
        class B implements A
        {
         const ConstA = 'Other Name';
        }
      
        // Lớp này đúng
        class D implements A
        {
        }
        ````
        
    - Định nghĩa hàm trong template bị sai 
    
        ````
        // Khai báo một Interface
        interface DogTemplate
        {
         // Hàm này đúng vì ta chỉ khai báo mà không có định nghĩa
        public function Run();
   
        // Hàm này sai vì ta đã định nghĩa cho nó
        public function Eat(){
   
        }
        }
        ````
        
    - Định nghĩa mức truy cập sai 
    
        ````
        // Template
        interface DogTemplate
        {
            public function Run();
      
             public function Eat();
        }
      
         // Lớp Dog
        class Dog implements DogTemplate
        {
            // Hàm này sai vì cấp độ truy cập
            // của hàm run bên template là public
            // mà trong hàm này ta lại khai báo là private
            private function Run(){
      
            }
      
            // Hàm này đúng
            public function Eat(){
      
            }
        }
        ````
        
    - Bị thiếu hàm 
    
        ````
        // Template
        interface DogTemplate
        {
            public function Run();
      
            public function Eat();
        }
      
        // Lớp Dog
        // Sai vì thiếu hàm Run
        class Dog implements DogTemplate
        {
            public function Eat(){
        
            }
        }   
         ````
    
### Tính kế thừa trong Interface 

- Interface không phải là một lớp nhưng cũng có tính chất kế thừa
    - 1 interface A kế thừa 1 interface B thì lúc này đối tượng nào inplement lớp A thì nó phải định nghĩa các hàm mà cả 2 lớp A và B đã khai báo
    
- Ví dụ:

    ````
    interface A {
        public function funcA();
    }
      
    interface B extends A
    {
        public function funcB();
    }
      
    // Lớp này đúng vì nó khai báo đầy
    // đủ các hàm trong A và B
    class C implements B
    {
        public function funcA()
        {
      
        }
      
        public function funcB()
        {
      
        }
    }
      
    // Lớp này sai vì nó khai báo mỗi hàm funcA
    class D implements B
    {
        public function funcA()
        {
      
        }
    }
    ```` 
