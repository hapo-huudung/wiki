# Abstract

## Abstract là gì?

* Lớp trìu tượng trước tiên nó chính là 1 lớp, nhưng nó được gọi là lớp trìu tượng bởi vì:
    * Các lớp khác khi kế thừa lớp trìu tượng **phải** định nghĩa các phương thức trìu tượng ấy
    
    * 1 Class chỉ kế thừa 1 Abstract class 
     
### Một số lưu ý khi sử dụng Abstract class
* Tất cả các phương thức của lớp abstract đều phải được khai báo là abstract và phải ở mức protected và public, không được ở mức private

* Lớp Abstract có thể có thuộc tính nhưng thuộc tính không được khai báo là abstract, và bạn không thể khởi tạo một biến của lớp Abstract được

    ````
    abstract class BaseClass
        {
         //phương thức ở mức protected 
         abstract protected function hello();
     
        //phương thức ở mức public 
        abstract protected function hi();   
        }
    ````
    
* Không thêm dòng lệnh nào bên trong các abstract phương thức
 
    ````
    abstract class BaseClass
    {
        // Phương thức này sai vì hàm hello là hàm abstract
        //nên không được code bên trong nó
         abstract protected function hello()
        {
            // dòng code
            echo 1;
        }
  
    }
    ````
    
* Không thể tạo một biến đối tượng mới của lớp Abstract
 
    ````
    abstract class BaseClass
    {
        abstract protected function hello();
    }
    
    // Sai vì BaseClass là lớp Abstract 
    // nên không khởi tạo mới được
    $base = new BaseClass();
    ````
    
* Mức truy cập các hàm của Abstract phải ở public hoặc protected để lớp kế thừa có thể Overwrite
 
* Các thuộc tính của Abstract không được khai báo abstract
  
    ````
    abstract class BaseClass
    {
        // Đúng
        public $name;
  
        // Sai vì các thuộc tính không được để ở dạng abstract
        abstract public $title;
  
        // Đúng
        abstract protected function hello();
  
        // Sai vì hàm abstract không thể ở private
        abstract private function hi_there();
    }
    ````
    
* Lớp kế thừa từ lớp Abstract phải Rewrite lại tất cả các hàm Abstract trong lớp Abstract, nếu không sẽ bị báo sai

    ````
    abstract class Person
    {
        protected $ten;
        protected $cmnd;
        protected $namsinh;
  
        abstract public function showInfo();
    }
  
    // Lớp này sai vì chưa viết lại hàm showInfo
    class CongNhan extends Person
    {
  
    }
  
    // Lớp này đúng vì ta đã khai báo, viết lại
    // đầy đủ các hàm abstract
    class SinhVien extends Person
    {
        public function showInfo(){
  
        
    }
    ````
