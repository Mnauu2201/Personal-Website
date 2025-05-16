Personal Website

Yêu cầu trước

Trước khi bắt đầu, bạn cần cài đặt những công cụ và phần mềm sau:

Node.js & npm: phiên bản LTS (>=14.x). Tải tại https://nodejs.org/

Java JDK: phiên bản 11 trở lên (OpenJDK hoặc Oracle JDK). Kiểm tra với java -version.

Maven (nếu không sử dụng Maven Wrapper). Kiểm tra với mvn -v.

Git: để quản lý mã nguồn và đẩy lên GitHub. Kiểm tra với git --version.

VS Code (hoặc bất kỳ IDE bạn thích).

Khởi tạo dự án

Thực hiện theo các bước sau để tạo dự án frontend ReactJS và backend Spring Boot:

1. Tạo thư mục gốc
  mkdir personal-website
  cd personal-website
  mkdir backend frontend
2. Tạo project Spring Boot (backend)

  Mở trang Spring Initializr: https://start.spring.io/

  Cấu hình:

  Project: Maven Project

  Language: Java

  Spring Boot: 3.x

  Group: com.yourname

  Artifact: personalwebsite-backend

  Dependencies: Spring Web, Spring Boot DevTools (tuỳ chọn thêm Spring Data JPA, H2 nếu cần)

3. Nhấn Generate để tải về file ZIP.

4. Giải nén vào thư mục backend/:

  cd backend
  unzip ../personalwebsite-backend.zip

5. Mở VS Code trong thư mục backend:
  code .
6. (Tuỳ chọn) Chỉnh cổng server trong src/main/resources/application.properties:

  server.port=8082  # hoặc 8080, tuỳ bạn

7. Chạy thử backend:

  ./mvnw spring-boot:run

3. Tạo project ReactJS (frontend)

Di chuyển về thư mục frontend:

  cd ../frontend

2. Khởi tạo React App:

  npx create-react-app .

3. Mở VS Code trong thư mục frontend:

  code .

4. (Tuỳ chọn) Cấu hình proxy để gọi API tới backend (put vào package.json ngay sau phần "private"):

  "proxy": "http://localhost:8082",

5. Chạy frontend:

  npm start

Sau khi hoàn thành, bạn sẽ có:

Backend Spring Boot chạy trên cổng bạn chọn (8082).

Frontend ReactJS chạy trên cổng 3000, tự động proxy API đến backend.

personal-website/
├─ backend/                # Spring Boot project
│  ├─ src/main/java/...    # Code Java
│  ├─ src/main/resources/  # Config, static nếu deploy chung
│  ├─ target/              # Binaries (ignored)
│  └─ pom.xml
├─ frontend/               # React project
│  ├─ public/              # HTML, favicon, manifest
│  ├─ src/                 # Component, CSS, JS
│  ├─ node_modules/        # Dependencies (ignored)
│  ├─ build/               # Build output (ignored)
│  └─ package.json
└─ README.md
