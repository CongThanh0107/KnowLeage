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

  #### Bad Comment 
  - Có rất nhiều comment không hay mà một số dev có thể thêm vào mã của mình. Trong trường hợp tốt nhất, "**bad**" có nghĩa là "**dư thừa**" trong trường hợp xấu nhất, nó có nghĩa là "**khó hiểu**" hoặc thậm chí là "**gây hiểu lầm**".

  - **Dividers & Markers:**

    + **Ví dụ:**
      ```js
      // !!!!!!!
      // CLASSES
      // !!!!!!!

      class User { ... }

      class Product { ... }

      // !!!!!!!
      // MAIN
      // !!!!!!!

      const user = new User(...);
      ```

    + Bộ chia và điểm đánh dấu là không cần thiết. Nếu code được viết một cách rõ ràng (tức là bạn sử dụng tên riêng, v.v.), thì rõ ràng các phần mã khác nhau nói về điều gì.Không cần thêm điểm đánh dấu cho việc đó. Chúng chỉ dừng quá trình đọc và khiến việc phân tích tệp mã trở nên khó khăn hơn.

 - **Redundant Information:**

   + **Ví dụ:**
      ```js
      function createUser() {   // creating a new user
        ...
      }
      ```
   + Những comment như trong ví dụ này không thêm gì cả. Thay vào đó, bạn dừng lại và dành thời gian đọc chúng - chỉ để tìm hiểu những gì bạn đã biết vì mã đã sử dụng tên riêng. Comment này có thể hữu ích nếu bạn đặt tên kém

 - **Commented Out Code:**

   + **Ví dụ:**
      ```js
        function createUser() {
          ...
        }

        // function createProduct() {

        // ...

        // }
      ```
   + Tránh việc Comment Out Code. Thay vào đó hãy xoá nó, nó có thể làm lộn xộn tệp mã ...
 
 - **Misleading Comments:**

   + **Ví dụ:**
      ```js
      function login() { // create a new user
        ...
      }
      ```
   + Có lẽ loại comment tệ nhất là những comment thực sự đánh lừa người đọc. Hãy hạn chế viết sai các comment như thế này

  #### Good Comment
   - **Legal Information:** Trong một số dự án và/hoặc công ty, bạn có thể được yêu cầu thêm thông tin pháp lý vào tệp mã của mình.
     + **Ví dụ:**
     ```js
      // (c) Academind GmbH
     ```
   - **"Required" Explanations:** Trong một số trường hợp việc thêm các giải thích bổ sung bên cạnh mã của bạn sẽ có ích - ngay cả khi bạn đặt tên chính xác cho mọi thứ.
     + **Một ví dụ điển hình là biểu thức chính quy:** Mặc dù tên passRegex cho chúng ta biết rằng biểu thức chính quy này sẽ được sử dụng để xác thực mật khẩu nhưng vẫn chưa rõ quy tắc cụ thể nào sẽ được áp dụng.
     ```js
       # Min. 8 characters, at least: one letter, one number, one special character const passwordRegex = /^(?=.* [A-Za-z])(?=.*\d)(?=.*[@$!%*#?&]) [A-Za-z\d@$!%*#? &]{8,}$/
     ```
   
   - **Warnings:** Ngoài ra, trong một số trường hợp hiếm hoi, cảnh báo bên cạnh một số mã có thể có ý nghĩa, chẳng hạn như nếu kiểm thử đơn vị có thể mất nhiều thời gian để hoàn thành hoặc nếu một chức năng nhất định không hoạt động trong một số môi trường nhất định.
     + **Ví dụ:**
     ```js
      function fetchTestData() {...} // requires local dev server
     ```
   - **Todo Notes:** Tất nhiên, tốt hơn là nên triển khai hoàn toàn hoặc không triển khai một tính năng nào hoặc theo từng bước tăng dần không yêu cầu nhận xét "**Todo**" - nhưng việc để lại nhận xét "Todo" chỗ này chỗ kia sẽ không có hại gì, đặc biệt là vì các IDE hiện đại giúp tìm thấy những tính năng này.
     + **Ví dụ:**
     ```js
     function login (email, password) {

      // todo: add password validation

      }
     ```
  #### Vertical Formatting

   - Định dạng dọc là việc sử dụng khoảng trắng - dọc trong tệp mã của bạn. Vì vậy, tất cả chỉ là thêm các dòng trống mà còn là nhóm các khái niệm liên quan lại với nhau và thêm khoảng trống giữa các khái niệm cách xa nhau.

   - **Adding Blank Lines**
     + **Ví dụ:** Đoạn mã này không sử dụng khoảng trắng giữa các line 
     ```js
     function login (email, password) {
      if (!email.includes ('@') || password.length < 7) {
      throw new Error('Invalid input!');
      }
      const user = findUserByEmail(email);
      const passwordIsValid = compare Encrypted Password (user.password, 
            password);
      if (passwordIsValid) {

      createSession();
      } else {
      throw new Error('Invalid credentials!');
      }
     }
      function signup (email, password) {
      if (!email.includes ('@') || password.length < 7) {
      throw new Error('Invalid input!');
      }
      const user = new User (email, password); user.saveToDatabase();
      }
     ```
     + Đoạn mã này bổ sung những dòng trống:
     ```js
     function login (email, password) {
      if (!email.includes ('@') || password.length < 7) {
      throw new Error('Invalid input!');
      }

      const user = findUserByEmail(email);

      const passwordIsValid = compare Encrypted Password (user.password, 
            password);

      if (passwordIsValid) {

      createSession();
      } else {
      throw new Error('Invalid credentials!');
      }
     }

      function signup (email, password) {
      if (!email.includes ('@') || password.length < 7) {
      throw new Error('Invalid input!');
      }

      const user = new User (email, password); user.saveToDatabase();
      }
     ```
   - **Ordering Functions & Methods:** Khi nói đến việc sắp xếp các hàm và phương thức, bạn nên tuân theo "quy tắc giảm dần"
     + **Ví dụ:**  Hàm **validate** được gọi bởi hàm **login** phải ở (gần) bên dưới hàm **login** - ít nhất là nếu ngôn ngữ lập trình của bạn cho phép sắp xếp như vậy.
     ```js
     function login (email, password) { 
        validate(email, passsword);
      }

     function validate (email, password) {...}
     ```
   - **Splitting Code Across Files:** Nếu tệp mã của bạn lớn hơn và/hoặc nếu bạn có nhiều "thứ" khác nhau trong một tệp (ví dụ: nhiều định nghĩa lớp), thì nên chia mã đó thành nhiều tệp và sau đó sử dụng các câu lệnh nhập và xuất để kết nối mã của bạn. Điều này đảm bảo rằng toàn bộ tệp mã riêng lẻ của bạn vẫn có thể đọc được.
  
  ### Horizontal Formatting
   - Tất nhiên, định dạng theo chiều ngang là sử dụng không gian theo chiều ngang trong tệp mã của bạn, điều đó chủ yếu có nghĩa là các dòng phải được giữ ngắn và dễ đọc.

   - **Breaking Lines Into Multiple Lines:** tất nhiên có thể đặt những dòng cực dài trên màn hình của mình - ít nhất là nếu bạn có thể đọc được văn bản/phông chữ nhỏ. Nhưng chỉ vì nó phù hợp với một dòng về mặt kỹ thuật, không có nghĩa đó là mã tốt.

     + **Ví dụ:**
     ```js
     if (!email && !password) {
      email = getValidatedEmail();
      password = getValidated Password();
     }
     ```
   - **Using Short Names:** Tên nên mang tính mô tả. Nhưng không nên lãng phí dung lượng và khiến chúng khó đọc hơn bằng cách viết quá cụ thể.
     + **Ví dụ:** Trong trường hợp này chỉ cần đặt tên **_"loggedInUser"_** là được
     ```js
       const loggedInUserAuthenticatedByEmailAndPassword = ...
     ```

### 4. Xử Lý Lỗi (Error Handling)

### 5. Kiểm Thử (Testing)

### 6. Tổ Chức Mã (Code Organization)