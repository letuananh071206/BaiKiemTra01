Câu 1: Trình bày sự khác nhau giữa Value Types và Reference Types trong C# về cơ chế lưu trữ vùng nhớ Stack và Heap.
Trong C#, kiểu dữ liệu được chia thành hai nhóm chính là Value Types (kiểu giá trị) và Reference Types (kiểu tham chiếu).
Value Types là kiểu dữ liệu mà biến lưu trực tiếp giá trị của dữ liệu. Khi một biến kiểu giá trị được gán cho một biến khác thì giá trị được sao chép sang biến mới. Hai biến sau khi sao chép sẽ có dữ liệu độc lập với nhau. Một số kiểu giá trị phổ biến gồm int, float, double, bool, char, struct và enum.
Reference Types là kiểu dữ liệu mà biến không lưu trực tiếp đối tượng mà lưu một tham chiếu đến đối tượng. Đối tượng được tạo ra thường được lưu trên vùng nhớ Heap. Khi một biến tham chiếu được gán cho biến tham chiếu khác thì tham chiếu được sao chép, vì vậy hai biến có thể cùng tham chiếu đến một đối tượng. Một số Reference Types phổ biến gồm class, object, string, array, interface và delegate.
Về vùng nhớ, Stack là vùng nhớ thường được sử dụng cho các biến cục bộ, thông tin gọi hàm và dữ liệu có thời gian sống ngắn. Heap là vùng nhớ được sử dụng để lưu trữ các đối tượng được tạo động và được .NET quản lý thông qua cơ chế Garbage Collector.
Có thể hiểu đơn giản rằng Value Type thường gắn với việc lưu trực tiếp giá trị, trong khi Reference Type sử dụng một biến tham chiếu đến đối tượng được lưu trên Heap.
Tuy nhiên, không nên hiểu tuyệt đối rằng mọi Value Type luôn nằm trên Stack và mọi Reference Type luôn nằm trên Heap. Vị trí thực tế còn phụ thuộc vào ngữ cảnh và cách CLR (.NET) quản lý bộ nhớ.
Kết luận: Điểm khác nhau cơ bản là Value Type lưu trực tiếp giá trị, còn Reference Type lưu tham chiếu đến đối tượng. Khi sao chép Value Type thì giá trị được sao chép độc lập, còn khi sao chép Reference Type thì có thể tạo ra nhiều tham chiếu cùng trỏ đến một đối tượng.
________________________________________
Câu 2: Tính năng Init-only Properties (init) trong C# 9/10 khác gì so với thuộc tính có set thông thường? Nêu trường hợp sử dụng thực tế.
Trong C#, set và init đều cho phép thiết lập giá trị cho thuộc tính, nhưng thời điểm được phép thay đổi giá trị là khác nhau.
Đối với thuộc tính sử dụng set, giá trị của thuộc tính có thể được thiết lập khi tạo đối tượng và cũng có thể được thay đổi sau khi đối tượng đã được tạo. Vì vậy, set phù hợp với những thuộc tính mà giá trị có thể thay đổi trong suốt thời gian tồn tại của đối tượng.
Đối với thuộc tính sử dụng init, giá trị chỉ được phép thiết lập trong quá trình khởi tạo đối tượng. Sau khi đối tượng được khởi tạo hoàn tất, thuộc tính đó không thể được thay đổi bằng cách gán thông thường. Tính năng init được giới thiệu từ C# 9 và tiếp tục được sử dụng trong các phiên bản C# sau đó.
Sự khác nhau chính:
•	set: cho phép gán và thay đổi giá trị sau khi đối tượng được tạo.
•	init: chỉ cho phép thiết lập giá trị trong quá trình khởi tạo đối tượng.
•	init giúp hạn chế việc thay đổi những dữ liệu cần được giữ cố định sau khi đối tượng được tạo.
•	set phù hợp với các dữ liệu cần cập nhật trong quá trình chương trình hoạt động.
Trường hợp sử dụng thực tế: init có thể được sử dụng cho các thông tin cần xác định một lần khi tạo đối tượng và không nên thay đổi sau đó, chẳng hạn như mã sinh viên, mã sản phẩm, mã đơn hàng hoặc mã định danh của một đối tượng.
Kết luận: set cho phép thuộc tính thay đổi trong suốt vòng đời của đối tượng, trong khi init giúp thuộc tính chỉ được thiết lập khi khởi tạo và sau đó giữ nguyên giá trị.
________________________________________
Câu 3: Phân biệt phương thức virtual ở lớp cha và phương thức override ở lớp con khi triển khai tính đa hình (Polymorphism).
Đa hình (Polymorphism) là một đặc điểm quan trọng của lập trình hướng đối tượng. Đa hình cho phép cùng một phương thức nhưng có thể có cách thực hiện khác nhau tùy thuộc vào đối tượng thực tế.
Từ khóa virtual được sử dụng trong lớp cha để khai báo một phương thức có khả năng được lớp con ghi đè. Khi một phương thức được khai báo là virtual, lớp con có thể cung cấp cách thực hiện riêng cho phương thức đó.
Từ khóa override được sử dụng trong lớp con để ghi đè phương thức virtual đã được khai báo trong lớp cha. Khi sử dụng override, lớp con thay đổi cách thực hiện của phương thức sao cho phù hợp với đặc điểm của lớp con.
Có thể hiểu đơn giản:
•	virtual: được sử dụng ở lớp cha, cho phép lớp con thay đổi cách thực hiện phương thức.
•	override: được sử dụng ở lớp con, dùng để ghi đè cách thực hiện phương thức của lớp cha.
•	Hai từ khóa này thường được sử dụng kết hợp để thực hiện tính đa hình.
Khi chương trình gọi một phương thức thông qua kiểu của lớp cha nhưng đối tượng thực tế thuộc lớp con, phương thức override của lớp con có thể được thực hiện. Nhờ đó, cùng một lời gọi phương thức nhưng có thể tạo ra hành vi khác nhau đối với các đối tượng khác nhau.
Kết luận: virtual là cơ chế mở ở lớp cha cho phép ghi đè, còn override là cơ chế ghi đè được thực hiện ở lớp con. Sự kết hợp của chúng giúp C# triển khai tính đa hình trong lập trình hướng đối tượng.
________________________________________
Câu 4: Tại sao một thành phần được khai báo là static trong Class lại không thể truy xuất thông qua một Object Instance được tạo bằng toán tử new?
Trong C#, từ khóa static được sử dụng để khai báo một thành phần thuộc về Class, thay vì thuộc về từng Object Instance.
Đối với thành phần thông thường, mỗi đối tượng được tạo ra từ một lớp có thể có dữ liệu riêng. Mỗi Object Instance có thể lưu giữ một giá trị khác nhau cho thành phần đó.
Ngược lại, thành phần được khai báo là static chỉ tồn tại ở cấp độ lớp. Nó được dùng chung cho tất cả các đối tượng thuộc lớp đó và không phụ thuộc vào một đối tượng cụ thể nào.
Do đó, khi sử dụng thành phần static, không cần phải tạo đối tượng bằng toán tử new. Thành phần static được truy cập thông qua tên của Class.
Lý do không truy xuất static thông qua Object Instance là vì Object Instance đại diện cho một đối tượng cụ thể, trong khi static lại thuộc về toàn bộ Class. Hai phạm vi này khác nhau về mặt bản chất.
Ví dụ về mặt ý nghĩa:
•	Thành phần thông thường → thuộc về từng Object.
•	Thành phần static → thuộc về Class.
•	Thành phần thông thường có thể có giá trị khác nhau ở mỗi Object.
•	Thành phần static được dùng chung ở cấp độ Class.
Một ứng dụng thực tế của static là lưu những dữ liệu dùng chung cho tất cả đối tượng của một lớp, chẳng hạn như biến dùng để đếm tổng số đối tượng đã được tạo.
Kết luận: Thành phần static thuộc về Class chứ không thuộc về từng Object Instance. Vì vậy, nó được truy cập thông qua tên Class và không cần tạo Object bằng toán tử new.

