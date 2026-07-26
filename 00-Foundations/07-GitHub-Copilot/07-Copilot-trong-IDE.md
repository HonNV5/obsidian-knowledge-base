---
title: "Copilot trong IDE — code completion, chat, scope reference, slash command"
section: 00-Foundations/07-GitHub-Copilot
tags: [github-copilot, gh-300, ide, vscode, chat, slash-commands, agents, pru, foundations]
related:
  - "[[00-MOC-GH300]]"
  - "[[03-Cai-dat-Cau-hinh-va-Cach-tuong-tac]]"
  - "[[08-Copilot-tren-GitHub-com]]"
difficulty: ⭐⭐⭐
estimated_time: 50m
source: [Microsoft Learn — GitHub Copilot Across Environments / Code completion · Copilot Chat]
---

# Note 07 — Copilot trong IDE

> **TL;DR:** Trong IDE, Copilot có **hai mặt**: **code completion** (gợi ý khi gõ + **multiple suggestions pane**, duyệt bằng `Alt+]` / `Alt+[`) và **Copilot Chat** (hội thoại). Copilot **thích nghi với phong cách code của bạn** theo 5 mặt: method implementation · naming conventions · formatting · comment style · design patterns; và **đọc 5 loại comment** (inline, block, docstring, TODO, API documentation) qua **NLP + contextual analysis**. Ba đòn bẩy nâng chất lượng câu trả lời của Chat: **scope referencing** (`#file:controller.js`, `@terminal`), **slash commands** (`/doc /explain /fix /generate /optimize /tests /new`), và **agents** (`@terminal`, `@vscode`). Về chi phí: **standard model (GPT-4o) = 1 PRU/request**, **premium model (o1-preview, o1-mini) = 2 PRU/request**. Gói Free có **2.000 code autocomplete + 50 chat message mỗi tháng**.

## 1. Code completion trong IDE

### 1.1. Ngôn ngữ được hỗ trợ mạnh

Copilot hỗ trợ rộng, nhưng **8 ngôn ngữ có năng lực mạnh nhất** (*strong capabilities*):

| | | | |
|---|---|---|---|
| **Python** | **JavaScript** | **Java** | **TypeScript** |
| **Ruby** | **Go** | **C#** | **C++** |

> **Tip gốc — con số phải nhớ:** gói **Free** có **2.000 code autocompletes** và **50 chat messages mỗi tháng**. **Educators, students và một số open-source maintainer** được **Copilot Pro miễn phí** (`aka.ms/Copilot4Students`).

### 1.2. Auto suggestions

Copilot gợi ý **khi bạn gõ**: đôi khi **hoàn thành dòng hiện tại**, đôi khi **đề xuất cả một khối code mới**. Bạn có thể **nhận toàn bộ, nhận một phần, hoặc bỏ qua**. Giá trị: gợi ý **thời gian thực, nhận biết ngữ cảnh** → bớt phải tra cú pháp, gỡ logic, hay viết đi viết lại các pattern quen thuộc.

### 1.3. Multiple suggestions pane

Khi Copilot đưa gợi ý, bạn thấy **snippet code màu xám**. **Rê chuột lên gợi ý** để hiện **GitHub Copilot control panel** → **đánh giá nhiều cách tiếp cận cho cùng một bài toán**.

| Thao tác | macOS | Windows / Linux |
|---|---|---|
| Gợi ý **kế tiếp** | `Option (⌥)` hoặc `Alt+]` | `Alt+]` |
| Gợi ý **trước đó** | `Option (⌥)` hoặc `Alt+[` | `Alt+[` |

Hoặc bấm **nút mũi tên tới/lui** trên control panel.

Giá trị thật: **giữ đà code** — so sánh nhiều hiện thực **trong vài giây** thay vì làm lại từ đầu hay đi tra ví dụ trên mạng.

### 1.4. Copilot thích nghi phong cách code của bạn — 5 mặt

| Mặt thích nghi | Copilot làm gì |
|---|---|
| **Method Implementation** | Bạn vừa gõ tên method, nó **gợi ý cả phần hiện thực** theo phong cách code bạn đã thiết lập |
| **Naming Conventions** | Bắt được **quy ước đặt tên** biến, hàm, lớp mà bạn ưa dùng |
| **Formatting** | Theo **kiểu thụt lề, cách đặt ngoặc** và các sở thích định dạng khác |
| **Comment Style** | **Bắt chước kiểu comment** của bạn: inline, block, hay docstring |
| **Design Patterns** | Dự án dùng nhất quán mẫu thiết kế nào thì nó gợi ý code **theo đúng mẫu đó** |

