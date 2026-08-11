---
title: "Quản trị & tuỳ biến Copilot — public code filter, content exclusions, IP indemnity"
section: 00-Foundations/07-GitHub-Copilot
tags: [github-copilot, gh-300, governance, privacy, content-exclusion, ip-indemnity, troubleshooting, foundations]
related:
  - "[[00-MOC-GH300]]"
  - "[[02-Copilot-la-gi-va-cac-goi]]"
  - "[[05-Copilot-xu-ly-Prompt-va-Du-lieu]]"
difficulty: ⭐⭐⭐⭐
estimated_time: 50m
source: [Microsoft Learn — Management and customization considerations with GitHub Copilot]
---

# Note 14 — Quản trị & tuỳ biến Copilot

> **TL;DR:** Đây là domain **Privacy fundamentals and context exclusions** — **15% đề GH-300**. Hai bảng tính năng theo gói cần thuộc: **management policy** (public code filter có ở MỌI gói; **user management, data excluded from training by default, enterprise-grade security, IP indemnity, content exclusions, SAML SSO, usage metrics** chỉ từ **Business**; **Require GitHub Enterprise Cloud** chỉ **Enterprise**) và **customization** (**tailor chat to private codebase** và **attach knowledge bases** chỉ **Enterprise**; **Copilot Extensions** có ở mọi gói). Ba bảo vệ hợp đồng: **IP indemnity** (Business/Enterprise — ⚠️ **chỉ có hiệu lực khi Matching public code được đặt BLOCK**) · **DPA** · **Copilot Trust Center**. **Public code filter** quản ở **3 scope**. **Content exclusions** (chỉ Business/Enterprise) chặn file khỏi code completion và Chat, nhưng có **3 giới hạn**: IDE (không áp khi dùng `@github`), **semantic information** vẫn lọt, và **chỉ áp cho member của tổ chức đã cấu hình**. Đổi content exclusion mất **tới 30 phút** để có hiệu lực.

## 1. Tính năng theo gói

### 1.1. Management policy features

| Feature | **Free\* & Pro** | **Business** | **Enterprise** |
|---|:---:|:---:|:---:|
| **Public code filter** | ✅ | ✅ | ✅ |
| **User management** | ❌ | ✅ | ✅ |
| **Data excluded from training by default** | ❌ | ✅ | ✅ |
| **Enterprise-grade security** | ❌ | ✅ | ✅ |
| **IP indemnity** | ❌ | ✅ | ✅ |
| **Content exclusions** | ❌ | ✅ | ✅ |
| **SAML SSO authentication** | ❌ | ✅ | ✅ |
| **Require GitHub Enterprise Cloud** | ❌ | ❌ | ✅ |
| **Usage metrics** | ❌ | ✅ | ✅ |

*\*GitHub Copilot Free có giới hạn sử dụng.*

### 1.2. Customization features

| Feature | **Free\* & Pro** | **Business** | **Enterprise** |
|---|:---:|:---:|:---:|
| **Tailor chat conversations to your private codebase** | ❌ | ❌ | ✅ |
| **Unlimited integrations with Copilot Extensions** *(public beta)* | ✅ | ✅ | ✅ |
| **Build a private extension for internal tooling** *(public beta)* | ✅ | ✅ | ✅ |
| **Attach knowledge bases to chat for organizational context** | ❌ | ❌ | ✅ |

```
★ Insight ─────────────────────────────────────
• Hai bảng này là "bản đồ ranh giới gói" chuẩn xác nhất trong cả giáo trình —
  đáng thuộc hơn phần mô tả văn xuôi ở note 02. Ba mốc dễ nhớ:
    - Public code filter là tính năng DUY NHẤT trong bảng management có ở
      MỌI gói (kể cả Free).
    - "Require GitHub Enterprise Cloud" là dòng DUY NHẤT chỉ Enterprise có
      trong bảng management — và nó là ĐIỀU KIỆN, không phải quyền lợi.
    - Trong bảng customization, hai dòng Enterprise-only đều nói về CODEBASE
      RIÊNG (tailor chat to private codebase, attach knowledge bases), còn
      hai dòng Extensions thì AI CŨNG CÓ.
• Bẫy hay gặp: "content exclusions" nghe như tính năng privacy cơ bản nên dễ
  đoán là mọi gói đều có — SAI, chỉ từ Business.
─────────────────────────────────────────────────
```