Câu 1: Trình bày sự khác nhau giữa Value Types và Reference Types trong C# về cơ chế lưu trữ vùng nhớ Stack và Heap.
Trong C#, kiểu dữ liệu được chia thành hai nhóm chính là Value Types (kiểu giá trị) và Reference Types (kiểu tham chiếu).
Value Types là kiểu dữ liệu mà biến lưu trực tiếp giá trị của dữ liệu. Khi một biến kiểu giá trị được gán cho một biến khác thì giá trị được sao chép sang biến mới. Hai biến sau khi sao chép sẽ có dữ liệu độc lập với nhau. Một số kiểu giá trị phổ biến gồm int, float, double, bool, char, struct và enum.
Reference Types là kiểu dữ liệu mà biến không lưu trực tiếp đối tượng mà lưu một tham chiếu đến đối tượng. Đối tượng được tạo ra thường được lưu trên vùng nhớ Heap. Khi một biến tham chiếu được gán cho biến tham chiếu khác thì tham chiếu được sao chép, vì vậy hai biến có thể cùng tham chiếu đến một đối tượng. Một số Reference Types phổ biến gồm class, object, string, array, interface và delegate.
Về vùng nhớ, Stack là vùng nhớ thường được sử dụng cho các biến cục bộ, thông tin gọi hàm và dữ liệu có thời gian sống ngắn. Heap là vùng nhớ được sử dụng để lưu trữ các đối tượng được tạo động và được .NET quản lý thông qua cơ chế Garbage Collector.
Có thể hiểu đơn giản rằng Value Type thường gắn với việc lưu trực tiếp giá trị, trong khi Reference Type sử dụng một biến tham chiếu đến đối tượng được lưu trên Heap.
Tuy nhiên, không nên hiểu tuyệt đối rằng mọi Value Type luôn nằm trên Stack và mọi Reference Type luôn nằm trên Heap. Vị trí thực tế còn phụ thuộc vào ngữ cảnh và cách CLR (.NET) quản lý bộ nhớ.
Kết luận: Điểm khác nhau cơ bản là Value Type lưu trực tiếp giá trị, còn Reference Type lưu tham chiếu đến đối tượng. Khi sao chép Value Type thì giá trị được sao chép độc lập, còn khi sao chép Reference Type thì có thể tạo ra nhiều tham chiếu cùng trỏ đến một đối tượng.
________________________________________
Câu 2: Tính năng Init-only Properties (init) trong C# 9/10 khác gì so với thuộc tính có set thông thường? Nêu trường hợp sử dụng thực tế.
Trong C#, set và init đều cho phép thiết lập giá trị cho thuộc tính, nhưng thời điểm được phép thay đổi giá trị là khác nhau.
Đối với thuộc tính sử dụng set, giá trị của thuộc tính có thể được thiết lập khi tạo đối tượng và cũng có thể được thay đổi sau khi đối tượng đã được tạo. Vì vậy, set phù hợp với những thuộc tính mà giá trị có thể thay đổi trong suốt thời gian tồn tại của đối tượng.
Đối với thuộc tính sử dụng init, giá trị chỉ được phép thiết lập trong quá trình khởi tạo đối tượng. Sau khi đối tượng được khởi tạo hoàn tất, thuộc tính đó không thể được thay đổi bằng cách gán thông thường. Tính năng init được giới thiệu từ C# 9 và tiếp tục được sử dụng trong các phiên bản C# sau đó.
Sự khác nhau chính:
•	set: cho phép gán và thay đổi giá trị sau khi đối tượng được tạo.
•	init: chỉ cho phép thiết lập giá trị trong quá trình khởi tạo đối tượng.
•	init giúp hạn chế việc thay đổi những dữ liệu cần được giữ cố định sau khi đối tượng được tạo.
•	set phù hợp với các dữ liệu cần cập nhật trong quá trình chương trình hoạt động.
Trường hợp sử dụng thực tế: init có thể được sử dụng cho các thông tin cần xác định một lần khi tạo đối tượng và không nên thay đổi sau đó, chẳng hạn như mã sinh viên, mã sản phẩm, mã đơn hàng hoặc mã định danh của một đối tượng.
Kết luận: set cho phép thuộc tính thay đổi trong suốt vòng đời của đối tượng, trong khi init giúp thuộc tính chỉ được thiết lập khi khởi tạo và sau đó giữ nguyên giá trị.
________________________________________
Câu 3: Phân biệt phương thức virtual ở lớp cha và phương thức override ở lớp con khi triển khai tính đa hình (Polymorphism).
Đa hình (Polymorphism) là một đặc điểm quan trọng của lập trình hướng đối tượng. Đa hình cho phép cùng một phương thức nhưng có thể có cách thực hiện khác nhau tùy thuộc vào đối tượng thực tế.
Từ khóa virtual được sử dụng trong lớp cha để khai báo một phương thức có khả năng được lớp con ghi đè. Khi một phương thức được khai báo là virtual, lớp con có thể cung cấp cách thực hiện riêng cho phương thức đó.
Từ khóa override được sử dụng trong lớp con để ghi đè phương thức virtual đã được khai báo trong lớp cha. Khi sử dụng override, lớp con thay đổi cách thực hiện của phương thức sao cho phù hợp với đặc điểm của lớp con.
Có thể hiểu đơn giản:
•	virtual: được sử dụng ở lớp cha, cho phép lớp con thay đổi cách thực hiện phương thức.
•	override: được sử dụng ở lớp con, dùng để ghi đè cách thực hiện phương thức của lớp cha.
•	Hai từ khóa này thường được sử dụng kết hợp để thực hiện tính đa hình.
Khi chương trình gọi một phương thức thông qua kiểu của lớp cha nhưng đối tượng thực tế thuộc lớp con, phương thức override của lớp con có thể được thực hiện. Nhờ đó, cùng một lời gọi phương thức nhưng có thể tạo ra hành vi khác nhau đối với các đối tượng khác nhau.
Kết luận: virtual là cơ chế mở ở lớp cha cho phép ghi đè, còn override là cơ chế ghi đè được thực hiện ở lớp con. Sự kết hợp của chúng giúp C# triển khai tính đa hình trong lập trình hướng đối tượng.
________________________________________
Câu 4: Tại sao một thành phần được khai báo là static trong Class lại không thể truy xuất thông qua một Object Instance được tạo bằng toán tử new?
Trong C#, từ khóa static được sử dụng để khai báo một thành phần thuộc về Class, thay vì thuộc về từng Object Instance.
Đối với thành phần thông thường, mỗi đối tượng được tạo ra từ một lớp có thể có dữ liệu riêng. Mỗi Object Instance có thể lưu giữ một giá trị khác nhau cho thành phần đó.
Ngược lại, thành phần được khai báo là static chỉ tồn tại ở cấp độ lớp. Nó được dùng chung cho tất cả các đối tượng thuộc lớp đó và không phụ thuộc vào một đối tượng cụ thể nào.
Do đó, khi sử dụng thành phần static, không cần phải tạo đối tượng bằng toán tử new. Thành phần static được truy cập thông qua tên của Class.
Lý do không truy xuất static thông qua Object Instance là vì Object Instance đại diện cho một đối tượng cụ thể, trong khi static lại thuộc về toàn bộ Class. Hai phạm vi này khác nhau về mặt bản chất.
Ví dụ về mặt ý nghĩa:
•	Thành phần thông thường → thuộc về từng Object.
•	Thành phần static → thuộc về Class.
•	Thành phần thông thường có thể có giá trị khác nhau ở mỗi Object.
•	Thành phần static được dùng chung ở cấp độ Class.
Một ứng dụng thực tế của static là lưu những dữ liệu dùng chung cho tất cả đối tượng của một lớp, chẳng hạn như biến dùng để đếm tổng số đối tượng đã được tạo.
Kết luận: Thành phần static thuộc về Class chứ không thuộc về từng Object Instance. Vì vậy, nó được truy cập thông qua tên Class và không cần tạo Object bằng toán tử new.

