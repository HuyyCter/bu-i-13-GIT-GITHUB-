## Giới thiệu GIT
- GIT là 1 hệ thống quản lý phiên bản phân tán 
- GIT cung cấp kho lưu trữ (repository) riêng chứa toàn bộ lịch sử thay đổi
- Ưu điểm : tốc độ nhanh, đơn giản, phân tán, phù hợp với dự án lớn nhỏ
- GIT là 1 trong những hệ thống quản lý phiên bản phân tán phổ biến nhất hiện nay

## Các thuật ngữ
- Working directory (Thư mục làm việc) : khu vực chứa dự án chúng ta đang làm việc
- Staging area (Khu vực sắp xếp) : khu vực chứa thông tin thay đổi của các file
- Repository (Git directory - thư mục git) : kho lưu trữ để lưu trữ dữ liệu, lịch sử các phiên bản

## Các câu lệnh GIT phổ biến
- git --version : xem phiên bản hiện tại đang được cài trên máy tính

- git --help : xem danh sách các câu lệnh git 

- git config : để đặt username và email của bạn trong file config của git
    + git config --global user.name : để xem thông tin cấu hình username
    + git config --global user.email : để xem thông tin cấu hình email
    + git config --global user.name "Nguyễn Quang Huy" : để đặt username mới
    + git config --global user.email "nguyenquanghuy070306@gmail.com" để đặt email mới

- git init
    + Khởi tạo 1 git repository (kho lưu trữ) trong 1 dự án mới hoặc dự án đã có (dùng trong thư mục gốc của dự án)
    + Khi khởi tạo xong, trong thư mục gốc (dự án đang làm) sẽ sinh ra 1 thư mục tên là .git, thư mục này sẽ lưu toàn bộ thông tin lịch sử của dự án mà bạn làm

- git status
    + Để xem trạng thái của những file đã được thay đổi (bao gồm : thêm, sửa, xóa) trong dự án
    + Ví dụ : tạo file README.md trong dự án (file này để giới thiệu và hướng dẫn cách cài đặt dự án). Sau đó gỡ lệnh git status, ta sẽ thấy có file README.md được thêm mới

- git add ten_file
    + Thông tin của các file sẽ được lưu vào Staging area
    + Staging area có tác dụng sắp xếp lại các file đã add vào
    + Ví dụ : tạo ra các file rồi thử lại câu lệnh này

- git add .
    + Thêm thay đổi cho tất cả các file

- git commit -m "Nội dung..."
    + Để đưa những file ở vùng Staging area chuyển sang Repository, mục đích là tạo 1 phiên bản mới và lưu vào lịch sử của Repository
    + Với điều kiện cấc têp tin, thư mục được thay đổi đã phải nằm trong Staging area\

- git log : giúp bạn xem lại thông tin lịch sử commit, nhằm giám sát sự thay đổi của dự án. Commit mới sẽ hiện bên trên, commit cũ sẽ hiện bên dưới (nếu gặp chữ END thì nhấn phím q để thoát)

- git show commit_id : dùng để xem chi tiết 1 commit (xem trong git log)

- git diff : xem sự thay đổi của 1 file sau khi chúng ta chỉnh sửa (file đó vẫn đang ở khu vực Working directory)

- gitk : mở dashboard xem trực quan hơn

- git checkout --ten_file : bỏ đi những thay đổi của file, để file đó trở về như lúc ban đầu

- git reset HEAD ten_file hoặc git reset ten_file : chuyển file đó từ vùng Staging area trở lại vùng Working directory

- git reset --soft commit_id 
    + Chuyển từ trạng thái đã commit về trạng thái trước lúc chạy lệnh git commit
    + Tức là từ Repository về lại Staging area

- git reset --mixed commit_id
    + Chuyển từ trạng thái đã commit về trạng thái trước lúc chạy lệnh git add
    + Tức là từ Repository về lại Working directory

- git branch 
    + Xem danh sách các nhánh. Các branch (nhánh) đại diện cho các phiên bản cụ thể của 1 kho lưu trữ tách ra từ project chính của bạn
    + Nhánh master là nhánh chính, để sau này deploy lên server

- git checkout -b ten_nhanh : tạo 1 nhánh mới và chuyển sang nhánh đó

- git checkout ten_nhanh : chuyển sang nhánh khác

## Quy trình
- Khi thêm, sửa, xóa file thì vẫn đang ở Working directory (chạy lệnh git status, những file màu đỏ là nằm trong Working directory)
- Sau đó chạy lệnh git add ten_file thì thông tin của các file sẽ được lưu vào Staging area, Staging area có tác dụng sắp xếp lại những file đã add vào (giả sử có 1 file được thay đổi, ta add vào lần 1, sau đó ta lại sửa file đó và add vào lần 2, thì Staging area chỉ lấy lần 2. Chạy lệnh git status, những file màu xanh lá là nằm trong Staging area)
- Sau đó chạy lệnh git commit -m "Nội dung commit...". Lúc này những file đã được đánh dấu ở vùng Staging area sẽ được lưu vào Repository