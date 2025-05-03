# FPT Stella 🚀

![GitHub](https://img.shields.io/github/license/FPT-Stella/Stella-Server?style=flat-square)  
![GitHub last commit](https://img.shields.io/github/last-commit/FPT-Stella/Stella-Server?style=flat-square)  
![GitHub issues](https://img.shields.io/github/issues/FPT-Stella/Stella-Server?style=flat-square)

**FPT Stella** là một tổ chức thuộc hệ sinh thái FPT, tập trung phát triển hệ thống quản lý sinh viên và người dùng với mục tiêu cung cấp giải pháp công nghệ hiệu quả, hiện đại. Chúng tôi xây dựng các ứng dụng client-server sử dụng các công nghệ tiên tiến như .NET 8.0, MongoDB, và React (hoặc các công nghệ frontend tương tự). Dự án được thiết kế để phục vụ việc quản lý dữ liệu sinh viên, người dùng, và các thực thể khác trong môi trường giáo dục. 📚

Hệ thống Stella bao gồm hai thành phần chính: **Stella-Server** (backend) và **Stella-Client** (frontend). Dưới đây là thông tin chi tiết về các repository của chúng tôi.

## 📂 Repository của FPT Stella

### 1. Stella-Server 🛠️

- **Mô tả**: Backend của hệ thống Stella, cung cấp các API RESTful để quản lý sinh viên, người dùng, và các nghiệp vụ liên quan. Được xây dựng với .NET 8.0 và MongoDB.
- **Link**: [Stella-Server](https://github.com/FPT-Stella/Stella-Server)
- **API Documentation**: Đã được deploy tại [Swagger UI](https://stella.dacoban.studio/swagger/index.html) 📜
- **Tính năng chính**:
  - 🧑‍🎓 Quản lý sinh viên (thêm, sửa, xóa, truy vấn theo `UserId`).
  - 👤 Quản lý người dùng và các thực thể khác.
  - 📦 Tích hợp MongoDB để lưu trữ dữ liệu.

### 2. Stella-Client 🌐

- **Mô tả**: Frontend của hệ thống Stella, cung cấp giao diện người dùng để tương tác với backend. (Giả định sử dụng React hoặc một công nghệ frontend khác, vì thông tin cụ thể không được cung cấp).
- **Link**: [Stella-Client](https://github.com/FPT-Stella/Stella-Client)
- **Website Browser**: Đã được deploy tại [Vercel](https://fptstella.vercel.app) 🖥️
- **Tính năng chính**:
  - 🖥️ Giao diện thân thiện với người dùng để quản lý sinh viên và người dùng.
  - 🔗 Tích hợp với API từ Stella-Server để hiển thị và cập nhật dữ liệu.
  - 📱 Responsive design, tương thích với nhiều thiết bị.

## 📑 Mục lục

- [Giới thiệu](#fpt-stella-🚀)
- [Repository của FPT Stella](#📂-repository-của-fpt-stella)
- [Yêu cầu cài đặt](#⚙️-yêu-cầu-cài-đặt)
- [Hướng dẫn setup](#🛠️-hướng-dẫn-setup)
- [Đóng góp](#🤝-đóng-góp)
- [Giấy phép](#📜-giấy-phép)

## ⚙️ Yêu cầu cài đặt

- **Backend (Stella-Server)**:
  - .NET SDK 8.0 hoặc mới hơn 🖥️
  - MongoDB 4.4 hoặc mới hơn 📦
- **Frontend (Stella-Client)**:
  - Node.js 18.x hoặc mới hơn (giả định sử dụng React hoặc một framework tương tự) 🌐
  - npm hoặc yarn để quản lý gói 📦
- **Công cụ khác**:
  - Git để clone repository 🛠️
  - IDE như Visual Studio 2022, Visual Studio Code 💻

## 🛠️ Hướng dẫn setup

### 1. Clone repository 📥

Clone cả hai repository về máy:

```bash
git clone https://github.com/FPT-Stella/Stella-Server.git
git clone https://github.com/FPT-Stella/Stella-Client.git
```

### 2. Setup Stella-Server 🔧

#### Cài đặt MongoDB

- Tải và cài đặt MongoDB từ [trang chính thức](https://www.mongodb.com/try/download/community) 📦
- Khởi động MongoDB server:

  ```bash
  mongod
  ```
- Đảm bảo MongoDB chạy trên `localhost:27017`.

#### Cấu hình connection string

- Trong thư mục `Stella-Server/src/FPTStella.Api`, tạo file `appsettings.json` hoặc sử dụng User Secrets:

  ```json
  {
    "ConnectionStrings": {
      "StellaConnection": "mongodb://localhost:27017/StellaDb"
    }
  }
  ```
- Nếu dùng User Secrets:

  ```bash
  cd Stella-Server/src/FPTStella.Api
  dotnet user-secrets init
  dotnet user-secrets set "ConnectionStrings:StellaConnection" "mongodb://localhost:27017/StellaDb"
  ```

#### Chạy Stella-Server

- Di chuyển đến thư mục backend:

  ```bash
  cd Stella-Server/src/FPTStella.Api
  ```
- Cài đặt dependencies và chạy:

  ```bash
  dotnet restore
  dotnet run
  ```
- Truy cập Swagger UI tại: `http://localhost:5000/swagger/index.html` 📜

### 3. Setup Stella-Client 🌐

#### Cài đặt dependencies

- Di chuyển đến thư mục frontend:

  ```bash
  cd Stella-Client
  ```
- Cài đặt các gói:

  ```bash
  npm install
  ```

  hoặc

  ```bash
  yarn install
  ```

#### Chạy Stella-Client

- Khởi động ứng dụng:

  ```bash
  npm start
  ```

  hoặc

  ```bash
  yarn start
  ```
- Mở trình duyệt và truy cập: `http://localhost:3000` (port mặc định của React, có thể thay đổi tùy cấu hình) 🌐

### 4. Truy cập API - Website deploy 🚀

- API của Stella-Server đã được deploy tại: [Swagger UI](https://stella.dacoban.studio/swagger/index.html).
- Website của Stella-Client đã được deploy tại: [Vercel](https://fptstella.vercel.app)

## 🤝 Đóng góp

Chúng tôi hoan nghênh mọi đóng góp! Vui lòng làm theo các bước sau:

1. Fork repository (`Stella-Server` hoặc `Stella-Client`) 🍴
2. Tạo branch mới:

   ```bash
   git checkout -b feature/<tên-tính-năng>
   ```
3. Commit thay đổi:

   ```bash
   git commit -m "feat: thêm tính năng XYZ"
   ```
4. Push lên branch:

   ```bash
   git push origin feature/<tên-tính-năng>
   ```
5. Tạo Pull Request 📤

Xem [CONTRIBUTING.md](CONTRIBUTING.md) để biết thêm chi tiết.

## 📜 Giấy phép

Dự án được phân phối dưới [MIT License](LICENSE). Xem file `LICENSE` để biết thêm thông tin.

---

**FPT Stella Team** 🌟


