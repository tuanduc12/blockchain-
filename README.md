<h2 align="center">
    <a href="https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin">
    🎓 Faculty of Information Technology (DaiNam University)
    </a>
</h2>
<h2 align="center">
   XÂY DỰNG ỨNG DỤNG GHI CHÚ TRÊN BLOCKCHAIN VỚI MONGODB BACKUP
</h2>
<div align="center">
    <p align="center">
      <img src="https://github.com/Tank97king/LapTrinhMang/blob/main/CHAT%20TCP/%E1%BA%A2nh/fitdnu_logo.png?raw=true" alt="FITDNU Logo" width="180"/>
      <img src="https://github.com/Tank97king/LapTrinhMang/blob/main/CHAT%20TCP/%E1%BA%A2nh/dnu_logo.png?raw=true" alt="DaiNam University Logo" width="200"/>
    </p>

[![Faculty of Information Technology](https://img.shields.io/badge/Faculty%20of%20Information%20Technology-blue?style=for-the-badge)](https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-orange?style=for-the-badge)](https://dainam.edu.vn)

</div>

## 📖 1. Giới thiệu hệ thống

Hệ thống **NoteBlockchain** là một ứng dụng dApp (Decentralized Application) cho phép người dùng tạo, quản lý và lưu trữ ghi chú cá nhân vĩnh viễn trên nền tảng Blockchain Ethereum, kết hợp giải pháp sao lưu tự động về cơ sở dữ liệu MongoDB để tối ưu hóa hiệu năng truy xuất dữ liệu.

Hệ thống bao gồm ba phần chính:
- **Smart Contract (Notes.sol)**: Được phát triển bằng ngôn ngữ Solidity và biên dịch qua Hardhat. Đóng vai trò là cơ sở dữ liệu phi tập trung lưu trữ vĩnh viễn nội dung ghi chú kèm thông tin ví người sở hữu (owner).
- **Backend (server.js)**: API server xây dựng bằng Express.js kết nối tới cơ sở dữ liệu MongoDB để sao lưu dữ liệu nhanh, giúp tìm kiếm và phản hồi danh sách ghi chú với độ trễ cực thấp.
- **Client (React App)**: Giao diện đồ họa ReactJS tương tác trực tiếp với Smart Contract thông qua thư viện `ethers.js` và ví điện tử MetaMask, đồng thời đồng bộ hóa trạng thái ghi chú với Express Backend.

### Các chức năng chính:
- ✅ Kết nối và xác thực tài khoản qua ví MetaMask.
- ✅ Tạo ghi chú mới và thực hiện giao dịch ghi trực tiếp lên Blockchain (Hardhat local).
- ✅ Tự động đồng bộ và sao lưu dữ liệu ghi chú sang MongoDB.
- ✅ Hiển thị danh sách ghi chú theo ví của người dùng đang đăng nhập.
- ✅ Đồng bộ hóa dữ liệu real-time giữa Blockchain và Database MongoDB.
- ✅ Hỗ trợ các file cài đặt và chạy tự động (`setup.bat`, `start.bat`) nhanh chóng trên môi trường Windows.
- ✅ Giao diện Responsive hiện đại, trực quan và dễ sử dụng.

## 🔧 2. Công nghệ sử dụng

- **Ngôn ngữ & Môi trường**: Node.js (v16+), Solidity (v0.8.24).
- **Giao diện người dùng (Frontend)**: ReactJS, CSS (Flexbox, Grid), Ethers.js (kết nối MetaMask).
- **Mạng Blockchain**: Hardhat local node (Ethereum localhost:8545), MetaMask Wallet.
- **Máy chủ Backend**: Express.js, Cors, Dotenv.
- **Cơ sở dữ liệu**: MongoDB (Atlas hoặc Local) thông qua thư viện Mongoose.
- **Công cụ phát triển**: Hardhat Framework, TypeScript.
- **Cấu trúc**: Các gói thành phần được tách biệt trực quan: `contracts/` (Solidity), `scripts/` (deploy smart contract), `frontend/` (React app), và `server.js` (Express backend).

## 🚀 3. Hình ảnh các chức năng

<p align="center">
  <img src="https://github.com/user-attachments/assets/999d3928-4e9d-4469-b788-cda4a2aad982" alt="Giao diện hệ thống" width="800"/>
</p>
<p align="center">
  <em>Hình 1: Giao diện hệ thống</em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e4293905-d95a-4037-aa40-0c739cf7e9cd" alt="Giao dịch nội dung trên blockchain" width="400"/>
</p>
<p align="center">
  <em>Hình 2: Giao dịch nội dung trên blockchain</em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/1e8216a3-5427-43ed-9658-7d2382f5957d" alt="Poster NoteBlockchain" width="800"/>
</p>
<p align="center">
  <em>Hình 3: Poster</em>
</p>


## 📝 4. Hướng dẫn cài đặt và sử dụng

### Yêu cầu hệ thống
- **Node.js** phiên bản 16 hoặc cao hơn.
- **MetaMask Extension** đã được cài đặt trên trình duyệt.
- **MongoDB** (Local MongoDB Server hoặc tài khoản MongoDB Atlas Cloud miễn phí).

### Cài đặt và chạy

Lưu ý: Hướng dẫn dưới đây áp dụng cho hệ điều hành Windows (PowerShell/CMD).

#### 1) Sử dụng file chạy tự động (Khuyên dùng)
Dự án cung cấp sẵn hai file chạy tự động để hỗ trợ người dùng thiết lập nhanh:
1. Sao chép file `.env.example` thành `.env` tại thư mục gốc và cấu hình kết nối MongoDB (`MONGO_URI`).
2. Nhấp đúp chuột hoặc chạy file `setup.bat` từ terminal để tự động cài đặt tất cả thư viện cần thiết và kiểm tra kết nối database.
3. Chạy file `start.bat`. Script sẽ tự động khởi động Hardhat node local, deploy Smart Contract lên mạng local, cập nhật ABI/địa chỉ contract cho React, sau đó khởi chạy song song Backend Server (port 5000) và Web Frontend (port 3000).

#### 2) Chạy thủ công từng thành phần
Nếu bạn muốn kiểm soát chi tiết từng dịch vụ, thực hiện các bước sau:

- **Bước 1: Cài đặt dependencies**
  ```powershell
  # Cài đặt dependencies ở thư mục gốc (cho Backend và Hardhat)
  npm install

  # Di chuyển vào thư mục frontend và cài đặt dependencies cho React
  cd frontend
  npm install
  cd ..
  ```

- **Bước 2: Cấu hình biến môi trường**
  Tạo file `.env` ở thư mục gốc của dự án:
  ```env
  MONGO_URI=mongodb://localhost:27017/NoteBlockchain
  PORT=5000
  ```

- **Bước 3: Khởi chạy Blockchain Node nội bộ (Hardhat Node)**
  ```powershell
  npx hardhat node
  ```
  *(Giữ terminal này chạy liên tục để duy trì mạng Blockchain giả lập)*

- **Bước 4: Triển khai Smart Contract lên mạng Local**
  Mở một cửa sổ terminal mới và thực hiện lệnh:
  ```powershell
  npx hardhat run scripts/deploy.ts --network localhost
  ```
  *(Script deploy sẽ tự động tạo file `frontend/src/Notes.json` chứa ABI và địa chỉ Smart Contract vừa deploy, đồng thời cập nhật địa chỉ vào component `App.js`)*

- **Bước 5: Khởi động Express Backend Server**
  ```powershell
  npm start
  ```
  *(Server sẽ lắng nghe các request đồng bộ hóa tại: `http://localhost:5000`)*

- **Bước 6: Khởi động React Frontend**
  ```powershell
  cd frontend
  npm start
  ```
  *(Giao diện web sẽ tự động mở trên trình duyệt tại: `http://localhost:3000`)*

---

### 3) Tệp và thư mục quan trọng
- `contracts/` — Chứa mã nguồn Smart Contract Solidity (`Notes.sol`).
- `scripts/` — Chứa các file script hỗ trợ deploy contract và cập nhật cấu hình cho frontend.
- `frontend/src/` — Giao diện React App (UI, các components xử lý ví, CSS,...).
- `server.js` — Điểm khởi động của Express Backend API Server kết nối MongoDB.
- `.env` — File lưu trữ thông tin cấu hình biến môi trường (PORT, MONGO_URI).

### 4) Cấu hình / tham số
- **Cổng kết nối mặc định của Server:** 5000.
- **Cổng kết nối mặc định của Frontend:** 3000.
- **Mạng Hardhat localhost:** `http://127.0.0.1:8545` (Chain ID: `31337`).

### 5) Khắc phục sự cố nhanh
- **Lỗi kết nối MongoDB:** Kiểm tra xem dịch vụ MongoDB đã được khởi động trên máy chưa, hoặc kiểm tra lại đường dẫn `MONGO_URI` trong file `.env`.
- **Lỗi MetaMask không thực hiện giao dịch (hoặc lỗi nonce):**
  1. Đảm bảo ví MetaMask của bạn đang kết nối đúng mạng **Localhost 8545** (RPC URL: `http://127.0.0.1:8545`, Chain ID: `31337`).
  2. Nếu gặp lỗi giao dịch bị treo, hãy vào: *Cài đặt MetaMask -> Nâng cao -> Chọn "Xóa dữ liệu hoạt động và tab" (Clear activity tab data)* để reset lại số nonce tài khoản.
- **Lỗi địa chỉ Smart Contract:** Hãy chắc chắn rằng bạn đã chạy script deploy sau khi khởi động Hardhat node, và file `frontend/src/Notes.json` đã được cập nhật đúng địa chỉ mới nhất.

### Gợi ý phát triển tiếp
- Bổ sung tính năng mã hóa nội dung ghi chú (sử dụng Public Key/Private Key) trước khi lưu lên Blockchain để đảm bảo tính riêng tư tuyệt đối.
- Tích hợp thêm IPFS (InterPlanetary File System) để cho phép người dùng đính kèm các tệp tin, hình ảnh có kích thước lớn vào ghi chú.
- Triển khai ứng dụng lên các mạng thử nghiệm công cộng (Testnet) như Sepolia hoặc Arbitrum Sepolia.
- Thêm tính năng sửa và xóa ghi chú trực tiếp trên Smart Contract.

---

## 👤 Thông tin liên hệ  
Họ tên: Bùi Tuấn Đức.  
Lớp: CNTT 16-01.  
Email: tuanduc1282004@gmail.com.

© 2025 AIoTLab, Faculty of Information Technology, DaiNam University. All rights reserved.

---