### 1.3. Bốn yếu tố cân nhắc khi chọn gói

| Yếu tố | Nội dung |
|---|---|
| **Data privacy and security** | Chỉ **Business và Enterprise** có kiểm soát privacy mạnh: **loại trừ file khỏi phân tích của Copilot**, **audit log chi tiết**, và **IP indemnity** |
| **Policy management** | Business và Enterprise cho **quản lý policy toàn diện ở mức tổ chức** → dữ liệu nhạy cảm được xử lý theo chính sách công ty |
| **Data collection and retention** | Hiểu **dữ liệu được thu thập và lưu giữ ra sao** là thiết yếu để tuân thủ quy định. **Individual subscriber tự chọn** GitHub có thu thập và lưu prompt cùng gợi ý của mình hay không |
| **IP indemnity and data privacy** | Với doanh nghiệp, đây là yếu tố **then chốt để tránh vấn đề pháp lý, bảo mật và khách hàng** |

## 2. Bảo vệ hợp đồng & lọc public code

![[public-code-filter-settings.png]]

*Ảnh: Microsoft Learn — cài đặt liên quan tới bảo vệ hợp đồng và chặn gợi ý trùng public code.*
Ảnh này gắn với ràng buộc quan trọng nhất của cả note: cài đặt **Suggestions matching public code** không chỉ là một tuỳ chọn kỹ thuật — nó là **điều kiện pháp lý** để IP indemnity có hiệu lực. Đặt sai (Allow) thì GitHub **không nhận trách nhiệm pháp lý** dù bạn đang trả tiền gói Business/Enterprise.

### 2.1. Ba bảo vệ hợp đồng

| Bảo vệ | Nội dung |
|---|---|
| **IP indemnity** | Có ở gói **Business và Enterprise**: **bảo vệ pháp lý trước các khiếu nại về sở hữu trí tuệ** liên quan tới việc dùng gợi ý của Copilot. Nếu một gợi ý bị khiếu nại xâm phạm quyền IP của bên thứ ba, **GitHub nhận trách nhiệm pháp lý**. ⚠️ **Để GitHub nhận trách nhiệm, cài đặt "Matching public code" PHẢI được đặt là BLOCKED** |
| **Data Protection Agreement (DPA)** | Văn bản nêu **các biện pháp bảo vệ dữ liệu** và tuân thủ quy định về quyền riêng tư → minh bạch và bảo đảm dữ liệu được xử lý an toàn, có trách nhiệm |
| **GitHub Copilot Trust Center** | Cung cấp thông tin chi tiết về **cách Copilot hoạt động**: bảo mật, quyền riêng tư, tuân thủ và **các biện pháp bảo vệ sở hữu trí tuệ** |

### 2.2. Lọc gợi ý trùng public code

Copilot **giảm thiểu chồng lấn code** bằng cách **nhận diện và lọc bỏ gợi ý trùng với code công khai**. Điều này giữ **tính nguyên bản và bảo mật** của codebase, **giảm rủi ro đưa code không an toàn hoặc không tuân thủ** vào dự án.

**Ba scope quản lý — bảng phân biệt:**

