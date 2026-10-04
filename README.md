# 🖥️ EARNAPP NODE TOOL

**Phiên bản: v1.0.8**

**EarnApp Node Tool** là ứng dụng Windows giúp quản lý nhiều EarnApp node bằng giao diện trực quan.


Tool hỗ trợ quản lý Docker node, proxy, EarnApp account, đăng ký device, theo dõi CPU/RAM, bật tắt node và tự động cập nhật phiên bản mới.

Website EarnApp: [https://earnapp.com](https://earnapp.com)  
Telegram hỗ trợ: [@haonguyen3](https://t.me/haonguyen3)

> **LƯU Ý BẮT BUỘC:** Máy phải cài và chạy được **Docker Desktop**. Proxy dùng cho tool phải là **proxy dân cư (Residential Proxy) ở quốc gia ngoài Việt Nam**. **Không dùng proxy Việt Nam, proxy datacenter, VPN miễn phí hoặc proxy public.**

---

## **🖥️ Demo Giao Diện**

![Demo giao diện EarnApp Node Tool](LINK_ANH_DEMO)

> Thay `LINK_ANH_DEMO` bằng link ảnh hoặc GIF giao diện thật trước khi đăng lên AMAAutomarket.

---

## **🚀 Tính Năng Chính**

- 🐳 **Quản lý Docker node:** cài image, tạo node, bật/tắt và xóa nhiều node ngay trên giao diện.
- 🌐 **Quản lý proxy:** nhập hàng loạt proxy `SOCKS5` hoặc `HTTP`, kiểm tra trạng thái, độ trễ, TCP/UDP và IP đầu ra.
- 👤 **Quản lý EarnApp account:** lưu account bằng Cookie, gán proxy và tự động làm mới dữ liệu.
- 📱 **Thêm Device EarnApp:** liên kết các node đã tạo vào EarnApp account được chỉ định.
- 📊 **Theo dõi hoạt động:** xem CPU, RAM, trạng thái node, trạng thái proxy và trạng thái device.
- 💰 **Theo dõi account:** xem số dư, tổng tiền, số device, tình trạng online/offline và usage 7 ngày.
- ⚡ **Thao tác hàng loạt:** chọn nhiều node, account hoặc proxy để xử lý cùng lúc.
- 🔐 **License theo thiết bị:** mỗi license dùng cho một máy, hỗ trợ key có thời hạn hoặc vĩnh viễn.
- 🔄 **Tự động cập nhật:** thông báo phiên bản mới, hiển thị tiến độ tải và cài bản cập nhật sau khi người dùng xác nhận.

---

## **⚙️ Tính Năng Nâng Cao**

- 🧭 **Tự động gán theo số thứ tự:** Proxy 1 tương ứng Account 1 và Node 1; Proxy 2 tương ứng Account 2 và Node 2.
- 🛡️ **Chống lộ IP thật:** các thao tác EarnApp API bị chặn khi proxy đã lỗi nhiều lần liên tiếp.
- 📡 **Kiểm tra SOCKS5 UDP:** hiển thị proxy hỗ trợ đầy đủ UDP, chỉ hỗ trợ một phần hoặc chỉ có TCP.
- 🔁 **Auto Refresh Account:** lựa chọn chu kỳ 60, 90, 120 hoặc 300 giây; có thể tắt riêng cho từng account.
- 🧰 **Docker path tùy chỉnh:** tự tìm hoặc nhập đường dẫn Docker Desktop khi Docker được cài ở vị trí khác mặc định.
- 📦 **Giới hạn tài nguyên mặc định:** mỗi node được cấu hình khoảng 256 MB RAM và 0,2 CPU để vận hành ổn định hơn khi chạy nhiều node.
- ♻️ **Khôi phục sau khi Docker khởi động lại:** node sử dụng chính sách `unless-stopped`, trừ những node đã được người dùng chủ động tắt.

---

## **🧰 Yêu Cầu Cài Đặt**

### **💻 Máy tính hoặc VPS Windows**

- ✅ Windows 10/11 64-bit được khuyến nghị.
- ✅ Windows VPS chỉ dùng được khi nhà cung cấp hỗ trợ **Nested Virtualization** và máy thực sự chạy được Docker Desktop với WSL 2.
- ✅ Tài khoản Windows có quyền Administrator để bật WSL, Virtual Machine Platform và cài Docker Desktop.
- ✅ CPU đã bật Virtualization trong BIOS/UEFI hoặc trong cấu hình VPS.
- ✅ Khuyến nghị tối thiểu 8 GB RAM và 20 GB dung lượng trống nếu chạy nhiều node.
- ✅ Ngày, giờ và múi giờ của Windows phải chính xác để license và HTTPS hoạt động ổn định.

> Nhiều VPS giá rẻ không hỗ trợ Nested Virtualization. Trong trường hợp đó, dù cài được ứng dụng thì Docker Desktop vẫn không chạy và tool không thể tạo node. Cần hỏi nhà cung cấp VPS trước khi mua.

### **🐳 Docker Desktop Là Bắt Buộc**

- ✅ Phải cài **Docker Desktop for Windows**.
- ✅ Docker Desktop phải ở trạng thái **Engine running** trước khi mở tool.
- ✅ Docker phải dùng **Linux containers** và WSL 2 backend.
- ✅ Hai Windows Feature bắt buộc là **Windows Subsystem for Linux** và **Virtual Machine Platform**.
- ❌ Chỉ cài WSL nhưng chưa cài Docker Desktop là chưa đủ.
- ❌ Chỉ mở Docker Desktop nhưng Docker Engine đang lỗi cũng không sử dụng được.

### **🌐 Proxy Dân Cư Ngoài Việt Nam Là Bắt Buộc**

- ✅ Chỉ dùng **Residential Proxy / proxy dân cư** có IP thật từ nhà mạng dân cư.
- ✅ Quốc gia của proxy phải là **ngoài Việt Nam**.
- ✅ Proxy phải còn hoạt động, truy cập được HTTPS và có thông tin đăng nhập chính xác.
- ✅ Nên dùng một IP proxy riêng, ổn định cho mỗi node.
- ✅ `SOCKS5` hỗ trợ UDP được ưu tiên; `HTTP` vẫn được tool hỗ trợ.
- ❌ Không dùng proxy Việt Nam.
- ❌ Không dùng proxy datacenter, hosting, cloud, proxy miễn phí hoặc proxy public.
- ❌ Không dùng VPN thay cho proxy.
- ❌ Không dùng một proxy đã chết, đổi IP liên tục hoặc bị giới hạn băng thông.

### **👤 EarnApp Account Và License**

- ✅ Có ít nhất một EarnApp account hợp lệ.
- ✅ Có Cookie đăng nhập EarnApp còn hiệu lực và chứa `xsrf-token`.
- ✅ Có license key EarnApp Node Tool hợp lệ.
- ✅ Có Internet để xác minh license, tải image và gọi EarnApp API.

---

## **⚠️ Chuẩn Bị Trước Khi Chạy**

### **1. Kiểm Tra Virtualization**

Mở **Task Manager** bằng `Ctrl + Shift + Esc`, chọn **Performance → CPU**, sau đó tìm dòng **Virtualization**.

- Nếu hiển thị **Enabled**: tiếp tục cài WSL 2.
- Nếu hiển thị **Disabled** trên máy cá nhân: bật Virtualization trong BIOS/UEFI.
- Nếu là VPS và không có Virtualization: liên hệ nhà cung cấp để bật Nested Virtualization hoặc đổi VPS khác.

### **2. Bật WSL Và Virtual Machine Platform**

Nhấn Start, gõ **PowerShell**, bấm chuột phải **Windows PowerShell → Run as administrator**.

Copy và chạy **từng dòng một**, chờ dòng trước hoàn thành rồi mới chạy dòng tiếp theo:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Khởi động lại Windows. Sau khi máy bật lại, tiếp tục mở PowerShell bằng quyền Administrator và chạy:

```powershell
wsl --update
wsl --set-default-version 2
wsl --status
```

Nếu máy chưa có WSL distribution, có thể chạy:

```powershell
wsl --install
```

Sau lệnh `wsl --install`, hãy khởi động lại Windows nếu hệ thống yêu cầu.

> Không tách một lệnh PowerShell thành nhiều dòng và không tự thêm dấu `` ` ``. Copy nguyên từng dòng như hướng dẫn để tránh lỗi tham số.

### **3. Cài Docker Desktop**

1. Tải Docker Desktop từ trang chính thức: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/).
2. Mở file cài đặt bằng quyền Administrator.
3. Giữ lựa chọn sử dụng **WSL 2 instead of Hyper-V** nếu trình cài đặt hiển thị.
4. Hoàn tất cài đặt và khởi động lại Windows khi được yêu cầu.
5. Mở Docker Desktop và chờ đến khi hiển thị **Engine running**.
6. Trong Docker Desktop, mở **Settings → General** và bật **Use the WSL 2 based engine**.

Kiểm tra Docker bằng PowerShell hoặc Command Prompt:

```powershell
docker version
docker info
```

Nếu hai lệnh hiển thị thông tin cả **Client** và **Server**, Docker Engine đã sẵn sàng.

### **4. Chuẩn Bị Proxy**

Mua proxy từ nhà cung cấp uy tín và kiểm tra các thông tin sau:

- Loại proxy: `SOCKS5` hoặc `HTTP`.
- Host/IP và Port.
- Username và Password.
- Quốc gia proxy không phải Việt Nam.
- Loại mạng là Residential/ISP dân cư, không phải Datacenter.

Định dạng mỗi proxy trong tool:

```text
ip:port:username:password
```

Ví dụ minh họa:

```text
198.51.100.10:1080:proxy_user_01:proxy_password_01
203.0.113.20:1080:proxy_user_02:proxy_password_02
```

Nếu proxy không dùng username/password, vẫn phải giữ đủ bốn phần:

```text
198.51.100.10:1080::
```

> Các IP trên chỉ là IP ví dụ dành cho tài liệu, không phải proxy thật.

### **5. Chuẩn Bị Cookie EarnApp**

Cookie là phiên đăng nhập của EarnApp account. Tool cần chuỗi Cookie đầy đủ, trong đó bắt buộc có `xsrf-token`.

Cách lấy Cookie bằng Chrome hoặc Edge:

1. Mở [https://earnapp.com](https://earnapp.com) và đăng nhập đúng EarnApp account.
2. Mở trang Dashboard/Passive Income của EarnApp.
3. Nhấn `F12` để mở Developer Tools.
4. Chọn tab **Network**.
5. Nhấn `F5` để tải lại trang.
6. Chọn một request có tên `user`, `money`, `devices` hoặc `counters` thuộc `earnapp.com/dashboard/api`.
7. Trong **Headers → Request Headers**, tìm dòng **Cookie**.
8. Copy toàn bộ phần giá trị sau chữ `Cookie:`. Chuỗi đúng thường có dạng `ten_cookie=gia_tri; xsrf-token=gia_tri; ...`.

Ví dụ cấu trúc, không phải Cookie thật:

```text
session=example_value; xsrf-token=example_token; other_cookie=example_value
```

> Cookie có quyền truy cập EarnApp account tương tự mật khẩu. Không gửi Cookie cho người khác, không chụp màn hình để lộ Cookie và không đăng Cookie lên nhóm chat.

---

## **⚡ Setup Nhanh Cho Người Mới**

Thực hiện đúng thứ tự dưới đây. Không bỏ qua bước proxy vì tool yêu cầu có đủ proxy trước khi tạo node.

### **Bước 1: Cài EarnApp Node Tool**

1. Mở file `EarnApp-Node-Tool-Setup-1.0.8-x64.exe`.
2. Chọn thư mục cài đặt hoặc giữ nguyên mặc định.
3. Hoàn tất trình cài đặt.
4. Nếu Windows SmartScreen cảnh báo, chỉ tiếp tục khi file được nhận từ đúng nguồn bán hàng/hỗ trợ chính thức.

Người dùng bản phát hành `.exe` **không cần cài Node.js, npm, GitHub hoặc chạy lệnh lập trình**.

### **Bước 2: Mở Docker Desktop**

1. Mở Docker Desktop.
2. Chờ trạng thái **Engine running**.
3. Giữ Docker Desktop chạy nền trong suốt thời gian vận hành node.

### **Bước 3: Kích Hoạt License**

1. Mở EarnApp Node Tool.
2. Nhập license key vào ô **License key**.
3. Bấm **Kích hoạt license**.
4. Chờ giao diện quản lý node xuất hiện.

Quy tắc license:

- Một key chỉ dùng cho một thiết bị Windows.
- Key có thời hạn được kiểm tra lại mỗi 24 giờ khi app đang mở.
- Key vĩnh viễn không bị kiểm tra định kỳ 24 giờ, nhưng vẫn được xác minh khi kích hoạt hoặc mở lại app.
- Khi key hết hạn được máy chủ xác nhận, tool khóa giao diện, dừng các container EarnApp do tool quản lý và tự thoát.
- Nếu đổi máy hoặc cài lại Windows làm thay đổi Machine ID, cần liên hệ hỗ trợ để reset license.

### **Bước 4: Kiểm Tra Trạng Thái Docker Trong Tool**

Quan sát góc trên giao diện:

- **Docker: Bật** nghĩa là tool đã kết nối Docker Engine.
- **Docker: Tắt** hoặc **Đang kết nối** quá lâu nghĩa là cần kiểm tra Docker Desktop.

Nếu tool không tự tìm thấy Docker:

1. Bấm **Chức năng**.
2. Bấm **Cấu hình**.
3. Bấm **Tìm** để tự phát hiện Docker Desktop.
4. Nếu vẫn không thấy, nhập đường dẫn mặc định:

```text
C:\Program Files\Docker\Docker
```

5. Bấm **Lưu cấu hình**.

### **Bước 5: Cài Docker Image**

1. Bấm **Chức năng**.
2. Bấm **Cài image**.
3. Chờ thông báo **Đã cài image thành công**.

Image được tải qua Internet nên thời gian chờ phụ thuộc tốc độ mạng. Không đóng Docker Desktop hoặc tắt tool trong lúc tải.

### **Bước 6: Thêm Và Kiểm Tra Proxy**

1. Bấm **Proxy** ở thanh trên cùng.
2. Bấm **Thêm**.
3. Dán danh sách proxy, mỗi proxy một dòng theo định dạng `ip:port:user:pass`.
4. Chọn đúng loại **SOCKS5** hoặc **HTTP**. Lựa chọn này áp dụng cho toàn bộ các dòng đang thêm.
5. Bấm **Thêm proxy**.
6. Tick chọn proxy vừa thêm.
7. Bấm **Check**.
8. Chỉ tiếp tục khi proxy hiển thị trạng thái **Live/Đang hoạt động**.

Thứ tự proxy rất quan trọng:

```text
Proxy 1 → Account 1 → Node 1
Proxy 2 → Account 2 → Node 2
Proxy 3 → Account 3 → Node 3
```

Muốn tạo 10 node thì phải thêm ít nhất 10 proxy trước. Mỗi proxy phải là proxy dân cư ngoài Việt Nam và nên có IP đầu ra riêng.

### **Bước 7: Thêm EarnApp Account**

1. Bấm **Account**.
2. Bấm **Thêm Account**.
3. Ở **Account mục tiêu**, chọn **Tạo Account mới (Tự động)**.
4. Ở **Proxy đăng nhập**, chọn **Tự động theo số Account** hoặc chọn proxy cụ thể.
5. Ở **Tự động Refresh Account**, chọn **ON**.
6. Dán chuỗi Cookie đầy đủ vào ô **Chuỗi Cookie (`xsrf-token=...`)**.
7. Bấm **Lưu & Đăng nhập**.
8. Chờ account hiển thị email, số dư, devices và trạng thái **Đã đăng nhập**.

Nếu trạng thái là **Hết phiên**, lấy Cookie mới từ trình duyệt rồi bấm biểu tượng cập nhật Cookie tại dòng account.

### **Bước 8: Tạo Node**

1. Quay lại trang chính.
2. Bấm **Chức năng**.
3. Bấm **Thêm node**.
4. Nhập số lượng node cần tạo.
5. Bấm **Tạo node**.
6. Chờ tool tạo xong và kiểm tra trạng thái từng node.

Nên tạo thử 1 node trước. Khi node đầu tiên hoạt động ổn định, tiếp tục tạo thêm theo tài nguyên của máy và số proxy đang có.

### **Bước 9: Gán Account Cho Node**

1. Tick chọn một hoặc nhiều node trong bảng.
2. Bấm **Gán account**.
3. Chọn EarnApp account đã lưu.
4. Bấm **Gán account** để xác nhận.

Không thể thêm Device EarnApp nếu node chưa được gán account.

### **Bước 10: Thêm Device EarnApp**

1. Đợi node chạy và tạo xong UUID. Với node mới, nên chờ khoảng 1-3 phút.
2. Tick chọn các node đã được gán account.
3. Bấm **Thêm Device EarnApp**.
4. Xác nhận số lượng device cần thêm.
5. Chờ tool xử lý từng node qua proxy của account.
6. Kiểm tra cột **Device Status**:
   - **Thành công:** device đã được liên kết.
   - **Đã tồn tại:** device đã có trong account, không cần thêm lại.
   - **Account hết phiên:** cần cập nhật Cookie.
   - **Thuộc Account khác:** device đang liên kết với EarnApp account khác.
   - **Rate limit/Timeout:** chờ rồi thử lại.

### **Bước 11: Kiểm Tra Kết Quả**

1. Mở trang **Account**.
2. Bấm **Chi tiết** tại account cần kiểm tra.
3. Xem danh sách device, trạng thái online/offline, số tiền và usage 7 ngày.
4. Quay lại trang node để kiểm tra CPU, RAM, Proxy và Device Status.

---

## **🧩 Cấu Hình Quan Trọng**

Người dùng bản `.exe` không cần sửa `config.json`. Các cấu hình cần thiết đều nằm trên giao diện.

### **🐳 Đường Dẫn Docker Desktop**

- Mặc định: `C:\Program Files\Docker\Docker`.
- Chỉ cần thay đổi khi Docker Desktop được cài ở ổ đĩa hoặc thư mục khác.
- Có thể nhập đường dẫn thư mục hoặc đường dẫn đầy đủ tới `Docker Desktop.exe`.

### **🌐 Thứ Tự Proxy**

- Proxy được đánh số theo thứ tự trong trang Proxy.
- Node mới tự lấy proxy có cùng số thứ tự.
- Account mới ở chế độ tự động cũng lấy proxy theo số slot account.
- Không xóa proxy đang được node/account sử dụng nếu chưa chuẩn bị proxy thay thế.

### **🔌 Loại Proxy**

- `SOCKS5`: phù hợp khi nhà cung cấp hỗ trợ SOCKS5; tool kiểm tra cả TCP và UDP.
- `HTTP`: phù hợp với HTTP CONNECT proxy; trạng thái UDP không được hỗ trợ.
- Không chọn `SOCKS5` cho một proxy HTTP hoặc ngược lại.

### **🔄 Auto Refresh Account**

- Chu kỳ hỗ trợ: 60, 90, 120 và 300 giây.
- Bật **ON** để tự cập nhật account.
- Chọn **OFF** cho account không muốn tự động gọi API.
- Nếu gặp rate limit thường xuyên, tăng chu kỳ lên 120 hoặc 300 giây.

### **🔐 License**

- License cần kết nối tới License Server qua HTTPS.
- License có thời hạn được xác minh định kỳ mỗi 24 giờ.
- Vì kiểm tra theo chu kỳ, trạng thái hết hạn có thể được phát hiện chậm tối đa gần 24 giờ so với thời điểm hết hạn chính xác.
- License vĩnh viễn không tạo bộ kiểm tra 24 giờ trong lúc app đang chạy.

### **⬆️ Cập Nhật Ứng Dụng**

Khi có phiên bản mới:

1. Tool hiển thị thông báo phiên bản mới.
2. Bấm **Tải bản cập nhật**.
3. Cửa sổ tiến độ hiển thị phần trăm, dung lượng đã tải và tốc độ tải.
4. Khi tải xong, chọn khởi động lại để cài đặt.
5. Không tắt máy trong lúc installer đang chạy.

---

## **🕹️ Vận Hành Hằng Ngày**

### **Bật Hoặc Tắt Node**

1. Tick chọn node cần thao tác.
2. Bấm **Bật/tắt node**.
3. Nếu các node có trạng thái khác nhau, chọn **Bật tất cả** hoặc **Tắt tất cả**.

### **Xóa Node**

1. Tắt node trước.
2. Tick chọn node cần xóa.
3. Bấm **Xóa node** và xác nhận.

> Xóa node có thể làm mất identity/UUID Docker của node đó. Chỉ xóa khi chắc chắn không cần dùng lại.

### **Làm Mới Thông Số**

Bấm **Tải lại thông số** để cập nhật CPU, RAM, mạng và trạng thái node. Không cần bấm liên tục vì việc đọc nhiều container cũng sử dụng tài nguyên Docker.

### **Giữ Máy Hoạt Động**

- Không tắt Docker Desktop khi node đang chạy.
- Không cho Windows Sleep/Hibernate nếu muốn node hoạt động liên tục.
- Đảm bảo VPS không tự khởi động lại do Windows Update vào giờ vận hành.
- Theo dõi CPU, RAM, dung lượng ổ đĩa và trạng thái proxy mỗi ngày.

---

## **🛡️ Lưu Ý An Toàn**

- 🔑 Không chia sẻ license key công khai.
- 🍪 Cookie EarnApp phải được bảo vệ như mật khẩu; người có Cookie có thể truy cập dữ liệu account.
- 🔐 Không gửi Cookie, proxy password hoặc mật khẩu VPS qua nhóm chat công khai.
- 🧑‍💻 Chỉ dùng account và proxy do bạn sở hữu hoặc được phép sử dụng.
- 🐳 Không bật Docker API không mã hóa trên cổng `2375` ra Internet.
- 🛡️ Không tắt Windows Defender hoặc Firewall chỉ để xử lý lỗi. Hãy thêm ngoại lệ đúng file khi thật sự cần và biết rõ nguồn file.
- 📜 Tuân thủ điều khoản sử dụng hiện hành của EarnApp và nhà cung cấp proxy.
- 💵 Tool hỗ trợ vận hành kỹ thuật, không đảm bảo doanh thu. Kết quả phụ thuộc EarnApp, chất lượng mạng, quốc gia IP, proxy và thời gian online.
- 🌍 Luôn kiểm tra IP đầu ra trước khi chạy: proxy phải là **Residential ngoài Việt Nam**.

---

## **🧯 Lỗi Thường Gặp**

### **🐳 Docker Hiển Thị “Tắt” Hoặc Không Kết Nối**

**Nguyên nhân thường gặp:** Docker Desktop chưa mở, Docker Engine chưa chạy hoặc tool chưa tìm thấy đường dẫn Docker.

**Cách xử lý:**

1. Mở Docker Desktop và chờ **Engine running**.
2. Chạy `docker version` để kiểm tra cả Client và Server.
3. Trong tool, mở **Chức năng → Cấu hình → Tìm → Lưu cấu hình**.
4. Đóng rồi mở lại EarnApp Node Tool.

### **⚠️ Docker Báo HTTP 500 / Server Error**

**Nguyên nhân thường gặp:** Docker Desktop backend hoặc WSL 2 đang lỗi.

**Cách xử lý:**

1. Đóng EarnApp Node Tool.
2. Thoát Docker Desktop.
3. Mở PowerShell bằng quyền Administrator và chạy:

```powershell
wsl --shutdown
```

4. Mở lại Docker Desktop.
5. Chờ **Engine running**, sau đó mở lại tool.

Nếu vẫn lỗi, chạy:

```powershell
wsl --status
wsl --update
docker version
```

### **🧩 WSL 2 Hoặc Virtual Machine Platform Chưa Bật**

Mở PowerShell bằng quyền Administrator và chạy từng dòng:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Khởi động lại Windows, sau đó chạy:

```powershell
wsl --update
wsl --set-default-version 2
```

### **🖥️ VPS Không Hỗ Trợ Virtualization**

Không thể sửa lỗi này bằng EarnApp Node Tool. Liên hệ nhà cung cấp VPS để bật Nested Virtualization hoặc chuyển sang VPS hỗ trợ WSL 2/Docker Desktop.

### **📦 Báo “Chưa Tìm Thấy Image”**

Mở **Chức năng → Cài image**, chờ tải hoàn tất rồi tạo node lại. Đảm bảo Docker Desktop và Internet vẫn hoạt động trong lúc tải.

### **🌐 Báo “Cần Proxy Số ...” Khi Tạo Node**

Tool chưa có đủ proxy theo số thứ tự. Ví dụ muốn tạo Node 6 nhưng danh sách chỉ có 5 proxy. Hãy thêm và Check đủ proxy trước khi tạo lại.

### **🔴 Proxy Hiển Thị Dead, Timeout Hoặc TCP Error**

Kiểm tra:

- Host/IP và Port có chính xác không.
- Username/Password có đúng không.
- Đã chọn đúng loại `SOCKS5` hoặc `HTTP` chưa.
- Proxy có yêu cầu whitelist IP của máy/VPS không.
- Gói proxy còn hạn và còn băng thông không.
- IP đầu ra có phải Residential ngoài Việt Nam không.

Nếu proxy lỗi, thay proxy mới trước khi tiếp tục. Không chạy node bằng kết nối thật để thay thế proxy.

### **🟡 SOCKS5 Hiển Thị UDP Partial Hoặc UDP No**

Proxy vẫn kết nối TCP nhưng UDP không đầy đủ. Hỏi nhà cung cấp proxy về hỗ trợ **SOCKS5 UDP ASSOCIATE** hoặc đổi sang proxy SOCKS5 Residential hỗ trợ UDP.

### **🍪 Account Báo “Cookie Thiếu xsrf-token”**

Bạn đã copy thiếu Cookie hoặc chỉ copy một cookie đơn lẻ. Hãy lấy toàn bộ dòng **Cookie** từ Request Headers và kiểm tra có `xsrf-token=` trước khi dán lại.

### **🔒 Account Báo 401/403 Hoặc “Hết Phiên”**

Cookie EarnApp đã hết hạn. Đăng nhập lại EarnApp trong trình duyệt, lấy Cookie mới và cập nhật lại account trong tool.

### **👤 Account Chưa Được Gán Proxy**

Mở Account, cập nhật account và chọn một proxy Live. Chế độ tự động sẽ dùng proxy theo số slot account nếu danh sách proxy đã đủ.

### **📱 Không Thêm Được Device EarnApp**

Kiểm tra theo thứ tự:

1. Node đang chạy và đã chờ đủ thời gian tạo UUID.
2. Node đã được gán account.
3. Account có Cookie còn hạn.
4. Proxy của account đang Live.
5. Device chưa liên kết với account khác.
6. EarnApp API không bị rate limit.

### **⏳ Báo Too Many Requests / Rate Limit**

Tạm dừng thao tác ít nhất 2 phút rồi thử lại. Không bấm liên tục nút **Thêm Device EarnApp**. Nếu account tự refresh quá nhanh, tăng chu kỳ lên 120 hoặc 300 giây.

### **🔗 Device Thuộc Account Khác**

Device đã được liên kết với một EarnApp account khác. Mở account cũ để gỡ/xóa device đó, chờ EarnApp cập nhật rồi thử liên kết lại với account đúng.

### **🔐 License Không Kích Hoạt Được**

Kiểm tra:

- Máy có Internet và ngày giờ Windows chính xác.
- Firewall không chặn License Server trên cổng HTTPS 443 (domain cấu hình trong `src/main/app-config.js`).
- License key được nhập đủ ký tự, không có khoảng trắng thừa.
- Key chưa hết hạn, chưa bị revoke và chưa gắn với máy khác.

Nếu đã đổi máy/cài lại Windows, liên hệ hỗ trợ để kiểm tra và reset Machine ID.

### **⌛ License Hết Hạn Khi App Đang Chạy**

License có thời hạn được kiểm tra mỗi 24 giờ. Khi lần kiểm tra tiếp theo xác nhận key đã hết hạn, tool khóa giao diện, dừng các container EarnApp do tool quản lý và tự thoát. Gia hạn hoặc kích hoạt key mới trước khi tiếp tục.

### **⬆️ Bấm Tải Cập Nhật Nhưng Chưa Thấy Cài Ngay**

Sau khi bấm tải, tool hiển thị cửa sổ tiến độ. Hãy chờ tải đủ 100%. Khi thông báo bản cập nhật đã sẵn sàng xuất hiện, chọn khởi động lại để cài.

Nếu tải thất bại, kiểm tra Internet, Firewall và dung lượng ổ đĩa rồi mở tool thử lại.

### **💾 Docker Dùng Nhiều Dung Lượng**

Mở PowerShell và xem dung lượng Docker đang sử dụng:

```powershell
docker system df
```

Không tự chạy lệnh xóa dữ liệu Docker nếu chưa sao lưu hoặc chưa hiểu rõ, vì có thể làm mất container, image, volume và identity của node.

---

## **📞 Thông Tin Liên Hệ**

Hỗ trợ cài đặt, license hoặc báo lỗi:

- 💬 Telegram: [@haonguyen3](https://t.me/haonguyen3)
- 🌐 EarnApp: [https://earnapp.com](https://earnapp.com)

Khi báo lỗi, gửi các thông tin không nhạy cảm sau:

- Phiên bản EarnApp Node Tool.
- Phiên bản Windows.
- Máy cá nhân hay VPS.
- Ảnh chụp thông báo lỗi, nhưng phải che license key, Cookie, proxy password và mật khẩu VPS.
- Kết quả `wsl --status` và `docker version` nếu lỗi liên quan Docker.

> Bộ phận hỗ trợ không cần mật khẩu VPS, Cookie đầy đủ hoặc proxy password để xem lỗi cơ bản. Không gửi các thông tin bí mật này qua tin nhắn.

---

## **📋 Checklist Trước Khi Chạy**

- [ ] Virtualization/Nested Virtualization đã bật.
- [ ] WSL 2 và Virtual Machine Platform đã bật.
- [ ] Docker Desktop đã cài và hiển thị Engine running.
- [ ] Tool hiển thị Docker: Bật.
- [ ] License đã kích hoạt.
- [ ] Docker image đã cài thành công.
- [ ] Đã thêm đủ proxy cho số node cần tạo.
- [ ] Tất cả proxy là Residential ngoài Việt Nam.
- [ ] Tất cả proxy đã Check và hiển thị Live.
- [ ] EarnApp account đã lưu bằng Cookie có `xsrf-token`.
- [ ] Node đã được gán account.
- [ ] Device Status đã hiển thị Thành công hoặc Đã tồn tại.
- [ ] Windows không Sleep và Docker Desktop luôn chạy nền.

---

**EarnApp Node Tool là công cụ quản lý độc lập và không phải sản phẩm chính thức của EarnApp. Người dùng tự chịu trách nhiệm tuân thủ điều khoản của EarnApp, nhà cung cấp proxy và pháp luật tại nơi sử dụng.**
