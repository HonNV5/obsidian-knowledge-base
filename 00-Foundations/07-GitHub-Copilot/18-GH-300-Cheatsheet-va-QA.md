---
title: "⭐ GH-300 Cheatsheet — bảng tra nhanh, cặp dễ nhầm, bản đồ đề thi, Q&A tổng hợp"
section: 00-Foundations/07-GitHub-Copilot
tags: [github-copilot, gh-300, cheatsheet, on-thi, tong-hop, foundations]
related:
  - "[[00-MOC-GH300]]"
difficulty: ⭐⭐⭐⭐⭐
estimated_time: 60m
source: [Tổng hợp 17 note trước — Microsoft Learn GitHub Copilot Fundamentals Part 1 & 2]
---

# Note 18 — GH-300 Cheatsheet + Q&A

> **TL;DR:** Note ôn cuối. Không dạy kiến thức mới — **gom mọi con số, định danh và bảng phân biệt** rải rác trong 17 note trước vào một chỗ tra được trong 15 phút trước giờ thi. Ba phần: **§1-§10 bảng tra nhanh** · **§11 bảng cặp dễ nhầm** (chỗ đề thi hay gài bẫy) · **§12 bản đồ 7 domain đề thi** (🔎 ngoài nguồn) + **§13 Q&A tổng hợp xuyên chủ đề**.

## 1. Năm gói Copilot

| Gói | Đối tượng | Điểm phân biệt cốt lõi |
|---|---|---|
| **Free** | Cá nhân, miễn phí | **2.000 code autocomplete + 50 chat message / tháng** |
| **Pro** | Cá nhân | Hạn mức cao hơn · **ưu tiên mô hình mới nhất** · sinh test tự động |
| **Pro+** | Cá nhân dùng nặng | Toàn bộ Pro + **thêm hạn mức premium request** + **priority infrastructure access** |
| **Business** | Tổ chức | ⭐ **Ranh giới quản trị**: policy control tập trung · **public code filter** · **IP indemnity** · **content exclusions** · SAML SSO · usage metrics |
| **Enterprise** | Doanh nghiệp lớn | ⭐ **Ranh giới cá nhân hoá**: gợi ý theo **codebase riêng** · **attach knowledge bases** · **fine-tune model cho tổ chức** · **cần GitHub Enterprise Cloud** |

**Hai mốc phải thuộc:**
- **Pro+ → Business** = từ *cá nhân* sang *tổ chức* (xuất hiện quản trị + pháp chế).
- **Business → Enterprise** = từ *quản trị* sang *cá nhân hoá theo code nội bộ*.

**Tính năng có ở MỌI gói (dễ bị nhầm là chỉ Business+):** **public code filter** · **Copilot Extensions** · **data excluded from training** *(mặc định — nhưng dòng "by default" trong bảng management policy chỉ từ Business)*.

## 2. Slash command theo surface