### 1.5. Copilot đọc comment thế nào

**Hai quy trình hiểu comment:**

| Quy trình | Nội dung |
|---|---|
| **Natural Language Processing** | Dùng kỹ thuật NLP nâng cao để **diễn giải nghĩa và ý định** đằng sau comment |
| **Contextual Analysis** | Phân tích comment **trong quan hệ với code xung quanh**, hiểu mức liên quan và mục đích của nó trong ngữ cảnh rộng của file/dự án |

**Năm loại comment Copilot dùng được:**

| Loại | Mô tả |
|---|---|
| **Inline comments** | Giải thích ngắn **cạnh dòng code cụ thể** |
| **Block comments** | Giải thích dài, thường **mô tả một hàm hoặc lớp** |
| **Docstrings** | **Chuỗi tài liệu chính thức** trong ngôn ngữ như Python |
| **TODO comments** | Ghi chú về **hiện thực/cải tiến trong tương lai** |
| **API Documentation** | Comment mô tả **cách dùng và tham số** của hàm/method |

**Bốn kiểu sinh code từ comment:**

| Kiểu | Nội dung | Ví dụ giáo trình |
|---|---|---|
| **Function implementation** | Comment mô tả một hàm → Copilot đề xuất **toàn bộ phần hiện thực** | — |
| **Code completion** | Comment giúp completion **chính xác hơn** vì hiểu ý định dev | Comment "hàm đảo ngược chuỗi" → Copilot đề xuất **slice notation với step `-1`** của Python |
| **Variable naming** | Comment ảnh hưởng **tên biến** được đề xuất, khiến chúng mô tả rõ và hợp ngữ cảnh | Comment về "danh sách sách yêu thích của user" → gợi ý tên biến **`favorite_books`** |
| **Algorithm selection** | Comment mô tả **thuật toán/cách tiếp cận cụ thể** → Copilot đề xuất code **theo đúng phương pháp đó** | Comment vạch các bước **bubble sort** → sinh hiện thực bám sát các bước đã mô tả |

```
★ Insight ─────────────────────────────────────
• "Copilot thích nghi 5 mặt" và "5 loại comment" là hai danh sách 5 mục KHÁC
  NHAU nhưng dễ trộn lẫn khi ôn. Mẹo phân biệt: 5 mặt thích nghi nói về CÁCH
  VIẾT CODE (implementation, naming, formatting, comment style, design pattern);
  5 loại comment nói về DẠNG COMMENT (inline, block, docstring, TODO, API doc).
  Lưu ý "comment style" nằm ở danh sách thứ nhất, không phải thứ hai.
• Ví dụ "reverse string → slice notation step -1" và "favorite_books" là hai
  chi tiết cụ thể được nêu đích danh trong nguồn — dạng chi tiết hay xuất hiện
  trong câu hỏi tình huống.
─────────────────────────────────────────────────
```

## 2. GitHub Copilot Chat

Truy cập: **bấm icon chat trên thanh điều hướng bên trái** của IDE.

### 2.1. Ba tình huống Chat toả sáng

| Tình huống | Nội dung | Ví dụ gốc |
|---|---|---|
| **Complex code generation** | Hiện thực **thuật toán phức tạp, cấu trúc dữ liệu**, hoặc sinh boilerplate cho **design pattern cụ thể**: **regex phức tạp**, **truy vấn SQL chi tiết**, cấu trúc dữ liệu nâng cao (ví dụ **Bubble sort trong Python**) | — |
| **Debugging assistance** | Phân tích **thông báo lỗi** và đề xuất cách sửa; nhận diện **lỗi logic**, giải thích **từng bước** các đoạn có vấn đề. Cách làm: **bôi đen đoạn code lỗi → chuột phải → Copilot → inline-chat** | *"I'm getting a NullReferenceException in this method. Can you help me debug it?"* |
| **Code explanations** | Bẻ code thành ngôn ngữ đơn giản, giải thích mục đích và chức năng của đoạn code lạ, đưa insight về best practice và tối ưu | *"Can you explain how this async/await code works in Python?"* |

### 2.2. Scope referencing — trỏ đúng phạm vi

Muốn câu trả lời chính xác thì phải **đóng khung câu hỏi bằng tham chiếu**:

| Loại tham chiếu | Cú pháp | Tác dụng |
|---|---|---|
| **File references** | `#file:` + tên file, ví dụ **`#file:controller.js`** | Bảo Chat **tập trung vào nội dung file đó** khi sinh câu trả lời |
| **Environment references** | **`@terminal`** | Dùng Chat **cùng với terminal**: Copilot **đọc output terminal** để gỡ rối và đề xuất. Ví dụ: *"@terminal how do I fix this error?"* |

