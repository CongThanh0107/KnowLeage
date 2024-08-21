# **Clean Code**

## 🔷 Mục lục
- **[Giới Thiệu Về Clean Code](#-giới-thiệu-về-clean-code)**
- **[Các Nguyên Tắc Của Clean Code](#rule)**

## 🔷 Giới Thiệu Về Clean Code

### Clean Code

- **Clean Code (Mã sạch)** là một khái niệm trong lập trình, được phát triển bởi Robert C. Martin, hay còn được biết đến với tên gọi Uncle Bob. Mục tiêu của Clean Code là viết mã nguồn có thể dễ dàng đọc, hiểu và bảo trì. Mã nguồn sạch không chỉ giúp lập trình viên tiếp cận và thay đổi mã dễ dàng hơn mà còn giảm thiểu lỗi và thời gian phát triển trong tương lai. 

### Tại sao Clean Code quan trọng?

- **Dễ Duy Trì (Maintainable):** Mã sạch giúp lập trình viên dễ dàng thực hiện các thay đổi mà không làm ảnh hưởng đến hệ thống. Điều này rất quan trọng trong việc phát triển phần mềm kéo dài, nơi mà yêu cầu có thể thay đổi thường xuyên

- **Giảm Thiểu Lỗi (Error Reduction):** Mã sạch thường ít có lỗi hơn vì nó rõ ràng và dễ hiểu. Giảm lượng mã có thể dẫn đến việc giảm số lượng lỗi.

- **Cải Thiện Tính Đọc (Readability Improvement):** Một mã được viết tốt sẽ dễ dàng tiếp cận hơn bởi các lập trình viên khác, hoặc thậm chí là chính tác giả trong tương lai. Điều này giúp tăng cường khả năng giao tiếp và hợp tác giữa các thành viên trong nhóm phát triển.

- **Thúc Đẩy Tính Tái Sử Dụng (Reusability):** Mã sạch thường được tổ chức tốt hơn, cho phép các phần của nó dễ dàng tái sử dụng trong các dự án khác.

## 🔷 Các Nguyên Tắc Của Clean Code

### 1. Tên Biến, Hàm, và Lớp (Naming Variables, Functions, and Classes)

  #### Đặt tên (Naming)

  - Đặt tên các thứ (**_= variables, properties, functions, methods, classes_**) một cách chính xác và dễ hiểu nếu là một phần cực kỳ quan trọng của việc viết mã sạch.

  - Tên có một mục đích đơn giản: Chúng phải mô tả những gì được lưu trữ trong một biến hoặc thuộc tính hoặc chức năng của một hàm hoặc phương thức hoặc loại đối tượng nào sẽ được tạo khi khởi tạo một lớp.

  #### Quy tắc đặt tên (Naming Rules)

  - **Variables & Properties:** 
    + Các biến và thuộc tính chứa dữ liệu : numbers, text (strings), boolean values, objects, lists, arrays, maps
    + Các biến và thuộc tính thường phải có một danh từ làm tên. **Ví dụ:** **_user, product, customer, database, transaction,..._**
    + Ngoài ra, bạn cũng có thể sử dụng một cụm từ ngắn có tính từ - thường để lưu trữ các giá trị boolean. **Ví dụ:** **_isValid, didAuthenticate, isLoggedIn, emailExists,..._**
    + **Ví dụ:**
      ```Python
        # Unclean Code  
        def calc(a, b):  
          return a * b  
      ```
      ```Python
        #Clean Code
        def calculateArea(length, width):  
          return length * width  
      ```

  - **Functions & Methods:** Các hàm và phương thức có thể được gọi để thực thi một số mã. Điều đó có nghĩa là họ thực hiện các nhiệm vụ và hoạt động.
    + Do đó, các hàm và phương thức thường phải nhận một động từ làm tên. **Ví dụ:** **_login(), createUser(), database.insert(), log(),..._**
    + Ngoài ra, các hàm và phương thức cũng có thể được sử dụng để chủ yếu tạo ra các giá trị - sau đó, đặc biệt là khi tạo các giá trị boolean, bạn cũng có thể sử dụng các cụm từ ngắn có tính từ. **Ví dụ:** **_isValid(...), isEmail(...), isEmpty(...),..._**
    + Nên tránh những tên như: **_email(), user(),..._** Những tên này nghe giống như thuộc tính. Thay vào đó, hãy ưu tiên **_getEmail(),..._**
    + Giống như Variables & Properties, nếu bạn có thể cụ thể hơn thì việc sử dụng những tên cụ thể hơn như vậy thường hợp lý hơn. **Ví dụ:** **_createUser()_** thay vì chỉ **_create()_**.
    + **Ví dụ:**
    ```Python
      # Unclean Code  
      def doStuff(x):  
        return x + 5  
    ```
    ```Python
      #Clean Code
      def incrementByFive(number):  
        return number + 5  
    ```

  - **Classes:** Các lớp được sử dụng để tạo các đối tượng (trừ khi đó là một static class).
    + Do đó tên class phải mô tả loại đối tượng mà nó sẽ tạo. Ngay cả khi đó là một ltatic class (tức là nó sẽ không được khởi tạo), vẫn sẽ sử dụng nó như một loại vùng chứa cho các phần dữ liệu và/hoặc chức năng khác nhau.
    + Tên class tốt cũng giống như tên biến và thuộc tính tốt nó thường là **danh từ**. **Ví dụ:** **_User, Product, RootAdministrator, Transaction, Payment,..._**
    + **Ví dụ:**
    ```Python
      # Unclean Code  
      class A:  
        def __init__(self):  
            self.value = 10  
            
        def getValue(self):  
            return self.value   
    ```
    ```Python
      #Clean Code
      class Circle:  
        def __init__(self, radius):  
          self.radius = radius  

        def getArea(self):  
          return 3.14 * self.radius * self.radius  

    ```

  #### Tránh đặt tên chung chung (Avoid Generic Names)

    - Trong hầu hết các trường hợp, bạn nên tránh các tên chung chung như **_hand(), process(), data, item,..._**

### 2. Cấu Trúc và Tổ Chức Mã Nguồn (Structure and Organization of Code)

### 3. Comments & Formatting (Ghi Chú và Định dạng)
  - Comment có thể giúp dễ đọc code hơn. Tuy nhiên trong thực tế điều ngược lại thường xảy ra. Mặt khác, định dạng mã phù hợp (thêm dòng trống,..) sẽ giúp ích rất nhiều cho việc đọc và hiểu mã.

### 4. Xử Lý Lỗi (Error Handling)

### 5. Kiểm Thử (Testing)

### 6. Tổ Chức Mã (Code Organization)