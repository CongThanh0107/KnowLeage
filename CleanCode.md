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

 - **Minimize The Number Of Parameters:** Hàm càng có ít tham số thì càng dễ đọc và gọi (và càng dễ đọc và hiểu các câu lệnh trong đó hàm được gọi).
   + Hãy xem ví dụ này :
   ```js
    // Unclean Code
    createUser('Max', 'Max', 'test@test.com', 'testers', 31, ['Sports', 'Cooking']);
   ```  
 - **Vậy có bao nhiêu tham số thì ổn ?**
   + Càng ít tham số thì hàm càng dễ đọc và dễ hiểu hơn
   + Tất nhiên, các hàm không có tham số rất dễ đọc và dễ hiểu. Ví dụ:
   ```js
   createSession();

   user.save();
   ```
   + Tuy nhiên chính khả năng lấy tham số đã làm cho các hàm trở nên năng động và linh hoạt. Mặt khác, bạn có thể gặp phải các hàm trong đó hai hoặc nhiều tham số có thể gây nhầm lẫn và không rõ ràng/thông thường giá trị nào sẽ đi ở đâu. Ví dụ:
   ```js
    createRectangle(10, 9, 30, 12);

    createUser('test@test.com', 31, 'max');
   ```
   + Vậy nên nếu không cần thiết hãy tránh tạo nhiều hơn hai tham số. Nó có thể làm cho mã của bạn khó gọi và khó đọc.
 
 - **Làm cách nào để giảm số lượng tham số ?**
   + Có thể thay thế các tham số bằng **map(bản đồ)** hoặc **array(mảng)**. Điều này giúp dễ đọc hơn nhiều.
   + **Ví dụ:**
   ```js
    createRectangle({x: 10, y: 9, width: 30, high: 12});
   ```
 
 - **Keep Functions Small**
   + Bên cạnh số lượng tham số, phần thân hàm cũng nên được giữ ở mức nhỏ gọn nhất
   + Bởi vì kích thước nhỏ hơn có nghĩa là ít mã để đọc và hiểu hơn. Nhưng ngoài ra, nó cũng buộc bạn (lý tưởng nhất) phải viết mã dễ đọc - ví dụ bằng cách trích xuất các hàm khác sử dụng cách đặt tên tốt.
   + **Ví dụ:**
   ```js
    function login (email, password) {

    validateUserInput (email, password);

    const existingUser = findUserByEmail(email);

    existingUser.validatePassword (password);
   }
   ```
 
 - **Rules Of Thumb**: Có hai quy tắc kinh nghiệm đơn giản , giúp bạn quyết định thời điểm chia tách mã của mình
   + 1.Trích xuất mã hoạt động trên cùng chức năng/có liên quan chặt chẽ với nhau
   + 2.Trích xuất mã yêu cầu giải thích nhiều hơn mã xung quanh
   + Đây là ví dụ cho quy tắc số 1:
   ```js
    function updateUser (userData) {
    validateUserData(userData);
    const user = findUserById(userData.id);
    user.setAge (userData.age);
    user.setName (userData.name);
    user.save();
    }
   ```
   + **setAge()** và **setName()** có cùng mục tiêu/chức năng: Chúng cập nhật dữ liệu trong đối tượng **user.save()** sau đó xác nhận những thay đổi này.Do đó bạn có thể chia chức năng:
   ```js
    function updateUser (userData) { 
      validateUserData (userData); 
      applyUpdate(userData);
    }

    function apply Update (userData) {
      const user = findUserById(userData.id);
      user.setAge(userData.age);
      user.setName (userData.name);
      user.save();
    }
   ```
   + Đây là ví dụ cho quy tắc số 2:
   ```js
    function process Transaction (transaction) {
      if (transaction.type === 'UNKNOWN') {
      throw new Error('Invalid transaction type.');
    }
    if (transaction.type === 'PAYMENT') {
      process Payment (transaction);
      }
    }
   ```
   + Tất nhiên, việc xác thực xem loại giao dịch có phải là **'UNKNOWN'** không khó đọc hay không nhưng nó chắc chắn cần được giải thích nhiều hơn từ phía bạn thay vì chỉ đọc **processPayment(...)**.Do đó, bạn có thể cấu trúc lại đoạn mã thành:
   ```js
    function process Transaction (transaction) {
      validateTransaction (transaction);
      if (isPayment (transaction)) {
        process Payment (transaction);
      }
    }
   ```
 
 - **Nguyên Tắc DRY (Don't Repeat Yourself):** là một trong những nguyên tắc quan trọng trong lập trình và phát triển phần mềm. Nguyên tắc này khuyến khích lập trình viên giảm thiểu sự trùng lặp mã nguồn bằng cách tái sử dụng mã. Việc áp dụng nguyên tắc DRY không chỉ giúp giảm thiểu lỗi mà còn làm cho mã nguồn dễ bảo trì, hiểu và mở rộng
   + **Ví dụ:**
   ```python
    #Unclean Code

    def calculate_area_of_rectangle(length, width):  
        area = length * width  
        print("Area of Rectangle:", area)  
      
    def calculate_area_of_square(side):  
        area = side * side  
        print("Area of Square:", area)  
      
    # Tính toán diện tích của hình chữ nhật  
    calculate_area_of_rectangle(10, 5)  
      
    # Tính toán diện tích của hình vuông  
    calculate_area_of_square(4)   
   ```

   ```python
    #Clean Code

    def calculate_area_of_rectangle(length, width):  
        return length * width  
      
    def calculate_area_of_square(side):  
        return calculate_area_of_rectangle(side, side)  
      
    def print_area(area, shape):  
        print(f"Area of {shape}: {area}")  
      
    # Tính toán diện tích của hình chữ nhật  
    rectangle_area = calculate_area_of_rectangle(10, 5)  
    print_area(rectangle_area, "Rectangle")  
      
    # Tính toán diện tích của hình vuông  
    square_area = calculate_area_of_square(4)  
    print_area(square_area, "Square")   

   ```
 
 - N**guyên Tắc KISS (Keep It Simple, Stupid):** Nguyên tắc KISS khuyến khích các lập trình viên giữ mã nguồn của họ đơn giản nhất có thể. Mục đích của nguyên tắc này là giảm thiểu độ phức tạp trong mã để dễ dàng bảo trì và mở rộng sau này.
   + **Ví dụ:**
   ```python
    #Unclean Code
    def complex_calculation(a, b, c):  
        if a > 0:  
            if b > 0:  
                if c > 0:  
                    return (a * b) + (b * c) + (a * c)  
                else:  
                    return (a * b) + (b * c)  
            else:  
                return (a * c)  
        else:  
            return (b * c)  
   ```
   ```python
    #Clean Code
    def simple_calculation(a, b, c):  
        return a * b + b * c + a * c  
        
    result = simple_calculation(2, 3, 4)  
    print(result)  
   ```
 
 - **Nguyên Tắc YAGNI (You Aren't Gonna Need It):** Nguyên tắc YAGNI khuyến cáo bạn không nên thêm tính năng hoặc mã mà bạn nghĩ có thể cần trong tương lai. Thay vào đó, chỉ nên viết mã cho các yêu cầu hiện tại.
   +  **Ví dụ:**
   ```python
    #Unclean Code

    class User:  
        def __init__(self, username, password):  
            self.username = username  
            self.password = password  
            self.is_admin = False  # Trường này không cần thiết ngay bây giờ nhưng được thêm vào dự phòng  
            self.last_login = None  # Đã thêm trường này cho một tính năng chưa được xác định  
      
        def set_admin(self):  
            self.is_admin = True  
      
    # Tạo người dùng  
    user1 = User("user1", "password123")  
   ```
   ```python
    #Clean Code

    class User:  
        def __init__(self, username, password):  
            self.username = username  
            self.password = password  
      
        def set_password(self, new_password):  
            self.password = new_password  
      
    # Tạo người dùng  
    user1 = User("user1", "password123")  
   ```

### 3. Ghi Chú và Định dạng (Comments & Formatting)
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
     + **Ví dụ:** Đoạn mã này không sử dụng cách dòng trống
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

 - **Thông báo lỗi rõ ràng:** Khi một lỗi xảy ra, cần thông báo cho người dùng một cách rõ ràng và dễ hiểu, để họ có thể biết cách khắc phục

 - **Duy trì trạng thái ứng dụng:** Không làm cho ứng dụng dừng hoàn toàn mà phải duy trì trạng thái ổn định và có thể phục hồi.

 - **Ghi lại lỗi:** Thực hiện ghi chú các lỗi xảy ra để phục vụ cho việc gỡ lỗi và cải tiến phần mềm trong tương lai.

 - **Sử dụng cấu trúc try-except:** Trong nhiều ngôn ngữ lập trình, việc sử dụng khối xử lý lỗi cụ thể (như try và except trong Python) rất quan trọng để bắt lỗi và xử lý chúng một cách hợp lý.

 - **Ví dụ:**
   ```python
    #Unclean Code

    def divide(a, b):  
        result = a / b  
        print("Result:", result)  
      
    # Gọi hàm  
    divide(10, 0)  # Gọi hàm với b = 0 => gây ra lỗi ZeroDivisionError  
   ```

   ```python
    #Clean Code

    def divide(a, b):  
        try:  
            result = a / b  
            print("Result:", result)  
        except ZeroDivisionError:  
            print("Error: Division by zero is not allowed.")  
        except TypeError:  
            print("Error: Please provide two numbers.")  
        else:  
            print("Division completed successfully.")  
        finally:  
            print("Execution finished.")  
      
    # Gọi hàm  
    divide(10, 0)  # Gọi hàm với b = 0  
    divide(10, 2)  # Gọi hàm với b = 2  
    divide(10, 'a')  # Gọi hàm với b là chuỗi  

   ```
 - **Kết luận:** Xử lý lỗi đúng cách rất cần thiết trong việc phát triển phần mềm. Nó không chỉ giúp gia tăng độ ổn định của ứng dụng mà còn cải thiện trải nghiệm người dùng. Việc thông báo lỗi rõ ràng và duy trì trạng thái ứng dụng là rất quan trọng, trong khi mã sạch sẽ dễ bảo trì hơn và giảm thiểu sự cố. Bằng cách sử dụng các cấu trúc phù hợp như try, except, else, và finally, lập trình viên có thể quản lý lỗi một cách hiệu quả và thân thiện với người dùng.

### 5. Kiểm Thử (Testing)

 - **Kiểm thử** là một bước quan trọng trong quy trình phát triển phần mềm, giúp xác định và sửa các lỗi trong mã trước khi sản phẩm được phát hành ra thị trường. Kiểm thử không chỉ giúp cải thiện chất lượng sản phẩm mà còn tạo điều kiện cho việc bảo trì và phát triển trong tương lai.
 - **Các Mục Quan Trọng Trong Kiểm Thử:**
   + **Đảm bảo chất lượng sản phẩm:** Kiểm thử giúp phát hiện lỗi và đảm bảo rằng phần mềm hoạt động theo yêu cầu đã xác định.
   + G**iảm rủi ro:** Kiểm thử giúp giảm thiểu rủi ro liên quan đến việc phát hành phần mềm lỗi, điều này giúp bảo vệ uy tín của công ty.
   + **Tăng tính đáng tin cậy:** Phần mềm đã được kiểm thử kỹ lưỡng sẽ đáng tin cậy hơn, gây dựng niềm tin nơi người dùng.
   + **Giúp phát hiện các vấn đề trong quá trình phát triển:** Việc thực hiện kiểm thử thường xuyên giúp phát hiện các vấn đề trước khi chúng trở thành lớn hơn trong các giai đoạn phát triển sau này.
   + **Tạo tài liệu cho dự án:** Các bài kiểm thử và kết quả của chúng có thể trở thành tài liệu quan trọng cho dự án, giúp cho việc bảo trì và phát triển về sau.
 - **Ví dụ:**
   ```python
    #Uncelan Code

    def add(a, b):  
        return a + b  
      
    # Kiểm thử  
    print("Test 1 (2 + 3):", add(2, 3))  # Kết quả đúng là 5  
    print("Test 2 (2 + '3'):", add(2, '3'))  # Lỗi kiểu dữ liệu  
      
    # Không có kiểm thử chính thức hoặc tự động  
   ```
   ```python
    #Clean code
    def add(a, b):  
        return a + b  
      
    # Kiểm thử tự động  
    def test_add():  
        assert add(2, 3) == 5, "Test Case 1 Failed"  
        assert add(-1, 1) == 0, "Test Case 2 Failed"  
        assert add(0, 0) == 0, "Test Case 3 Failed"  
          
        try:  
            add(2, '3')  # Kiểm thử trường hợp lỗi kiểu dữ liệu  
        except TypeError:  
            print("Test Case 4 Passed: TypeError was raised as expected")  
          
        print("All test cases passed!")  
      
    # Gọi hàm kiểm thử  
    test_add()  
   ```