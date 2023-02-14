# Agency_Brand_Crawl

## Mục tiêu

Lấy dữ liệu của các Agency Partner từ trang web https://www.agencyvietnam.com/.

## Idea

Vì không có API nên sẽ cào bề mặt. **Tuy nhiên phải sử dụng selenium vì nếu sử dụng requests, ở phần email sẽ báo [email_protected] -> không lấy về email được**.

## Các bước thực hiện

Đầu tiên, cần truy cập trang web chính https://www.agencyvietnam.com/ bằng Chrome driver và lấy page_source. Từ page_source, tìm kiếm tất cả các menu hiện có và đường link của nó. Vì các menu có thể sẽ bi thay đổi (thêm/ xóa) nên sẽ không dùng find_element mà thay vào đó là find_all (trả về list các giá trị theo tags và class truyền vào) của thư viện BeautifulSoup.

Sau khi lấy được menu link thì tiếp tục dùng Chrome driver để truy cập vào từng link để lấy ra segment của từng công ty và đường link dẫn tới công ty.

Sau khi đã có đường link từng công ty thì tiếp tục dùng Chrome driver để truy cập và lấy ra các thông tin cần thiết. Tuy nhiên sẽ dùng find_element vì ở phần này các element đều đã có vị trí cố định. Những element không có sẽ trả về rỗng.

Cuối cùng, lưu lại thành dataframe và xuất thành file excel.
