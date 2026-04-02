# Hướng dẫn cài đặt OpenClaw trên macOS

## Cài đặt công cụ cần thiết

### Cài đặt và cập nhật Homebrew

Trước khi bắt đầu cài đặt, hãy đảm bảo rằng Homebrew đã được cài đặt trên hệ thống và các gói phần mềm đã được cập nhật:

1. Truy cập [trang web chính thức của Homebrew](https://brew.sh) và sao chép đường dẫn hiển thị trên trang.

    ![image.png](../assets/image%2029.png)

2. Dán lệnh vào cửa sổ dòng lệnh. Nhấn **Enter** để xác nhận bạn muốn cài đặt Homebrew và đợi quá trình cài đặt hoàn tất.



3. Cập nhật danh sách gói bằng cách nhập:

    ```bash
    brew update
    ```

    ![image.png](../assets/image%2030.png)


### Cài đặt Node.js và NPM trên máy Mac

Sau khi cài đặt Homebrew, hãy làm theo các bước dưới đây để cài đặt Node.js và NPM:

1. Nhập lệnh cài đặt:

    ```bash
    brew install node
    ```

    Homebrew tải xuống và cài đặt Node.js, các gói NPM và các gói phụ thuộc của chúng.

    ![image.png](../assets/image%2031.png)

2. Hãy xác nhận rằng bạn đã cài đặt Node.js thành công bằng cách kiểm tra phiên bản:

    ```bash
    node -v
    ```

    Hệ thống hiển thị phiên bản Node.js như là kết quả đầu ra của lệnh.

     ![image.png](../assets/image%2032.png)


3. Kiểm tra phiên bản NPM đã cài đặt bằng cách gõ:

    ```bash
    npm -v
    ```

    Số phiên bản NPM được hiển thị.

     ![image.png](../assets/image%2033.png)



## Cài đặt và thiết lập OpenClaw

### Cài đặt

Mở **Terminal** và chạy lệnh sau:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

Nhập xong chờ đến khi cài đặt hoàn tất, thường cần vài phút.

![image.png](../assets/image%2034.png)



### Thiết lập ban đầu

#### Thao tác

- Dùng mũi tên (**←**/**→**) để di chuyển trái/phải
- Dùng mũi tên (**↑**/**↓**) để di chuyển lên/xuống
- Nhấn `Space` để chọn các lựa chọn bắt đầu bằng **☐**
- Nhấn `Enter` để xác nhận lựa chọn

#### Chạy thiết lập

```bash
openclaw onboard --install-daemon
```

1. **I understand this is personal-by-default and shared/multi-user use requires lock-down. Continue?**

    Chọn `Yes`

    ![image.png](../assets/image%206.png)

2. **Setup mode**

    Chọn `QuickStart`

    ![image.png](../assets/image%207.png)

3. **Model/auth provider**

    Chọn `OpenRouter`

    ![image.png](../assets/image%208.png)

4. **Enter OpenRouter API key**

    Nhập API key của bạn (lấy từ [OpenRouter](https://openrouter.ai/keys))

    ![image.png](../assets/image%209.png)

5. **Default model**

    Chọn `openrouter/stepfun/step-3.5-flash`

    ![image.png](../assets/image%2010.png)

6. **Select channel (QuickStart)**

    Chọn `Skip for now`

    ![image.png](../assets/image%2011.png)

7. **Search provider**

    Chọn `Skip for now`

    ![image.png](../assets/image%2012.png)

8. **Configure skills now? (Recommended)**

    Chọn `No`

    ![image.png](../assets/image%2013.png)

9. **Enable hooks?**

    Chọn `Skip for now`

    ![image.png](../assets/image%2014.png)

10. **How do you want to hatch your bot?**

    Chọn `Do this later`

    ![image.png](../assets/image%2015.png)


Sau khi hoàn tất các lựa chọn, bạn đã thiết lập ban đầu thành công.

![image.png](../assets/image%2016.png)

**Lưu ý:** Sau lựa chọn 10, OpenClaw sẽ tự động mở cửa sổ terminal mới để chạy gateway. Nếu không tự động mở, có thể mở thủ công:

```bash
openclaw gateway
```

![image.png](../assets/image%2017.png)

Đảm bảo gateway luôn được mở để sử dụng OpenClaw và OpenClaw có thể tự thao tác trên macOS.

### Sử dụng Dashboard

Mở **Terminal** và nhập lệnh sau

```bash
openclaw dashboard
```

Dashboard sẽ được mở tự động trên trình duyệt

![image.png](../assets/image%2018.png)

Nếu không tự động mở, sao chép URL và mở trong trình duyệt


### Sử dụng kênh chat

Sẽ có nhiều kênh để bạn có thể sử dụng, trong hướng dẫn này sẽ dùng Telegram.

#### Thiết lập kênh chat Telegram

Mở **Terminal** và nhập lệnh sau (cách lấy bot token được hướng dẫn bên dưới).

```bash
openclaw channels add --channel telegram --token <bot-token>
```

![image.png](../assets/image%2020.png)

#### Cách lấy bot token

1. Mở Telegram, tìm kiếm BotFather và nhấn Start

    ![image.png](../assets/image%2021.png)

2. Nhập `/newbot` vào khung chat, nhấn `Enter`

    ![image.png](../assets/image%2022.png)

3. Đặt tên cho bot

    ![image.png](../assets/image%2023.png)

4. Chọn username cho bot, lưu ý phải kết thúc bằng `bot`

    ![image.png](../assets/image%2024.png)

5. Bot token sẽ được hiển thị trong khung chat, sao chép và sử dụng cho lệnh trên

    ![image.png](../assets/image%2025.png)


#### Cách ghép nối OpenClaw với Telegram Bot

Để Telegram Bot vừa tạo tương tác thay OpenClaw, cần ghép nối chúng.

Mở **Terminal** và nhập lệnh sau (cách lấy code được hướng dẫn bên dưới)

```bash
openclaw pairing approve telegram <code>
```

![image.png](../assets/image%2035.png)

#### Cách lấy code

1. Mở Telegram, tìm kiếm username bot vừa tạo, nhấn Start

    ![image.png](../assets/image%2027.png)

2. Sao chép code hiển thị trong khung chat và dùng cho lệnh trên

    ![image.png](../assets/image%2028.png)


## Tổng kết

Hướng dẫn trên đã hoàn thành các bước cài đặt và thiết lập OpenClaw hoạt động thông qua kênh chat Telegram