![[chat-file-reference.png]]

*Ảnh: Microsoft Learn — dùng `#file` để chọn và tham chiếu trực tiếp một file trong câu hỏi.*
Gõ `#file` trong ô chat, VS Code hiện danh sách file để chọn; sau khi chọn, tham chiếu xuất hiện trong prompt dưới dạng `#file:controller.js` và Copilot chỉ đọc nội dung file đó thay vì đoán từ toàn workspace.

### 2.3. Slash commands trong Chat

| Lệnh | Tác dụng | Ví dụ gốc |
|---|---|---|
| **`/doc`** | **Thêm comment** cho code được chỉ định/bôi đen | gõ `/doc` kèm code cần tài liệu hoá |
| **`/explain`** | **Giải thích** code đã chọn | `/explain the #file:controller.js` |
| **`/fix`** | **Đề xuất cách sửa** vấn đề trong code đã chọn | bôi đen đoạn lỗi rồi `/fix` |
| **`/generate`** | **Sinh code mới** theo yêu cầu | `/generate code to find the root of a number in client.js` |
| **`/optimize`** | Phân tích và **đề xuất cải thiện thời gian chạy / hiệu quả** | `/optimize the calculate method in controller.js` |
| **`/tests`** | **Tự tạo unit test** cho code đã chọn | bôi đen code rồi `/tests using Mocha` |
| **`/new`** | **Smart action sinh nguyên một project mới** từ yêu cầu | `/new generate a new HTML file with pages and JavaScript for advanced calculations` → bấm **Create Workspace** |

> Slash command **làm rõ ý định truy vấn**, khiến yêu cầu tập trung hơn → chất lượng câu trả lời tăng đáng kể.

### 2.4. Copilot agents trong Chat

**Copilot agents** = **công cụ tuỳ biến bạn xây và tích hợp** với Copilot Chat để bổ sung chức năng riêng. Hai agent dựng sẵn được nêu:

| Agent | Dùng cho | Ví dụ |
|---|---|---|
| **`@terminal`** | Câu hỏi liên quan **dòng lệnh** | Tìm file lớn nhất trong thư mục · giải thích lệnh vừa chạy |
| **`@vscode`** | Câu hỏi về **Visual Studio Code** | Cách debug · cách đổi setting trong IDE |

![[chat-agent-terminal.png]]

*Ảnh: Microsoft Learn — agent `@terminal` trả lời câu hỏi về dòng lệnh ngay trong Copilot Chat.*
Điểm đáng chú ý: agent đứng ở **đầu prompt** (`@terminal ...`) và quyết định **nguồn ngữ cảnh** Copilot sẽ dùng — ở đây là nội dung terminal, chứ không phải file đang mở. Đây là khác biệt so với `#file:` (chọn *tài nguyên*) và `/command` (chọn *hành động*).

### 2.5. Model selection & premium features — chi phí PRU

Copilot Chat có nhiều mô hình AI; một số môi trường cho bạn **chọn mức năng lực**:

| Nhóm mô hình | Ví dụ | Chi phí | Phù hợp | Ví dụ tác vụ |
|---|---|---|---|---|
| **Standard models** | **GPT-4o** | **1 PRU / request** | Phản hồi **nhanh, tin cậy** cho hầu hết tác vụ; hỗ trợ code thường ngày, giải thích code, debug cơ bản | Sinh hàm đơn giản · hỏi cú pháp · gợi ý refactor cơ bản |
| **Premium models** | **o1-preview, o1-mini** | **2 PRU / request** (gấp đôi) | **Suy luận nâng cao** cho bài toán phức tạp; phân tích tinh vi, thuật toán phức tạp, quyết định kiến trúc | Debug code đa luồng · thiết kế thuật toán phức tạp · phân tích bảo mật |

> Khi gặp bài toán khó cần suy luận sâu, premium model cho phân tích thấu đáo hơn — **nhưng phải cân nhắc mức tiêu PRU** khi chọn model cho từng loại tác vụ.

### 2.6. Gửi feedback

Hầu hết IDE tích hợp Chat đều có cơ chế feedback sẵn. Trong **VS Code**: rê chuột lên **đầu phần gợi ý của Copilot Chat** → hiện nút **thumbs up** (hữu ích) và **thumbs down** (không hữu ích).