| Scope | **Ai quản** | **Kiểm soát gì** | Ghi chú |
|---|---|---|---|
| **Organization** (gói Business/Enterprise) | **Admin** | Public code filter **cho toàn bộ thành viên**; **bắt buộc để có IP indemnity** | Org admin **chặn gợi ý trùng public code cho mọi member**. Đây là điều kiện **kích hoạt IP Indemnity** |
| **Personal account** (Free, Pro, Pro+) — **tự trả tiền** | **Người dùng cá nhân** | Toggle **Allow / Block** gợi ý trùng public code | Người **tự mua license** kiểm soát hoàn toàn cài đặt này tại **Copilot → Features → Privacy** |
| **Personal account** (Free, Pro, Pro+) — **org cấp seat** | Người dùng cá nhân | Toggle **Allow / Block** | ⚠️ Nếu seat **do tổ chức gán**, **toggle có thể bị KHOÁ** và **phản ánh chính sách của tổ chức** |

### 2.3. Đường đi cấu hình

| Ai | Các bước |
|---|---|
| **Org/Enterprise admin** | Góc trên phải GitHub → ảnh đại diện → **Your enterprises** hoặc **Your organizations** → **Settings** cạnh tổ chức → sidebar trái **Copilot** (dưới *Code, planning, and automation*) → **Features** → cuộn tới mục **Privacy** → **Suggestions matching public code** → chọn (ví dụ **Block**) → **Save** |
| **Người dùng cá nhân tự trả** | Ảnh đại diện → **Settings** → sidebar trái **Copilot** (dưới *Code, planning, and automation*) → **Features** → mục **Privacy** → **Suggestions matching public code** → toggle **Allow / Block** → có hiệu lực ngay với môi trường cá nhân |

## 3. Content exclusions

**Content exclusion** = tính năng **bảo vệ thông tin nhạy cảm bằng cách ngăn dùng các file, thư mục hoặc repository cụ thể để làm cơ sở cho gợi ý code-completion**.

### 3.1. Cấu hình

| Mức | Các bước |
|---|---|
| **Repository** | Trang chính của repo → dưới tên repo chọn **Settings** → sidebar mục **Code & automation** chọn **Copilot** → mục **Repositories and paths to exclude**, khai file/thư mục cần loại trừ |
| **Organization** | Ảnh đại diện → **Your organizations** → **Settings** cạnh tổ chức → sidebar trái **Copilot → Content exclusion** → nhập chi tiết file hoặc repository cần loại trừ |

> ⚠️ **Chỉ khai được content exclusion ở SETTINGS của organization hoặc repository.** Cài đặt định nghĩa trong org/repo thuộc một enterprise **áp lên toàn bộ member được cấp license Copilot Business hoặc Enterprise**.

### 3.2. Tác động — ba điều xảy ra

Khi bạn loại trừ nội dung khỏi Copilot:

1. **Code completion không còn khả dụng trong các file bị ảnh hưởng.**
2. **Nội dung file bị ảnh hưởng KHÔNG dùng để tạo gợi ý code completion ở file khác.**
3. **Nội dung file bị ảnh hưởng KHÔNG dùng cho phản hồi của Copilot Chat.**

**Đánh đổi:** loại trừ file làm code **an toàn và tuân thủ hơn**, nhưng **giảm ngữ cảnh khả dụng** cho Copilot → có thể **ảnh hưởng độ chính xác và hữu ích của gợi ý**.

> **Ví dụ gốc:** loại trừ một **file cấu hình quan trọng** có thể khiến Copilot **không gợi ý được các snippet phụ thuộc vào cấu hình định nghĩa trong file đó**. Phải cân nhắc kỹ để **cân bằng bảo mật và chức năng**.

### 3.3. Ba giới hạn của content exclusions — điểm thi

| Giới hạn | Nội dung |
|---|---|
| **IDE limitations** | Ở một số IDE, **content exclusion không áp dụng khi dùng một số tính năng như Copilot Chat**. Cụ thể: trong **Visual Studio Code và Visual Studio**, **content exclusion KHÔNG được áp khi bạn dùng chat participant `@github`** trong câu hỏi |
| **Semantic information** | Copilot **vẫn có thể dùng thông tin ngữ nghĩa từ file bị loại trừ** nếu **IDE cung cấp thông tin đó trong một file KHÔNG bị loại trừ** — bao gồm **type information** và **định nghĩa hiện khi hover** cho symbol hoặc lời gọi hàm |
| **Policy scope** | Content exclusion **chỉ áp cho member của tổ chức nơi bạn cấu hình**. **Bất kỳ ai khác có quyền truy cập các file đó vẫn thấy gợi ý code completion và phản hồi Chat tham chiếu tới chúng** |

