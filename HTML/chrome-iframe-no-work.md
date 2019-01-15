# chrome iframe no work

在網路上查到的狀況大概是這樣，Chrome 65 更新後 hidden 下的 iframe 皆不會載入。

不確定這個調整的目地為何，可能是為了增加瀏覽器效能、避免用戶背端載入高風險的網頁。

在 hidden 的狀況下，用 jquery 查詢 $(iframe).attr('src') 皆回傳為 null

即使用 script 硬塞 attribute src 也沒有辦法

參考文章
https://stackoverflow.com/questions/49281164/chrome-65-cant-print-hidden-iframe

- - -
## 可行的調整方式

### 列印隱藏的 iframe 內容

style 可調整為

    visibility: hidden;
    position: absolute;

### iframe 依照視窗寬度決定是否顯示 hidden*

在script偵測畫面調整，重新載iframe

    $(window).resize(function () {
        // .hidden-xs 為768px，CSS 的與 script 有落差請勿剛好設在768
        if ($(window).width() >= 700) {
            $(document.getElementsByName("calendar")).attr('src', '/iframe-calendar.html');
        }
    });

參考文章
http://blog.shihshih.com/window-width-not-the-same-as-media-query/