```
★ Insight ─────────────────────────────────────
• Ba ký hiệu của Copilot Chat có vai trò khác nhau, đề thi rất hay hoán đổi:
    #  → chọn TÀI NGUYÊN   (#file:controller.js — nhìn vào cái gì)
    @  → chọn AGENT/MÔI TRƯỜNG (@terminal, @vscode — hỏi ai)
    /  → chọn HÀNH ĐỘNG    (/explain, /fix, /tests — làm gì)
  Một prompt tốt có thể dùng cả ba: "/explain the #file:controller.js".
• Bảng PRU 1 vs 2 là chi tiết định lượng duy nhất về model selection trong cả
  giáo trình: GPT-4o = 1 PRU (standard), o1-preview/o1-mini = 2 PRU (premium).
  Ghép với note 04 (lịch sử chat đầy đủ 2–3 PRU/lượt) để thấy chi phí cộng dồn.
─────────────────────────────────────────────────
```

## Q&A phỏng vấn

**Q1. Tám ngôn ngữ Copilot hỗ trợ mạnh nhất?**
→ Python · JavaScript · Java · TypeScript · Ruby · Go · C# · C++.

**Q2. Gói Free cho bao nhiêu autocomplete và chat message mỗi tháng?**
→ **2.000 code autocompletes** và **50 chat messages**/tháng. Educators, students và một số open-source maintainer được **Copilot Pro miễn phí**.

**Q3. Duyệt qua nhiều gợi ý bằng phím nào?**
→ `Alt+]` (kế tiếp) / `Alt+[` (trước đó); trên macOS còn dùng được `Option (⌥)`. Hoặc rê chuột lên gợi ý để hiện **control panel** và bấm mũi tên.

**Q4. Copilot thích nghi phong cách code theo 5 mặt nào?**
→ Method implementation · naming conventions · formatting · comment style · design patterns.

**Q5. Copilot hiểu comment qua hai quy trình nào?**
→ **Natural Language Processing** (diễn giải nghĩa/ý định) và **Contextual Analysis** (đặt comment trong quan hệ với code xung quanh).

**Q6. Phân biệt `#`, `@`, `/` trong Copilot Chat.**
→ `#` tham chiếu **tài nguyên** (`#file:controller.js`) · `@` gọi **agent/môi trường** (`@terminal`, `@vscode`) · `/` ra **hành động** (`/explain`, `/fix`, `/tests`).

**Q7. `/optimize` khác `/fix` thế nào?**
→ `/fix` **đề xuất cách sửa vấn đề** trong code đã chọn; `/optimize` **phân tích và cải thiện thời gian chạy / hiệu quả** của code (code vẫn đang chạy đúng).

**Q8. Bạn cần debug một đoạn code đa luồng phức tạp. Nên chọn model nào, tốn bao nhiêu PRU?**
→ **Premium model** (o1-preview / o1-mini) vì cần suy luận nâng cao — **2 PRU/request**, gấp đôi standard model GPT-4o (1 PRU).

**Q9. Muốn sinh nguyên một project mới từ mô tả, dùng gì?**
→ Smart action **`/new`**, ví dụ `/new generate a new HTML file with pages and JavaScript for advanced calculations`, rồi bấm **Create Workspace**.

## Tự kiểm tra

1. Multiple suggestions pane hiện ra bằng cách nào? *(rê chuột lên gợi ý xám → GitHub Copilot control panel)*
2. Năm loại comment Copilot dùng được? *(inline · block · docstring · TODO · API documentation)*
3. Bốn kiểu sinh code từ comment? *(function implementation · code completion · variable naming · algorithm selection)*
4. Bảy slash command trong Chat và tác dụng từng cái?
5. Hai agent dựng sẵn và việc của chúng? *(@terminal — dòng lệnh; @vscode — câu hỏi về VS Code)*
6. Cách gỡ lỗi nhanh bằng inline-chat theo giáo trình? *(bôi đen đoạn lỗi → chuột phải → Copilot → inline-chat)*
7. PRU của GPT-4o và o1-mini? *(1 và 2)*

## Liên quan
- [[00-MOC-GH300|⬅ MOC GH-300]]
- Trước: [[06-Copilot-Spaces]] · Kế tiếp: [[08-Copilot-tren-GitHub-com]]
- [[03-Cai-dat-Cau-hinh-va-Cach-tuong-tac]] — phím tắt và cách bật/tắt
- [[04-Prompt-Engineering-voi-Copilot]] — "Surround": mở file liên quan chính là bổ trợ cho scope referencing
- [[16-Unit-Testing-voi-Copilot]] — `/tests` ở mức nâng cao cùng `/setupTests`, `/fixTestFailure`
- [[10-Agent-Mode-trong-IDE]] — agent mode: bước tiến so với chat thường