```
★ Insight ─────────────────────────────────────
• Ba giới hạn này khiến content exclusion trở thành BIỆN PHÁP GIẢM THIỂU chứ
  không phải RÀO CHẮN. Nếu câu hỏi tình huống là "có nên dựa vào content
  exclusion để bảo vệ secret không?" thì đáp án đúng luôn là KHÔNG — secret
  phải nằm ngoài repo (Key Vault, secret manager), exclusion chỉ là lớp phụ.
• Ghép với note 11 để thấy lỗ hổng lớn nhất: Cloud Agent KHÔNG tôn trọng
  content exclusions. Tức ngoài 3 giới hạn ở đây còn một trường hợp thứ tư —
  agent thấy và sửa được cả file đã bị loại trừ.
• Con số 30 phút (mục 4) là hệ quả của việc IDE cache cài đặt — nên câu hỏi
  "vừa thêm exclusion mà vẫn có gợi ý" có đáp án là CHỜ hoặc RELOAD, không
  phải "cấu hình sai".
─────────────────────────────────────────────────
```

## 4. Xử lý sự cố thường gặp

### 4.1. Không có gợi ý code

| Hành động | Nội dung |
|---|---|
| **Kiểm tra kết nối internet** | Copilot **cần kết nối hoạt động** mới chạy được |
| **Cập nhật extension Copilot** | Bản cũ có thể **không giao tiếp hiệu quả với server Copilot** |
| **Xác nhận IDE tương thích** | Một số IDE cần **cấu hình hoặc cập nhật riêng** |
| **Rà lại content exclusions** | File bị loại trừ thì **không có gợi ý** — kiểm tra cài đặt exclusion |

### 4.2. Content exclusions không hoạt động như mong đợi

| Vấn đề | Cách xử lý |
|---|---|
| **Áp dụng bị trễ** | Sau khi thêm/sửa content exclusion, thay đổi có thể mất **TỚI 30 PHÚT** mới có hiệu lực ở các IDE đã nạp cài đặt sẵn. Muốn áp ngay → **reload cài đặt content exclusion trong IDE** |
| **Phạm vi loại trừ không đủ** | Cài đặt **chỉ áp cho member của tổ chức đã cấu hình** — bảo đảm mọi thành viên liên quan đã được áp đúng. **Kiểm tra icon Copilot trên status bar**: nếu **có gạch chéo** thì file đang bị content exclusion; **rê chuột lên icon** để xem **tổ chức hay repository cha** đã tắt Copilot cho file đó |
| **Giới hạn theo IDE** | Ở một số IDE, exclusion **không áp khi dùng một số tính năng như Copilot Chat** — biết để điều chỉnh workflow |

### 4.3. Gợi ý không đạt yêu cầu

| Kỹ thuật | Nội dung |
|---|---|
| **Provide clear context** | Code phải cấp ngữ cảnh rõ: **comment mô tả** và **tên biến có nghĩa** |
| **Use Copilot commands** | Một số IDE có lệnh riêng để yêu cầu gợi ý — ví dụ **VS Code dùng `Ctrl+Enter`** để kích hoạt Copilot |
| **Adjust prompt length** | Đôi khi prompt **dài hơn hoặc chi tiết hơn** cho kết quả tốt hơn — **thử nghiệm với độ dài khác nhau** |

## Q&A phỏng vấn

**Q1. Tính năng nào trong bảng management policy có ở MỌI gói kể cả Free?**
→ **Public code filter**. Tất cả các mục còn lại (user management, data excluded from training by default, enterprise-grade security, IP indemnity, content exclusions, SAML SSO, usage metrics) **chỉ từ Business**; **Require GitHub Enterprise Cloud** chỉ Enterprise.

