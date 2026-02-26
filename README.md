# Mạch phát triển MKE-K01 ESP32-S3 Dev Kit
## Giới thiệu sản phẩm
Vietduino Uno là bo mạch phát triển do MakerEDU nghiên cứu và sản xuất, dựa trên nguyên mẫu Arduino Uno, được nâng cấp toàn diện về phần cứng, hướng tới độ ổn định cao, hiệu suất tốt và độ bền lâu dài – đặc biệt phù hợp cho Giáo Dục STEM, Phòng Thí Nghiệm, Maker Space, nghiên cứu và phát triển ứng dụng nhúng cơ bản.
Mạch được thiết kế tương thích hoàn toàn với Arduino Uno về hình dạng, chuẩn chân tín hiệu và cách sử dụng, cho phép người dùng tận dụng trực tiếp toàn bộ hệ sinh thái Arduino: thư viện, ví dụ mẫu, shield và cộng đồng hỗ trợ.
## Ưu điểm nổi bật
- Tương thích hoàn toàn Arduino Uno, giữ nguyên form factor, vị trí chân và chuẩn giao tiếp, dễ dàng thay thế Arduino Uno trong các dự án hiện có.
- Nâng cấp mạch nguồn xung giảm áp hiệu suất chuyển đổi cao, tỏa nhiệt thấp, tiết kiệm năng lượng.
- Hỗ trợ dải điện áp đầu vào rộng: **6 ~ 24VDC**
- Dòng đầu ra lớn:
  - **5VDC: tối đa 1500mA**
  - **3.3VDC: tối đa 700mA**
- **IC chuyển đổi USB–UART chính hãng**
  - Sử dụng IC CH340, đảm bảo giao tiếp ổn định, nạp chương trình tin cậy và độ bền cao khi sử dụng lâu dài.
- **Bảo vệ cổng USB máy tính**
  - Tích hợp chức năng tự động cách ly nguồn USB khi cấp nguồn ngoài qua chân VIN hoặc Jack DC, giúp tăng độ an toàn trong quá trình học tập và thử nghiệm.
## Thông số kỹ thuật
### Thông tin chung
- Model: Vietduino Uno (Arduino Uno Compatible)
- Vi điều khiển: ATmega328P-PU (Microchip)
- Điện áp hoạt động: 5VDC
- Điện áp đầu vào VIN: 6 ~ 24VDC
- Clock Speed: 16MHz
### Bộ nhớ
- Flash Memory: 32 KB (0.5 KB dùng cho bootloader)
- SRAM: 2 KB
- EEPROM: 1 KB
### Dòng điện
- Dòng DC mỗi chân I/O: Tối đa 20 mA
- Dòng DC chân 3V3: Tối đa 700 mA
- Dòng DC chân 5V: Tối đa 1500 mA
### Giao tiếp & nạp chương trình
- IC USB–UART: CH340
- Cổng kết nối máy tính: USB-C hoặc USB-B
### Các chân tín hiệu
- Digital I/O: 14 chân(D0 ~ D13, trong đó 6 chân hỗ trợ PWM)
- PWM: D3, D5, D6, D9, D10, D11
- Analog Input: 6 chân (A0 ~ A5)
- LED_BUILTIN: D13
### Kích thước
- Kích thước mạch: 68.6 × 53.34 mm
![Vietduino Uno](/extras/VietduinoUno1.jpg)
## Hướng dẫn sử dụng cơ bản với Arduino IDE
### Bước 1: Cài đặt Arduino IDE
- Tải và cài đặt [Phần mềm Arduino IDE từ trang chủ Arduino](https://www.arduino.cc/en/software) phù hợp với hệ điều hành đang sử dụng.
### Bước 2: Kết nối mạch với máy tính
- Kết nối Vietduino Uno với máy tính bằng cáp USB.
- Khi kết nối thành công, LED nguồn (ON) trên mạch sẽ sáng.
### Bước 3: Cài đặt driver CH340
- Vietduino Uno sử dụng IC CH340 để giao tiếp USB–UART.
- Nếu máy tính chưa nhận mạch, hãy cài đặt Driver CH340 phù hợp với hệ điều hành.
### Bước 4: Cấu hình mạch trong Arduino IDE
Thực hiện các thiết lập sau trong Arduino IDE:
- Chọn loại board: Tools → Board → Arduino AVR Boards → Arduino Uno
- Chọn cổng kết nối (Port): Tools → Port → chọn cổng tương ứng với Vietduino Uno (nếu chưa xác định được, hãy rút cáp USB và cắm lại để nhận diện cổng mới xuất hiện)
![Vietduino Uno](/extras/VietduinoUno3.jpg)
![Vietduino Uno](/extras/VietduinoUno4.jpg)
### Bước 5: Nạp chương trình thử nghiệm (Blink)
Sau khi cấu hình xong, bạn có thể nạp chương trình Blink để kiểm tra mạch.
Chương trình này sẽ làm LED_BUILTIN tại chân D13 chớp tắt mỗi 1 giây.
```ino
/*
  Blink
  Turns an LED_BUILTIN on D13 of Vietduino Uno for one second, then off for one second, repeatedly.
*/
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN on D13 as an output.
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(13, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  digitalWrite(13, LOW);   // turn the LED off by making the voltage LOW
  delay(1000);                      // wait for a second
}
```
## Lưu ý sử dụng an toàn
- Không đặt mạch trên bề mặt kim loại dẫn điện
- Tránh môi trường:
  - Ẩm ướt
  - Nhiệt độ cao
  - Nhiều bụi dẫn điện
- Nên sử dụng nguồn DC adapter chất lượng tốt
- Luôn đảm bảo mạch:
  - Không bị chập mạch
  - Không đấu sai cực nguồn
  - Khi mạch được cấp nguồn ngoài, không rút/cắm USB liên tục trong lúc tải lớn đang hoạt động
- Nên ngắt nguồn ngoài trước khi:
  - Thay đổi đấu nối phần cứng
  - Kết nối lại với máy tính để nạp chương trình
 ## Hình ảnh sản phẩm
![Vietduino Uno](/extras/VietduinoUno5.png)
![Vietduino Uno](/extras/VietduinoUno6.png)
