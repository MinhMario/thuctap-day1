cau 1: 15
cau 2:7
cau 3:Le Hung
cau 4:
Lệnh	Chức năng
git diff	Xem thay đổi chưa được đưa vào Staging Area (git add).
git diff --staged	Xem thay đổi đã được đưa vào Staging Area nhưng chưa commit.
File .env chứa mật khẩu, API key, thông tin bí mật; đưa lên Git thì lịch sử lưu mãi và ai xem repo cũng thấy, dễ bị lộ/lợi dụng.
cau 5: Ở 3.1 main không có commit mới kể từ lúc tách nhánh, nên Git chỉ dời con trỏ main lên (Fast-forward). Ở 3.2 main và feature/giao-dien-moi đều có commit riêng (hai nhánh rẽ đôi), nên Git phải tạo merge commit để ghép lại.
cau 6: feature/giao-dien-moi sửa phần main chưa đổi nên gộp tự động được. feature/tieu-de sửa cùng dòng <h1> trong index.html mà giao-dien-moi (đã gộp) cũng sửa khác đi, nên Git không biết chọn bên nào và báo xung đột.
cau 7: Vì commit đã có trên nhánh chung, người khác có thể đã kéo về. reset viết lại lịch sử nên gây lệch/xung đột với họ. revert tạo commit mới đảo ngược thay đổi, giữ nguyên lịch sử nên an toàn.
cau 8: --soft: lùi commit, giữ thay đổi trong staging. --mixed (mặc định): lùi commit, thay đổi về lại working directory (chưa staging). --hard: lùi commit và xóa luôn thay đổi ở cả staging lẫn working directory.
cau 9: Commit df17ab7 "Thêm bộ lọc thu/chi" của Lê Hùng. Hàm tinhTong được viết lại bằng reduce nhưng giá trị khởi tạo là chuỗi rỗng '' thay vì 0, nên phép cộng thành nối chuỗi (vd "10000050000") thay vì cộng số.
cau 10: merge sẽ kéo toàn bộ commit của hotfix vào main, gồm cả commit thử font Comic Sans chưa được duyệt. cherry-pick chỉ lấy đúng commit sửa lỗi.
cau 11: Không giống, vì rebase tạo commit mới (đổi commit cha nên đổi mã băm). Nếu người khác đã kéo nhánh về, lịch sử của họ sẽ khác với nhánh đã rebase, gây xung đột và commit bị nhân đôi.
cau 12: git fetch chỉ tải dữ liệu mới từ remote về, không đổi code đang làm. git pull = fetch + merge (hoặc rebase), tải về và gộp luôn vào nhánh hiện tại.