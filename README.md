# Mạch phát triển MKE-K01 ESP32-S3 Dev Kit

Mạch phát triển MKE-K01 ESP32-S3 Dev Kit là board phát triển ứng dụng dựa trên module ESP32-S3-WROOM-1 chính hãng Espressif, được thiết kế tương thích với nguyên mẫu ESP32-S3 DevKitC-1, giúp người dùng tận dụng tối đa tài liệu, sơ đồ chân và phần mềm mẫu có sẵn. Sản phẩm tối ưu cho phát triển các dự án IoT, AIoT, nhúng và điều khiển không dây với hiệu năng xử lý mạnh mẽ và kết nối Wi-Fi/BLE linh hoạt.

**Ứng dụng thực tế**
- Hệ thống IoT/Smart Home: điều khiển đèn, cảm biến từ xa
- AIoT/Computer Vision nhẹ: nhận dạng cơ bản trên thiết bị
- Thu thập dữ liệu không dây: sensor network, môi trường
- Robot điều khiển và giáo dục STEM
- Thiết bị điều khiển hiển thị/LED thông minh
- Gateway Protocols/Edge Devices

## Ưu điểm nổi bật
- Sử dụng module trung tâm ESP32-S3-WROOM-1 chính hãng Espressif và các linh kiện chính hãng chất lượng cao.
- Ba tùy chọn cấu hình bộ nhớ:
  - N16R8 – 16 MB Flash + 8 MB PSRAM (tối ưu cho ứng dụng AI/ML, buffer lớn)
  - MCN4 – 4 MB Flash không PSRAM (phù hợp dự án cơ bản)
  - MCN16 – 16 MB Flash không PSRAM (nhiều chương trình hơn, chi phí thấp)
- Hỗ trợ kết nối Wi-Fi 2.4 GHz và Bluetooth Low Energy (BLE5)
- CPU Dual-core Xtensa® LX7 cho hiệu năng cao, xử lý đa nhiệm mượt
- LED RGB tích hợp điều khiển bằng GPIO
- Cổng USB OTG + USB-to-UART onboard giúp nạp chương trình dễ dàng và giao tiếp với máy tính
- Tích hợp đầy đủ chân GPIO breakout, tương thích thiết kế breadboard
- Hỗ trợ môi trường phát triển Arduino IDE, ESP-IDF, MicroPython

## Thông số kỹ thuật
- Nguồn hoạt động: 5VDC từ cổng USB
- Module trung tâm: ESP32-S3-WROOM-1 (Wi-Fi + BLE5) chính hãng Espressif
- CPU: Xtensa® Dual-core LX7, up to 240 MHz
- Bộ nhớ Flash & PSRAM tùy chọn:
  - 16 MB Flash + 8 MB PSRAM (N16R8)
  - 4 MB Flash không PSRAM (MCN4)
  - 16 MB Flash không PSRAM (MCN16)
- Kết nối không dây:
  - Wi-Fi 802.11 b/g/n (2.4 GHz)
  - Bluetooth Low Energy BLE5
- IC giao tiếp USB-UART: High-speed Serial UART CH343P chính hãng có tốc độ truyền tối đa lên đến 6Mbp tương thích chuẩn USB 2.0, tự nhận Driver trên hầu hết các hệ điều hành.
- Cổng USB
  - Cổng USB-to-UART (MicroUSB/USB-C tùy phiên bản) dùng để cấp nguồn, nạp chương trình và giao tiếp debug
  - Cổng USB OTG full-speed (USB 1.1) trên chip ESP32-S3 hỗ trợ giao tiếp USB thiết bị/giao diện nếu phần mềm hỗ trợ
- GPIO và giao tiếp
  - Hầu hết chân GPIO của ESP32-S3 module được breakout ra header 2 bên, dễ dàng dùng cho các cảm biến/peripherals
  - Các chuẩn giao tiếp bao gồm: UART, SPI, I2C, I2S, PWM, ADC
  - Lưu ý: Một số chân (GPIO35/36/37) bị dùng bởi kết nối Flash/PSRAM trên module nên không dùng được ngoài
- Nút chức năng
  - RESET – khởi động lại MCU
  - BOOT (Download) – đưa board vào chế độ nạp firmware
- LED chỉ báo
  - LED RGB addressable nằm trên board, được điều khiển qua GPIO48 giúp hiển thị trạng thái, debugging hoặc ánh sáng tùy chỉnh
  - LED Power 3.3 V bật khi board được cấp nguồn qua USB
- Giao diện lập trình: Arduino IDE, ESP-IDF, MicroPython
- Kích thước nhỏ gọn và thiết kế tiện cho prototyping

## Kích thước
- Kích thước mạch:
![MKE-K01 ESP32-S3 DK](/extras/esp32s3dk_0.png)

## Hướng dẫn sử dụng cơ bản với Arduino IDE
### Bước 1: Cài đặt Arduino IDE
- Tải và cài đặt [Phần mềm Arduino IDE từ trang chủ Arduino](https://www.arduino.cc/en/software) phù hợp với hệ điều hành đang sử dụng.
### Bước 2: Kết nối mạch với máy tính
- Kết nối MKE-K01 ESP32-S3 Dev Kit với máy tính bằng cáp USB.
- Khi kết nối thành công, LED nguồn (ON) trên mạch sẽ sáng.
### Bước 3: Cài đặt driver CH340
- MKE-K01 ESP32-S3 Dev Kit sử dụng IC CH343P để giao tiếp USB–UART.
- Nếu máy tính chưa nhận mạch, hãy cài đặt Driver CH343P phù hợp với hệ điều hành, thông thường Driver sẽ tự nhận trên hầu hết các hệ điều hành.
### Bước 4: Cấu hình mạch trong Arduino IDE
Thực hiện các thiết lập sau trong Arduino IDE:
- Chọn loại board: Tools → Board → 
- Chọn cổng kết nối (Port): Tools → Port → chọn cổng tương ứng với MKE-K01 ESP32-S3 Dev Kit (nếu chưa xác định được, hãy rút cáp USB và cắm lại để nhận diện cổng mới xuất hiện)
![MKE-K01 ESP32-S3 DK](/extras/esp32s3dk_1.png)
![MKE-K01 ESP32-S3 DK](/extras/esp32s3dk_2.png)
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
- Nên sử dụng với nguồn điện chất lượng tốt
- Luôn đảm bảo mạch:
  - Không bị chập mạch
  - Không đấu sai cực nguồn
  - Khi mạch được cấp nguồn ngoài, không rút/cắm USB liên tục trong lúc tải lớn đang hoạt động
- Nên ngắt nguồn ngoài trước khi:
  - Thay đổi đấu nối phần cứng
  - Kết nối lại với máy tính để nạp chương trình
 ## Hình ảnh sản phẩm
![MKE-K01 ESP32-S3 DK](/extras/esp32s3dk_3.png)
![MKE-K01 ESP32-S3 DK](/extras/esp32s3dk_4.png)





