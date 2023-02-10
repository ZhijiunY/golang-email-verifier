## create golang-email-verifier

Learn from Akhil Sharma on Youtube

一些名詞解釋：

SPF (Sender Policy Framework) 寄件者政策框架：
SPF 用來規範在選定的郵件發送服務器位址，可以用來發送寄件人的網域郵件。這樣機制可以避免垃圾信濫發業者，偽裝網域發送假冒郵件。SPF 的設定裡面，列出明確許可的郵件發信機網域名稱，郵件收信服務器透過檢查發信人網域的 SPF，就知道這封電子郵件是否來自被允許的發信機位址。

DKIM (DomainKeys Identified Mail)，網域驗證郵件，用來防止郵件內容遭到竄改:
DKIM 是一種電腦數位簽章，採用公鑰與私鑰這種加密驗證法進行。在發送郵件時由發信服務器對郵件以私鑰進行簽章，而在郵件接收服務器上，會透過 DNS 到發信者的網域查詢 DKIM 紀錄，擷取上面記載的公鑰資料，然後對這封郵件做簽章解碼，如果公鑰與私鑰能配對成功，代表郵件確實為原始發信機所發出。

DMARC 是用來輔助 SPF 與 DKIM 的不足:
用來讓發信端網域通知收件端郵件服務器，當遇到 SPF 與 DKIM 的設定檢查不過時，進行的處理方式。最知名的案例就是 Yahoo 在2014年，宣布 DMARC 設為「拒絕」，也就是說所有不是從 Yahoo 郵件服務器發出的郵件，寄信人都不能用 Yahoo 郵件地址。

SPF (Sender Policy Framework) 的作用、語法和設定方式。 簡單來說就是讓人家知道收到你的網域的電子郵件時， 只有其 IP 來自於 SPF 中有寫到的 IP 才是認可的來源這樣。 其實就是一筆特殊格式的 DNS TXT 紀錄

來自：
https://www.richesinfo.com.tw/index.php/mxmail/mxmail-faq/267-dkim-dmarc

https://tech-blog.cymetrics.io/posts/crystal/email-sec-settings-spf/
