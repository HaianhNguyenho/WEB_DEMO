HƯỚNG DẪN CHẠY PROJECT:

- Giải nén
- Import Db:
	+ Chạy mysql ( mysql, xampp,... )
	+ import data
	+ Data ban đầu hiện tại trống sản phẩm ( có thể tự add data trong khi test sau )
	+ Data hiện tại bao gồm 1 account admin ban đầu
		email: admin@gmail.com
		pwd: 123456

- Lấy mật khẩu ứng dụng account google:
	+ Vào "Quản lý tài khoản" Google
	+ Vào "Bảo mật" ( Security )
	+ Bật "Xác minh 2 bước" mới có thể thêm mật khẩu ứng dụng nhe.
	+ Nhớ copy mật khẩu ứng dụng trước khi đóng popup ( Nếu không thực hiện tạo thêm 1 lần nữa )
	+ Vậy là xong

- Vào thư mục project = vscode
- Vào file Mailer.java : Đường dẫn src/java/Utils/Mailer.java
	+ Email chính là email của account gg vừa copy mật khẩu ứng dụng
	+ Password chính là mật khẩu ứng dụng
	+ PREFIX là prefix ở tiêu đề khi gửi mail thôi ( tí demo sẽ thấy )
	+ Xong phần mail

- Vào src/java/DAO/Database.java ( nếu sử dụng mysql khác hoặc quyền hạn user khác mặc định )
	+ CONNECTION_STRING: đường dẫn để kết nối db mysql. mặc định localhost và port 3306
	+ USER mặc định xampp là root
	+ PASSWORD mặc định là none "".
	+ Nếu sử dụng khác thì nhớ setting

- Chạy project
	+ Vào Maven -> Plugin -> War -> Exploded: để build proj
	+ Sau khi build -> 1 Thư mục proj sẽ hiện trong folder target
	+ Chuột phải vào thư mục -> Run on server hoặc debug on server
	+ Chọn server muốn run ( chú ý nhớ port setting của tomcat server nha )

- Vào proj test thôi.
- File này bên mình sẽ gửi kèm vào project nhe.


MỘT SỐ CHỨC NĂNG ĐÃ HOÀN THÀNH:
- Phần ADMIN:
	+ Quản lý sản phẩm ( Thêm, xóa, sửa,.. )
	+ Quản lý tài khoản ( khóa tk, xóa tk )
	+ Quản lý đơn hàng ( Hủy, xác thực, xác nhận hoàn thành đơn hàng )
		* Sau khi hoàn thành đơn hàng sẽ update số lượng sản phẩm nhé
	+ Xem thống kê ( tạm )

- Phần User chung ( ADMIN vẫn được quyền sử dụng ):
	+ Xem sản phẩm / Xem theo thể loại, thương hiệu.
	+ filter sản phẩm ( Tạm sử dụng được )
	+ Thêm giỏ hàng ( chọn size, số lượng )
		NOTE: Thêm giỏ hàng số lượng hiện tại có vẻ bị bug luôn có số lượng 1
	+ Đặt hàng ( thanh toán )
	+ Đăng ký tài khoản ( nên chọn email có tồn tại để thực hiện chức năng gửi mail xác thực, cũng như quên mật khẩu )
	+ Quên mật khẩu ( có gửi mail xác thực )
		NOTE: email admin hiện tại là giả, muốn sử dụng chức năng này thì nên đổi email admin trong mysql sang 1 email thực khác.
		NOTE: Còn lại tất cả user sau khi đăng ký khác đều có thể sử dụng.
	+ Đăng nhập

* Phần lớn chức năng đã hoàn thành và validate, security cho admin ( user khác kh thể sử dụng chức năng admin ).