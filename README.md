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
    + Với điều kiện cấc têp tin, thư mục được thay đổi đã phải nằm trong Staging area