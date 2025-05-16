# 🚀 **Personal Website** 🚀

---

## 📋 **Yêu cầu trước**

Trước khi bắt đầu, bạn cần cài đặt các công cụ sau:

* **Node.js & npm**: phiên bản LTS (>=14.x)
  Tải: [https://nodejs.org/](https://nodejs.org/)
* **Java JDK**: phiên bản 11+
  Kiểm tra: `java -version`
* **Maven** (nếu không dùng Maven Wrapper)
  Kiểm tra: `mvn -v`
* **Git**
  Kiểm tra: `git --version`
* **VS Code** (hoặc IDE ưa thích)

---

## 🛠 **Khởi tạo dự án**

### 1️⃣ Tạo thư mục gốc

```bash
mkdir personal-website
cd personal-website
mkdir backend frontend
```

### 2️⃣ Backend (Spring Boot)

1. Truy cập **Spring Initializr**: [https://start.spring.io/](https://start.spring.io/)
2. Cấu hình:

   * **Project**: Maven Project
   * **Language**: Java
   * **Spring Boot**: 3.4.5
   * **Group**: `com.personalwebsite.quanganh`
   * **Name**: `PersonalWebsite`
   * **Artifact**: `PersonalWebsite`
   * **Package name**: `com.personalwebsite.quanganh.PersonalWebsite`
   * **Dependencies**: Spring Web, Spring Boot DevTools,Lombok, Spring Data JPA, H2 Database, My SQL Driver (tùy chọn JPA, H2)
3. Nhấn **Generate** → tải file ZIP.
4. Giải nén vào `backend/`:

   ```bash
   cd backend
   unzip ../personalwebsite-backend.zip
   ```
5. Mở VS Code:

   ```bash
   code .
   ```
6. (Tuỳ chọn) Chỉnh cổng server trong `src/main/resources/application.properties`:

   ```properties
   server.port=8082
   ```
7. Chạy chạy thử:

   ```bash
   ./mvnw spring-boot:run
   ```

### 3️⃣ Frontend (ReactJS)

1. Di chuyển vào `frontend/`:

   ```bash
   cd ../frontend
   ```
2. Khởi tạo React App:

   ```bash
   npx create-react-app .
   ```
3. Mở VS Code:

   ```bash
   code .
   ```
4. (Tuỳ chọn) Thiết lập proxy trong `package.json`:

   ```json
   {
     "proxy": "http://localhost:8082"
   }
   ```
5. Chạy frontend:

   ```bash
   npm start
   ```

---

## 🎉 **Kết quả**

* **Backend**: Spring Boot chạy cổng **8082**
* **Frontend**: ReactJS tại **[http://localhost:3000](http://localhost:3000)**, tự động proxy API

---

## 🗂 **Cấu trúc thư mục**

```text
personal-website/
├── **backend/**            # Spring Boot project
│   ├── .mvn/               # Maven Wrapper
│   ├── **src/**            # Source code
│   │   ├── main/           # Java & resources
│   │   └── test/           # Unit tests
│   ├── mvnw                # Maven Wrapper script
│   ├── mvnw.cmd            # Maven Wrapper cho Windows
│   ├── pom.xml             # Maven config
│   ├── .gitignore          # Bỏ qua target, logs...
│   └── .gitattributes      # File thuộc tính Git
│
└── **frontend/**           # ReactJS project
    ├── **public/**         # HTML, favicon, manifest
    ├── **src/**            # Component, CSS, JS
    ├── node_modules/       # Dependencies (ignored)
    ├── build/              # Build output (ignored)
    ├── package.json        # npm config
    ├── package-lock.json   # Lock file
    └── .gitignore          # Bỏ qua node_modules, build...
```

---

## 📞 **Liên hệ**

Mọi thắc mắc vui lòng mở **Issue** hoặc liên hệ: `you@example.com`