| Surface | Lệnh |
|---|---|
| **IDE / Copilot Chat** | `/doc` · `/explain` · `/fix` · `/generate` · `/help` · `/optimize` · `/tests` · `/new` |
| **Testing (C# Dev Kit)** | `/setupTests` · `/tests` · `/plan` · `/fixTestFailure` |
| **Copilot CLI** (13 lệnh) | `/help` · `/explain <command>` · `/suggest <task>` · `/revise` · `/feedback` · `/exit` · `/model <model>` · `/theme` · `/skills` · `/mcp` · `/list-dirs` · `/reset-allowed-tools` · `/sandbox enable` |
| **GitHub Copilot app** | `/chronicle` |

> ⚠ **Slash command trong CLI KHÔNG thay được bằng ngôn ngữ tự nhiên** — phải gõ đúng lệnh.

## 3. Ký hiệu tham chiếu ngữ cảnh trong Chat

| Ký hiệu | Nghĩa | Ví dụ |
|---|---|---|
| **`#`** | **Tài nguyên** (resource) — chỉ Copilot nhìn vào cái gì | `#file:controller.js` · `#selection` · `#codebase` · `#editor` |
| **`@`** | **Agent / môi trường** — chỉ Copilot đứng ở đâu | `@terminal` · `@vscode` · `@github` · `@copilot` |
| **`/`** | **Hành động** — chỉ Copilot làm gì | `/fix` · `/tests` · `/doc` |

**Mẹo nhớ:** `#` = *cái gì* · `@` = *ở đâu* · `/` = *làm gì*.

## 4. Bảng PRU tổng hợp (Premium Request Unit)

| Tác vụ | PRU | Note nguồn |
|---|---|---|
| **Standard model (GPT-4o)** | **1 / request** | 07 |
| **Premium model (o1-preview, o1-mini)** | **2 / request** | 07 |
| **Chat kèm toàn bộ lịch sử hội thoại** | **2–3 / lượt** | 04 |
| **Chat có tóm tắt ngữ cảnh / reset** | **~1 / request** | 04 |
| **PR summary** | **1–2** | 08 |
| **Code review** | **1–3** | 08, 13 |
| **Agent handoff (mỗi lần bàn giao)** | **~1** | 10 |
| **Chuỗi draft–review 2 bước** | **2–3** | 10 |
| **Premium reasoning** | **~4+** (so với ~2 model chuẩn) | 10 |
| **Boilerplate đơn giản** | **1–2** | 15 |
| **Project scaffolding** | **3–5** | 15 |
| **Cloud Agent** | **1 premium request cho MỖI model request** (từ **04/06/2025**) | 11 |

**Bốn cách tối ưu PRU:** *Plan ahead* (cảnh báo ở **75% · 90% · 100%**) · *Use PRUs strategically* · *Refine your prompts* · *Scale up if needed*.

**Quy tắc nhớ ngưỡng:** **check nhẹ một dòng = không tốn PRU**; **quét cả diff / agentic = tốn PRU**.

## 5. Con số phải thuộc

| Con số | Ý nghĩa | Note |
|---|---|---|
| **46% / 55% / 74%** | 46% code mới do AI viết · 55% nhanh hơn · **74% cảm thấy tập trung hơn** | 02 |
| **~150 characters** | Ngưỡng **public code match** — gợi ý dài hơn mà trùng public code thì có thể bị chặn | 05, 14 |
| **28 ngày** | **Copilot Chat ngoài editor** giữ prompt/response | 05 |
| **Không giữ** | **Code completion trong editor** — huỷ prompt ngay sau khi trả gợi ý | 05 |
| **~200-500 dòng / vài nghìn token** | Context window của code completion | 05 |
| **4k token** | Context window của **Copilot Chat** | 05 |
| **2.000 + 50** | Quota tháng gói **Free**: autocomplete + chat message | 07 |
| **< 30 giây** | Copilot review xong một PR | 13 |
| **tới 30 phút** | Content exclusion **có hiệu lực** sau khi đổi cấu hình | 14 |
| **3 ngày → 1 ngày** | PR lead time trước/sau khi bật review có PRU | 13 |
| **30%** | Mức giảm PRU khi dành review premium cho code production | 13 |
| **2 tuần / 4 tuần** | Khảo sát developer: **short-form mỗi 2 tuần**, **long-form không quá 1 lần / 4 tuần** | 15 |
| **1 giờ** | Timeout một phiên **Cloud Agent** | 11 |
| **3.00 MiB** | Giới hạn kích thước ảnh gửi cho Cloud Agent | 11 |
| **≤ 59 phút** | `timeout-minutes` tối đa trong `copilot-setup-steps.yml` | 11 |
| **> 30 tool** | Số tool của **GitHub MCP Server** | 12 |
| **.NET 8.0 SDK trở lên** | Yêu cầu môi trường unit testing | 16 |

## 6. Bốn surface của Copilot

| Surface | Hợp nhất cho | Vai trò then chốt |
|---|---|---|
| **GitHub Copilot app** | Quản lý **agent workflow đầu-cuối** | **Điều phối** issue → code → PR → merge |
| **Copilot trong VS Code (IDE)** | **Sửa và debug code** | Phát triển tay, sát code |
| **Copilot CLI** | Workflow **hướng terminal** | Tự động hoá, scripting, kiểm soát mức môi trường |
| **Copilot trên GitHub.com** | **Cộng tác và hoạch định** | Issue, tạo PR, phối hợp bất đồng bộ |

## 7. Ba bộ ba "mức tự trị" — cùng một trục, ba tên gọi

| Bối cảnh | Mức thấp (giám sát nhiều) | Mức giữa | Mức cao (tự trị) |
|---|---|---|---|
| **Copilot app — session mode** | **Interactive** | **Plan** | **Autopilot** |
| **Chat view — agent** | **Ask** (chỉ đọc, không sửa file) | **Plan** (kế hoạch review được) | **Agent** (sửa file + chạy lệnh + lặp) |
| **Permission level** | **Default Approvals** | — | **Bypass Approvals** → **Autopilot** |

**Bốn mức tương tác với Copilot** (thang tăng dần độ tự động, trục khác nhưng dễ lẫn):
**Inline Suggestions → Copilot Chat → Copilot Edits → Agent Mode**

## 8. Agent Mode (IDE) vs Cloud Agent

| Tiêu chí | **Agent Mode** (note 10) | **Cloud Agent** (note 11) |
|---|---|---|
| **Chạy ở đâu** | **Máy bạn**, trong IDE | **Hạ tầng GitHub** (sandbox GitHub Actions) |
| **Đồng bộ?** | **Đồng bộ** — bạn ngồi xem | **Bất đồng bộ** — chạy nền |
| **Kích hoạt** | Chọn Agent trong Chat view | **Gán issue cho Copilot** (UI hoặc GraphQL) |
| **Kết quả** | Sửa trực tiếp file trong workspace | **Branch `copilot/` + draft PR** |
| **Gói** | Theo gói Copilot của bạn | **Pro, Pro+, Business, Enterprise** |
| **Tài nguyên tốn** | PRU | **PRU + GitHub Actions minutes** |
| **Content exclusions** | ✅ Có áp | ⚠️ **KHÔNG tôn trọng** |
| **Public code filter** | ✅ Có áp | ⚠️ **KHÔNG tôn trọng** |
| **Đổi model** | ✅ Được | ❌ **Không** |
| **Số PR mỗi task** | — | **Đúng 1** |
| **Runner** | — | **Chỉ Ubuntu x64 GitHub-hosted** |

## 9. Public code filter vs Content exclusions

| | **Public code filter** (Matching public code) | **Content exclusions** |
|---|---|---|
| **Chặn cái gì** | **Gợi ý trùng public code** (~**150 ký tự** trở lên) | **File/thư mục cụ thể** khỏi ngữ cảnh Copilot |
| **Hướng** | **Đầu ra** — cái Copilot trả về | **Đầu vào** — cái Copilot được nhìn |
| **Gói** | **Mọi gói** | **Chỉ Business / Enterprise** |
| **Quản ở** | **3 scope** (cá nhân / tổ chức / enterprise) | Repo, org, enterprise |
| **Liên quan pháp lý** | ⚠️ **IP indemnity chỉ hiệu lực khi đặt BLOCKED** | Không |
| **Độ trễ** | Tức thì | **Tới 30 phút** |
| **Cloud Agent có tuân?** | ❌ Không | ❌ Không |

**Ba giới hạn của content exclusions:** (1) **IDE — không áp khi dùng `@github`** · (2) **semantic information vẫn lọt** · (3) **chỉ áp cho member của tổ chức đã cấu hình**.

## 10. Tuỳ biến bằng file instructions

| File | Phạm vi | Dùng được cho |
|---|---|---|
| **`.github/copilot-instructions.md`** | **Một file, cả repo** | Chat, code review |
| **`.github/instructions/*.instructions.md`** | **Theo đường dẫn** — frontmatter **`applyTo:`** dùng glob (`applyTo: tests/**`) | Chat, **code review**, **Cloud Agent** |
| **`.github/workflows/copilot-setup-steps.yml`** | Chuẩn bị môi trường cho **Cloud Agent** | Key cho phép: `steps` · `permissions` · `runs-on` · `container` · `services` · `snapshot` · `timeout-minutes` (**≤59**) |

## 11. Bảng cặp dễ nhầm ⚠️

| Cặp | Phân biệt |
|---|---|
| **`Tab`** vs **`Ctrl+Enter`** vs **`Ctrl+I`** | Nhận suggestion · **duyệt nhiều suggestion** · **mở inline chat** |
| **`Alt+]` / `Alt+[`** vs **`Ctrl+Enter`** | Duyệt trong **multiple suggestions pane** · **mở** pane nhiều gợi ý |
| **Implicit prompt** vs **Selective context** | Prompt **soạn sẵn** trong slash command (*ý định*) · chủ động chỉ định **Copilot nhìn đâu** (*dữ liệu*) |
| **`#editor`** vs **`#selection`** | **Toàn bộ file đang mở** · **chỉ phần đang bôi đen** |
| **Fine-tuning** vs **LoRA** | Huấn luyện lại **toàn bộ tham số** · thêm **phần khả huấn nhỏ vào từng lớp** (GitHub dùng LoRA — thắng adapters và prefix-tuning) |
| **Code completion** vs **Chat** (giữ dữ liệu) | **Không giữ prompt** (huỷ ngay) · **giữ 28 ngày** (khi dùng ngoài editor) |
| **Context window** | Completion **~200-500 dòng** · Chat **4k token** |
| **Toxicity filter** | Chạy **HAI lần** — bước 3 (inbound) và bước 5 (outbound) |
| **Proxy filter** | Đặt trong **Azure tenant do GitHub sở hữu**, không phải tenant của bạn |
| **Zero / one / few-shot** | Không ví dụ · **một** ví dụ · **nhiều** ví dụ |
| **Copilot review** | Luôn là **comment review** — **không approve/reject**, **không tính vào required approvals** → **không chặn merge** |
| **IP indemnity** | Business/Enterprise **VÀ** Matching public code phải = **Blocked** |
| **Agent Mode** vs **Cloud Agent** | Xem §8 — mấu chốt: **đồng bộ trong IDE** vs **bất đồng bộ trên GitHub** |
| **Copilot Edits** vs **Agent Mode** | Sửa nhiều file **theo chỉ dẫn của bạn** · **tự quyết** file nào, tự chạy lệnh, tự lặp |
| **Copilot Spaces** | Là **ngữ cảnh có tổ chức** (breadth vs depth), **không cấp quyền truy cập mới** |
| **`/doc`** vs **`/docs`** | Nguồn dùng cả hai; **bảng liệt kê chính thức là `/doc`** |
| **`/tests`** vs **`/setupTests`** | Sinh test cho code · **dựng framework test cho project** |
| **NUnit** trong 3 framework | Là framework **duy nhất không kèm `coverlet.collector`** |
| **MCP: 3 kiểu kết nối** | local↔local · **local làm cầu tới remote** · remote hoàn toàn qua internet |
| **GitHub MCP remote vs Docker** | Remote hỗ trợ **OAuth**; **Docker bắt buộc PAT, không OAuth** |
| **Cloud Agent MCP** | **Chỉ hỗ trợ tools** — không resources, không prompts, **không OAuth remote** |
| **Copilot trong SDLC** | **KHÔNG** thu thập requirement · **KHÔNG** trực tiếp tham gia deployment |
| **Codespaces** | Không commit + push trước khi xoá = **mất sạch việc** |

## 12. Bản đồ 7 domain đề thi GH-300

> 🔎 **Ngoài nguồn** — trọng số lấy từ mô tả kỳ thi GH-300 của GitHub, **không có trong 2 file giáo trình**. Dùng để phân bổ thời gian ôn.

| Domain | Trọng số | Note phủ | Nhắm vào |
|---|---|---|---|
| **GitHub Copilot plans and features** | **31%** | 02, 03, 07, 08, 09 | ⭐ Nặng nhất — **bảng 5 gói** + **tính năng nào có ở surface nào** |
| **How GitHub Copilot works and handles data** | **15%** | 05, 10, 11, 12 | **Pipeline 7 bước**, giữ dữ liệu, context window |
| **Privacy fundamentals and context exclusions** | **15%** | 14, 11 | **Public code filter vs content exclusions** + 3 giới hạn |
| **Developer use cases for AI** | **14%** | 15, 17 | SDLC, đo lường, REST metrics, lab theo ngôn ngữ |
| **Prompt crafting and prompt engineering** | **9%** | 04, 06 | **4 Ss**, zero/one/few-shot, chain prompting |
| **Testing with GitHub Copilot** | **9%** | 16 | `/setupTests` `/tests` `/fixTestFailure`, Ask/Plan/Agent |
| **Responsible AI** | **7%** | 01 | **6 nguyên tắc F-R-P-I-T-A** |

**Chiến lược ôn:** 31% + 15% + 15% = **61% đề nằm ở gói/tính năng + cách vận hành + privacy**. Ba domain nhỏ nhất (RAI 7%, prompt 9%, testing 9%) cộng lại chỉ **25%** nhưng **dễ ăn trọn điểm** vì nội dung ngắn và có cấu trúc rõ — ôn chúng trước để chốt điểm chắc.

## 13. Danh sách đếm được — kiểm tra trí nhớ

| Số | Danh sách |
|---|---|
| **6 nguyên tắc RAI** | Fairness · Reliability & safety · Privacy & security · Inclusiveness · Transparency · Accountability |
| **6 tính năng lớn của Copilot** | Copilot chat · PR summaries · code review assistance · Copilot for the CLI · Copilot Spaces · Copilot Cloud Agent |
| **5 gói** | Free · Pro · Pro+ · Business · Enterprise |
| **4 Ss** | Single · Specific · Short · Surround |
| **4 best practice prompt** | Provide enough clarity · provide enough context with details · provide examples for learning · assert and iterate |
| **7 bước pipeline** | Secure transmission + context gathering → proxy filter → toxicity filtering → LLM generation → post-processing & validation → delivery + feedback loop → repeat |
| **4 mức tương tác** | Inline Suggestions → Copilot Chat → Copilot Edits → Agent Mode |
| **4 bước vòng agent** | Xác định file & dependency → đề xuất + thực thi thay đổi → chạy lệnh terminal → giám sát & tinh chỉnh lặp |
| **3 kiểu kết nối MCP** | local↔local · local làm cầu tới remote · remote qua internet |
| **3 mức tự động code review** | Cá nhân (Pro/Pro+) · repo (ruleset) · tổ chức (ruleset theo pattern) |
| **3 framework test** | xUnit · NUnit · MSTest |
| **3 giai đoạn quy trình test** | Thiết lập môi trường → sinh test code → chạy & bảo trì |
| **5 giai đoạn SDLC** | Requirement analysis → Design & development → Testing & QA → Deployment → Maintenance & support *(mạnh nhất ở **Design & development**; **không trực tiếp** thu thập requirement, **không trực tiếp** tham gia deployment)* |
| **4 giai đoạn khung đo lường** | Evaluation → Adoption → Optimization → Sustained efficiency |
| **4 agent trong orchestrated workflow** | Draft agent · review agent · documentation agent · test agent |
| **4 nhóm giới hạn của Copilot** | Code quality & correctness · language/framework specificity · dependency on training data · complex problem solving |
| **3 giới hạn content exclusions** | IDE `@github` · semantic information · phạm vi policy theo tổ chức |
| **6 lớp bảo mật Cloud Agent** | Sandbox có firewall · quyền đọc repo · chỉ push `copilot/` · chỉ nghe user có write · người yêu cầu không tự duyệt · lọc ký tự ẩn |
| **3 kiểu ngữ cảnh chọn lọc** | Workspace · `@terminal` · mở/tham chiếu file |
| **8 ngôn ngữ Copilot hỗ trợ mạnh nhất** | Python · JavaScript · Java · TypeScript · Ruby · Go · C# · C++ |
| **4 nhóm use case tăng năng suất** | Học ngôn ngữ/framework mới · giảm context switching · viết tài liệu · automating the boring stuff |

## 14. Q&A tổng hợp xuyên chủ đề

**Q1. Mô tả pipeline 7 bước và nói rõ bước nào chạy hai lần.**
→ (1) Truyền an toàn HTTPS + gom ngữ cảnh (dùng **FIM** — Fill-In-the-Middle, lấy code **trước và sau** con trỏ) → (2) **Proxy filter** trong **Azure tenant do GitHub sở hữu** → (3) **Toxicity filtering** → (4) **LLM sinh code** → (5) **Post-processing & validation** → (6) Giao gợi ý + feedback loop → (7) Lặp. **Toxicity filter chạy hai lần**: bước 3 (inbound) và bước 5 (outbound).

**Q2. Một tổ chức muốn IP indemnity. Cần điều kiện gì?**
→ **Gói Business hoặc Enterprise** **VÀ** đặt **Matching public code = Blocked**. Chỉ mua gói mà không bật chặn thì **không được bảo vệ**.

**Q3. Vì sao Cloud Agent là điểm mù bảo mật?**
→ Nó **không tôn trọng content exclusions** và **không tôn trọng public code filter** — hai cơ chế privacy chính. Chỉ dựa vào chúng để bảo vệ code nhạy cảm là **thiếu**, phải kèm quản trị ở tầng khác (giới hạn ai được gán issue, review draft PR).

**Q4. Sự khác biệt về lưu trữ dữ liệu giữa code completion và Chat?**
→ **Code completion trong editor: prompt bị huỷ ngay** sau khi trả gợi ý, **không lưu**. **Copilot Chat dùng ngoài editor: giữ 28 ngày**.

**Q5. Đội cần review tự động cho mọi repo tên kết thúc bằng `service`. Làm sao?**
→ **Ruleset cấp tổ chức** áp theo pattern **`*service`**, bật *Require a pull request before merging* → **Request pull request review from Copilot**. (Mức cá nhân chỉ Pro/Pro+; mức repo chỉ một repo.)

**Q6. Chọn model nào cho phân tích bảo mật code đa luồng, tốn bao nhiêu?**
→ **Premium model (o1-preview / o1-mini)** — **2 PRU/request**, gấp đôi GPT-4o (1 PRU).

**Q7. Cách rẻ nhất để giảm PRU trong một hội thoại dài?**
→ **Tóm tắt ngữ cảnh hoặc reset hội thoại** — từ **2–3 PRU/lượt** về **~1 PRU/request**. Dùng **tham chiếu ngắn gọn** thay vì dán lại code.

**Q8. MCP là gì, ai tạo, ví như cái gì?**
→ **Model Context Protocol**, do **Anthropic** giới thiệu, ví như **"chuẩn USB-C cho công cụ AI"** — cách nhất quán, an toàn để mô hình AI kết nối tool và nguồn dữ liệu. **GitHub MCP Server** có **>30 tool**, endpoint **`https://api.githubcopilot.com/mcp/`**.

**Q9. Khác biệt cấu hình MCP qua remote OAuth và qua Docker?**
→ **Remote**: `MCP: add server` → HTTP → URL → **OAuth một cú bấm**, không cần Docker/file cấu hình. **Docker**: image **`ghcr.io/github/github-mcp-server`**, **bắt buộc PAT** (scope **`repo`** + **`read:packages`**), **không hỗ trợ OAuth**.

**Q10. Copilot Spaces giải quyết vấn đề gì, và không giải quyết vấn đề gì?**
→ Giải quyết **tổ chức ngữ cảnh** (breadth vs depth) để Copilot trả lời sát dự án. **Không** cấp quyền truy cập mới — *"a Space doesn't grant new access"*.

**Q11. Copilot làm được và không làm được gì trong SDLC?**
→ Hỗ trợ mạnh **coding, testing, documentation, review**. **KHÔNG** thu thập requirement và **KHÔNG** trực tiếp tham gia deployment.

**Q12. Ba nhóm phím tắt hay bị hỏi?**
→ **`Tab`/`→`** nhận suggestion, **`Esc`** từ chối · **`Ctrl+Enter`** duyệt nhiều suggestion, **`Alt+]`/`Alt+[`** đi qua lại trong pane · **`Ctrl+I`** inline chat, **`Ctrl+Alt+I`** mở Chat view.

**Q13. Cloud Agent tạo branch tên gì và ai được gán việc cho nó?**
→ Branch tiền tố **`copilot/`**; agent là **`copilot-swe-agent`**. **Chỉ user có write permission** mới ra lệnh được; **người yêu cầu PR không được tự duyệt** PR đó.

**Q14. Ba mitigation cho rủi ro AI trong Responsible AI?**
→ **Robust governance frameworks** · **transparency in AI processes** · **human oversight**.

**Q15. Đo tác động Copilot bằng gì ngoài cảm tính?**
→ **REST API usage metrics** (`GET /enterprises/{enterprise}/copilot/usage`, `GET /orgs/{org}/copilot/usage`) + **khảo sát developer** (**short-form mỗi 2 tuần**, **long-form không quá 1 lần / 4 tuần**) + chỉ số **PR lead time, quality indicators, developer experience**.

**Q16. Nếu đặt content exclusion mà Copilot vẫn gợi ý từ file đó?**
→ Ba khả năng: (1) **chưa tới 30 phút** để có hiệu lực · (2) đang dùng **`@github` trong IDE** — exclusion **không áp** · (3) **semantic information** vẫn lọt, hoặc bạn **không thuộc tổ chức đã cấu hình** policy đó.

**Q17. Ba cách sửa test đang fail?**
→ (1) **Nút Fix Test Failure (sparkle)** trong Test Explorer cho **một** test · (2) **`/fixTestFailure`** trong Chat · (3) **Agent** tự giám sát, sửa và chạy lại khi **hỏng hàng loạt**.

**Q18. Prompt nào tốt hơn và tại sao: `// Create an API endpoint` hay bản có framework?**
→ Bản có framework. Bản đầu **ambiguous and vague** — Copilot có thể dùng **framework bạn không biết** hoặc **endpoint đòi dữ liệu bạn không nhận ra**. Prompt tốt nêu **framework + kiểu payload + HTTP method** để Copilot hiểu **goal và scope**.

`★ Insight ─────────────────────────────────────`
**Ba trục xuyên suốt toàn bộ GH-300 — nắm được thì đoán được đáp án cả những câu chưa gặp:**

1. **Trục gói:** mọi tính năng đều nằm ở một trong ba bậc — *có ở mọi gói* (public code filter, Extensions) / *từ Business* (quản trị, pháp chế, exclusions) / *chỉ Enterprise* (cá nhân hoá theo codebase). Gặp câu hỏi "gói nào có X", hỏi lại: X là **tiện ích**, **quản trị**, hay **cá nhân hoá**?
2. **Trục tự trị:** Inline → Chat → Edits → Agent Mode → Cloud Agent. Càng sang phải, Copilot **tự quyết nhiều hơn**, **tốn PRU nhiều hơn**, và **các cơ chế kiểm soát càng khó áp** (đỉnh điểm: Cloud Agent bỏ qua cả exclusions lẫn public code filter).
3. **Trục dữ liệu:** *đầu vào* (context gathering, content exclusions, context window) ↔ *đầu ra* (toxicity filter, public code match ~150 ký tự, validation). Mỗi cơ chế privacy chỉ chặn được **một trong hai chiều** — đó là lý do phải dùng cả hai.
`─────────────────────────────────────────────────`

## Tự kiểm tra cuối

1. Đọc §11 từ trên xuống, **che cột phải**, tự giải thích từng cặp.
2. Viết lại **bảng PRU §4** từ trí nhớ — sai quá 3 dòng thì đọc lại note 04, 08, 10, 13.
3. Vẽ lại **pipeline 7 bước** và đánh dấu chỗ toxicity filter chạy.
4. Liệt kê đủ **6 nguyên tắc RAI** và **6 tính năng lớn**.
5. Nêu **3 điểm Cloud Agent khác Agent Mode** về mặt **bảo mật**.
6. Với mỗi domain trong §12, kể **hai điều cụ thể** bạn nhớ được.

## Liên quan
- [[00-MOC-GH300|⬅ MOC GH-300]]
- Trước: [[17-Thuc-hanh-Copilot-theo-Ngon-ngu]]
- Nguồn của từng bảng ghi trong cột *Note* — bấm số để mở note gốc:
  [[01-Responsible-AI-voi-Copilot|01]] · [[02-Copilot-la-gi-va-cac-goi|02]] · [[03-Cai-dat-Cau-hinh-va-Cach-tuong-tac|03]] · [[04-Prompt-Engineering-voi-Copilot|04]] · [[05-Copilot-xu-ly-Prompt-va-Du-lieu|05]] · [[06-Copilot-Spaces|06]] · [[07-Copilot-trong-IDE|07]] · [[08-Copilot-tren-GitHub-com|08]] · [[09-Copilot-CLI-va-GitHub-Copilot-App|09]] · [[10-Agent-Mode-trong-IDE|10]] · [[11-Copilot-Cloud-Agent|11]] · [[12-GitHub-MCP-Server|12]] · [[13-Code-Review-va-Pull-Request|13]] · [[14-Quan-tri-va-Tuy-bien|14]] · [[15-Developer-Use-Cases-va-Do-luong|15]] · [[16-Unit-Testing-voi-Copilot|16]] · [[17-Thuc-hanh-Copilot-theo-Ngon-ngu|17]]