**Q2. Hai tính năng customization chỉ có ở Enterprise?**
→ **Tailor chat conversations to your private codebase** và **Attach knowledge bases to chat for organizational context**.

**Q3. Điều kiện để IP indemnity có hiệu lực là gì?**
→ Phải ở gói **Business hoặc Enterprise** **VÀ** cài đặt **"Matching public code" phải được đặt BLOCKED**. Chỉ khi đó GitHub mới nhận trách nhiệm pháp lý.

**Q4. Ba bảo vệ hợp đồng GitHub cung cấp?**
→ **IP indemnity** · **Data Protection Agreement (DPA)** · **GitHub Copilot Trust Center**.

**Q5. Ba scope quản lý public code filter?**
→ **Organization** (admin quản, áp cho mọi member, bắt buộc cho IP indemnity) · **personal account tự trả tiền** (user toàn quyền toggle Allow/Block tại Copilot → Features → Privacy) · **personal account do org cấp seat** (toggle **có thể bị khoá**, phản ánh chính sách tổ chức).

**Q6. Content exclusions gây ra ba tác động nào?**
→ Code completion **không còn** trong file bị ảnh hưởng · nội dung file đó **không dùng để gợi ý ở file khác** · nội dung file đó **không dùng cho phản hồi Copilot Chat**.

**Q7. Ba giới hạn của content exclusions?**
→ **IDE limitations** (VS Code/Visual Studio: không áp khi dùng chat participant **`@github`**) · **semantic information** (type info, hover definition vẫn lọt qua file không bị loại trừ) · **policy scope** (chỉ áp cho member của tổ chức đã cấu hình).

**Q8. Vừa thêm content exclusion mà file vẫn có gợi ý. Vì sao và làm gì?**
→ Thay đổi mất **tới 30 phút** mới có hiệu lực ở IDE đã nạp cài đặt sẵn. **Reload cài đặt content exclusion trong IDE** để áp ngay.

**Q9. Làm sao biết một file đang bị content exclusion?**
→ **Icon Copilot trên status bar có gạch chéo**; **rê chuột lên icon** để xem **tổ chức hay repository cha** đã tắt Copilot cho file đó.

**Q10. Content exclusion khai được ở đâu?**
→ **Chỉ ở settings của organization hoặc repository** — không khai ở mức cá nhân.

## Tự kiểm tra

1. Vẽ lại bảng management policy 9 dòng theo 3 cột gói.
2. Bốn yếu tố cân nhắc khi chọn gói? *(data privacy & security · policy management · data collection & retention · IP indemnity & data privacy)*
3. Đường đi cấu hình public code filter cho org admin? *(Your organizations → Settings → Copilot → Features → Privacy → Suggestions matching public code → Block → Save)*
4. Đường đi cấu hình content exclusion cho repo? *(Settings → Code & automation → Copilot → Repositories and paths to exclude)*
5. Bốn hành động khi không có gợi ý code?
6. Phím tắt kích hoạt Copilot trong VS Code khi gợi ý không đạt? *(`Ctrl+Enter`)*

## Liên quan
- [[00-MOC-GH300|⬅ MOC GH-300]]
- Trước: [[13-Code-Review-va-Pull-Request]] · Kế tiếp: [[15-Developer-Use-Cases-va-Do-luong]]
- [[02-Copilot-la-gi-va-cac-goi]] — mô tả 5 gói ở mức tính năng; note này là bảng chính xác theo policy
- [[05-Copilot-xu-ly-Prompt-va-Du-lieu]] — ngưỡng ~150 ký tự của bộ lọc public code, và dữ liệu giữ 28 ngày
- [[11-Copilot-Cloud-Agent]] — ⚠️ Cloud Agent **không** tôn trọng content exclusions lẫn public code filter
- [[01-Responsible-AI-voi-Copilot]] — nguyên tắc Privacy & security đằng sau các cơ chế này
