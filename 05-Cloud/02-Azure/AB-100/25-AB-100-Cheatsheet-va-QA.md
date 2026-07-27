---
title: "AB-100 Cheatsheet: bảng tra nhanh, cặp dễ nhầm, 35 câu Module assessment & Q&A phỏng vấn"
section: 05-Cloud/02-Azure/AB-100
tags: [azure, ab-100, cheatsheet, on-thi, quiz, module-assessment, interview, skills-measured, copilot-studio, dynamics-365, microsoft-foundry, fresher]
related: ["00-MOC-AB100", "11-Ba-loai-Agent-va-Foundry-Tools", "13-Grounding-Power-Apps-va-Well-Architected", "19-Testing-Quy-trinh-Metrics-va-Validation"]
difficulty: advanced
estimated_time: 75
source: "Tổng hợp toàn bộ 11 docx `_source/Microsoft/AB-100/` + phần Module assessment của cả 11 module"
---

# Note 25 — AB-100 Cheatsheet & Q&A ôn thi

> [!summary] TL;DR
> Note **ôn nhanh 24 giờ trước khi thi**, không dạy khái niệm mới — mọi khái niệm đã nằm ở note 01-24, đây chỉ là bản **nén và đối chiếu**. Sáu phần:
> 1. **Bảng tra nhanh mọi con số** — đề AB-100 hỏi rất nhiều dạng *"bao nhiêu tầng / mấy nguyên tắc / ngưỡng bao nhiêu"*, phần này gom hết vào một chỗ theo cụm.
> 2. **Bảng tra nhanh định danh** — tên sản phẩm, tính năng, cờ cấu hình, viết tắt.
> 3. **Sáu bảng cặp dễ nhầm** — nơi đề hay gài bẫy: *3 loại agent · NLU/CLU/generative · build/buy/extend · Copilot Studio/Foundry/M365 Copilot · MCP/A2A/connector · security/governance/compliance*.
> 4. 🔎 **Ngoài nguồn: 10 mục Skills measured + trọng số** — bản đồ đề chính thức, dùng để phân bổ thời gian ôn.
> 5. **Toàn bộ 35 câu Module assessment** của 11 module — dịch, chỉ đáp án đúng, và **giải thích vì sao ba đáp án còn lại sai** (phần này quan trọng hơn đáp án đúng, vì các đáp án nhiễu chính là hiểu lầm phổ biến mà đề nhắm vào).
> 6. **Q&A phỏng vấn** ở tầm solution architect.
>
> ⚠️ **Đính chính con số:** khi lập kế hoạch tôi ước lượng nguồn có **~39 câu** Module assessment. Đếm chính xác bằng nhãn `Correct` trên cả 11 docx: **đúng 35 câu**. Note này phủ **35/35**.

---

## 1. Bảng tra nhanh mọi con số

### 1.1. Cụm nhập môn & Plan (25–30%)

| Con số | Là gì | Liệt kê | Note |
|---|---|---|---|
| **4** | Vai trò của architect | Strategic Alignment · Solution Design · Governance & Compliance · Scalability | [[01-Vai-tro-AI-Solution-Architect\|01]] |
| **5** | Nhóm trách nhiệm AI architect | Vision & Roadmap · Data Architecture · Integration · Security & Ethics · Performance Monitoring | 01 |
| **5** | Giai đoạn khung chuyển đổi AI | Business Goals → AI Strategy → Architecture Design → Implementation → Monitoring & Optimization | 01 |
| **4** | Đòn bẩy nhân rộng AI | Automation · Standardization · Continuous Learning · User training | 01 |
| **6** | Nguyên tắc Responsible AI | Fairness · Reliability & Safety · Privacy & Security · Inclusiveness · Transparency · Accountability | 01, [[09-Copilot-trong-Dynamics-365-CE-va-Service\|09]], [[24-Governance-Data-Residency-va-Responsible-AI\|24]] |
| **3** | Lợi ích của OOB agent | Faster Deployment · Scalability · Compliance | [[02-Ban-do-cong-nghe-AI-Microsoft\|02]] |
| **3** | Mảng agent thêm giá trị | Task automation · Data analytics · Decision-making | [[03-Phan-tich-yeu-cau-va-Du-lieu-Grounding\|03]] |
| **5** ⭐ | **Chiều chất lượng dữ liệu grounding** | **Accuracy · Relevance · Timeliness · Cleanliness · Availability** | 03 |
| **6** | Pha CAF cho AI adoption | Strategy · Plan · Ready · Govern · Secure · Manage | [[04-CAF-cho-AI-va-Vong-doi-Agent\|04]] |
| **4** | Giai đoạn vòng đời agent | Plan agents · Govern & secure agents · Build agents · Operate agents | 04 |
| **3** | Bậc agent (thang leo) | SaaS (prebuilt) → Low-code (Copilot Studio) → Pro-code (Foundry / container) | [[05-Chien-luoc-Multi-Agent-va-Chon-nen-tang\|05]] |
| **5** ⭐ | **Mẫu điều phối Microsoft Agent Framework** | **Sequential · Concurrent · Group chat · Handoff · Magentic** | 05 |
| **5** | "Fit" biện minh cho custom model | Business · Model · Data · Cost · Operational Fit | 05 |
| **25** | Số **nguồn tri thức tối đa** trong generative orchestration | — | [[06-Nguon-tri-thuc-Prompt-Library-va-SLM\|06]] |
| **500** | Số **knowledge object tối đa / agent** | — | 06 |
| **5** | Số **nguồn phi cấu trúc** xuất hiện đồng thời khi truy hồi | — | 06 |
| **4** | Trụ cột prompt engineering | Clarity · Context · Constraints · Output format | 06 |
| **7** | Trường metadata quản trị của một prompt trong prompt library | — | 06 |
| **5** | Mức trưởng thành prompt library | Basic → … → Enterprise | 06 |
| **7** ⭐ | **Vai trò nghiệp vụ cho workload AI** | executive sponsor · AI CoE lead · product owner · business domain specialist · data owner/steward · RAI-compliance officer · change-management & skilling lead | [[07-Solution-Rules-Vai-tro-va-AI-CoE\|07]] |
| **4** | Nhóm quy định phải rà | Data privacy · AI-specific · Industry · Local | 07 |
| **7** | Bước khung đánh giá tuân thủ theo vùng | — | 07 |
| **3** | Đường tiến hoá của AI CoE | Centralized → Hybrid → Advisory | 07 |
| **4** | Tiêu chuẩn của một mô hình ROI tốt | Measurable · Repeatable · Aligned to business outcomes · **Grounded in real usage analytics** | [[08-ROI-TCO-va-Build-Buy-Extend\|08]] |
| **5** | Nhóm ROI | Productivity Gains · Cost Savings · Revenue Impact · Risk Reduction · Strategic & Innovation Value | 08 |
| **5** ⭐ | **Nhóm chi phí TCO** | **Infrastructure · Development & Integration · Data Quality & Preparation · Expertise & Staffing · Operations & Licensing** | 08 |
| **3** | Con đường triển khai | Build · Buy · Extend | 08 |

### 1.2. Cụm Design (25–30%)

| Con số | Là gì | Liệt kê | Note |
|---|---|---|---|
| **4** | Giai đoạn rải Responsible AI | Design → Development → Deployment → Operations | 09 |
| **4** | Vùng tuỳ biến Copilot trong app D365 | Business terms · Prompt & output · Data scope & field · Surface integration | 09 |
| **2** | Số **app registration** cần cho custom connector (OAuth 2.0 + Entra ID) | — | [[10-Connectors-va-Contact-Center\|10]] |
| **7 ngày** ⭐ | Thời gian **tối đa** để Copilot action mới xuất hiện trong D365 Sales | Đăng xuất/đăng nhập lại để đẩy nhanh | 10 |
| **4** | Kênh của D365 Contact Center | voice · chat · messaging · digital | 10 |
| **6** ⭐ | Thành phần của **task agent** | **Goals · Skills · Actions · Knowledge · Context · Safety & Rules** | [[11-Ba-loai-Agent-va-Foundry-Tools\|11]] |
| **5** ⭐ | Thành phần của **autonomous agent** | **Goals · Triggers · Instructions · Knowledge sources · Actions** | 11 |
| **5** | Nhóm Foundry tool | Retrieval & grounding · Data & application connectors · Workflow & action · Reasoning/planning/execution · Specialized | 11 |
| **5** | Thành phần của một topic | trigger phrases · message nodes · question nodes · conditions & branching · actions | [[12-Copilot-Studio-Topics-Agent-Flows-Prompt-Actions\|12]] |
| **5** | Loại topic | Instructional · Action · Informational · System · Reusable | 12 |
| **2** | Khối tạo nên agent flow | **Trigger + Action** | 12 |
| **5** | Mục của template Prompt Coach | Goal · Context · Instructions/Rules · Examples · Output Format | 12 |
| **5** | Loại prompt action | Transform · Summarize · Extract · Generate · Classify | 12 |
| **4** ⭐ | **Chặng của pipeline grounded AI** | **Ingestion & preparation → Chunking & embeddings → Indexing → Retrieval & orchestration** | [[13-Grounding-Power-Apps-va-Well-Architected\|13]] |
| **5** ⭐ | **Trụ Power Platform Well-Architected** | **Reliability · Security · Operational Excellence · Performance Efficiency · Experience Optimization** ⚠️ Azure WAF thay trụ cuối bằng **Cost Optimization** | 13 |
| **6** | Nhóm tiêu chí thành công (success criteria) | — | 13 |
| **4** | Trụ của AI Adoption Plan theo CAF | — | 13 |
| **5** | Kịch bản biện minh custom model trong Foundry | ngôn ngữ chuyên ngành · quyết định tác động cao · chủ quyền dữ liệu · workflow độc đáo · tối ưu chi phí inference khối lượng lớn | [[14-Extensibility-Custom-Model-M365-Copilot-MCP\|14]] |
| **A/B/C** | Khung thiết kế agent M365 Copilot | Understand the core problem · Define agent behavior · Connect data and tools | 14 |
| **4** | Mẫu cộng tác agent M365 | Sequential · Parallel · Feedback-loop · Orchestrated | 14 |
| **4** ⭐ | **Tầng extensibility trong Copilot Studio** | **Instruction-level · Skill & capability · Integration · Pro-code (VS Code)** | 14 |
| **4** | Tình huống dùng Computer Use | không có API/connector · tác vụ lặp hướng UI · đi qua nhiều app · cần suy luận kiểu người | [[15-Computer-Use-Agent-Behaviors-va-Toi-uu-M365\|15]] |
| **4** | Thành phần hình thành agent behavior | Instructions · Knowledge · Actions and tools · Policies and constraints | 15 |
| **2** | Chế độ suy luận | Standard reasoning ↔ **Deep reasoning (preview)** | 15 |
| **4** | Mẫu giải pháp agent trong M365 | SharePoint knowledge assistant · Teams project assistant · Organizational policy assistant · Site owner support agent | 15 |
| **3** | Loại năng lực AI của D365 Customer Service | Agent Hub · autonomous service agents · Copilot in Contact Center | [[16-Orchestrate-Prebuilt-Agents-va-Apps\|16]] |
| **4** | **Autonomous service agent** có tên riêng | Customer Intent · Case Management · Customer Knowledge Management · Quality Evaluation | 16 |
| **3** ⭐ | **Mô hình trải nghiệm AI** (F&SC và CS) | **Sidecar · Embedded · Outside (external orchestration)** | 16 |
| **8** | Mục của readiness checklist cho agent M365 | — | 16 |
| **8** | Agent trong catalog ready-to-pilot | — | 16 |
| **4** | Thành phần Power Platform AI | AI Hub · Copilot in Power Platform · AI Builder · Copilot Studio | 16 |

### 1.3. Cụm Deploy (40–45%) ← trọng số cao nhất

| Con số | Là gì | Liệt kê | Note |
|---|---|---|---|
| **5** ⭐ | **Tầng giám sát** | **Operational Health · Performance Metrics · Quality & Output Accuracy · Usage Insights · Risk, Compliance & Security** | [[17-Khung-Giam-sat-va-Cong-cu\|17]] |
| **4** | Quy trình giám sát phải khuyến nghị | Establish a Monitoring Operating Model · Configure Guardrails & Threshold Alerts · Conduct Regular Quality Evaluations · Continuously Improve Based on Insights | 17 |
| **6** | Thành phần của monitoring operating model | gồm **vai trò · nhịp rà log · quản lý thay đổi** | 17 |
| **6** | Nhóm công cụ giám sát | Azure Monitor · M365 Admin Analytics · Copilot & Agent Analytics · Power Platform Admin Center · observability tập trung · dashboard tuỳ biến | 17 |
| **6** | Domain phân loại backlog | Accuracy · Knowledge · Performance · UX · Integration · Governance | [[18-Metrics-Telemetry-va-Tuning\|18]] |
| **3** ⭐ | **Nhóm metric hiệu năng agent** | **Operational · Quality & Reasoning · User-Centered** | 18 |
| **4** | Nhóm telemetry | Operational · Model-Level · Behavioral · Governance & Compliance | 18 |
| **4** | Lớp tuning | Knowledge · Behavioral · Performance · Governance-aligned | 18 |
| **6** ⭐ | **Bước quy trình chẩn đoán** | **Monitor → Identify anomalies → Correlate signals → Determine root cause → Apply targeted tuning → Validate improvements** | 18 |
| **4** | Phần của test plan | Test Scope · Test Data · Test Roles · Success Criteria | [[19-Testing-Quy-trinh-Metrics-va-Validation\|19]] |
| **4** | Loại kiểm thử | Scenario-based · Performance & reliability · Safety & compliance · Usability | 19 |
| **5** | Chiều validation cho custom model | performance · quality & accuracy · safety & compliance · cost & efficiency · user-centric | 19 |
| **< 2 giây** ⭐ | Ngưỡng **latency** | — | 19 |
| **≥ 90%** ⭐ | Ngưỡng **accuracy** | — | 19 |
| **≤ 3%** ⭐ | Ngưỡng **incorrect information** | — | 19 |
| **= 0** ⭐ | Ngưỡng **guardrail violations** | Không phải "thấp", mà là **bằng 0** | 19 |
| **100%** ⭐ | Tỷ lệ **sensitive output bị chặn** | — | 19 |
| **≥ 4,5/5** ⭐ | Ngưỡng **user satisfaction** | — | 19 |
| **6** | Bước validate prompt | — | [[20-Testing-Prompt-E2E-va-Sinh-Test-Case\|20]] |
| **8** | Trường của blueprint test case | — | 20 |
| **4** | Tiêu chí rà test case do Copilot sinh | Completeness · Accuracy · Clarity · Maintainability | 20 |
| **6** ⭐ | **Nhóm artifact dữ liệu chịu ALM** | dataset huấn luyện · dataset đánh giá & golden set · tri thức grounding · tài sản prompt · policy & guardrail · telemetry vận hành | [[21-ALM-cho-Du-lieu-va-Copilot-Studio\|21]] |
| **4** | Môi trường trong ALM dữ liệu | **Dev → Test → Pre-Prod → Prod** | 21 |
| **7 (A–G)** | Pha vòng đời dữ liệu | — | 21 |
| **5** | Promotion gate (mỗi gate đòi **bằng chứng**) | — | 21 |
| **3** | Môi trường tối thiểu cho Copilot Studio | Dev / Test / Prod | 21 |
| **7** | Thành phần Foundry agent chịu ALM | — | [[22-ALM-cho-Foundry-Custom-Model-va-D365\|22]] |
| **7** ⭐ | **Giai đoạn vòng đời custom model** | **Plan & Design → Data Preparation → Model Development → Evaluation & Approval → Deployment → Monitor & Optimize → Retirement** | 22 |
| **6 / 7** | Loại tài sản AI trong D365 F&SC / D365 CE & Service | — | 22 |
| **6** ⭐ | **Vùng defense in depth** | **Identity & access · Data governance · Observability & cost · Threat protection · Development & interoperability standards · Incident response** | [[23-Bao-mat-Agent-Model-va-Access-Control\|23]] |
| **5** | Bước blueprint hardening model | — | 23 |
| **5** ⭐ | **Chặng luồng truy xuất grounding** | **Prompt → Policy Check → Search Index → Sanitization Layer → Model Context Injection** | 23 |
| **5** | Thuộc tính kiến trúc của audit trail | immutable · timestamped · gán theo danh tính · log JSON · ghi log tách nhiệm & phê duyệt | 23 |
| **90 ngày / 12–24 tháng / vô thời hạn** ⭐ | Retention audit log theo mức rủi ro | thấp / chịu quản lý / liên quan sự cố | 23 |
| **5** | Nhóm lỗ hổng AI | prompt manipulation · model behavior · data exposure · identity/RBAC gaps · agent & workflow | 24 |
| **4** ⭐ | **Kỹ thuật thao túng prompt** | ghi đè chỉ dẫn hệ thống · ngữ cảnh đánh lừa · ép buộc nhiều bước / đầu vào đầu độc · **nhúng chỉ dẫn ẩn trong text, HTML hoặc file** | 24 |
| **5** | Lớp phòng thủ chống prompt manipulation | — | 24 |
| **5** | Phần của mô hình rà Responsible AI | mục đích & phạm vi · dữ liệu/riêng tư/bảo mật · hành vi model & agent · công bằng & thiên lệch · minh bạch & trải nghiệm | 24 |
| **700/1000** | Điểm đỗ AB-100 | Cert expert-level, **gia hạn hằng năm** miễn phí trên Microsoft Learn | MOC |

`★ Insight ─────────────────────────────────────`
**Vì sao phải học con số chứ không chỉ học ý.** Đề AB-100 dùng rất nhiều câu dạng *"đâu là bước tiếp theo tốt nhất"* — dạng này không hỏi con số. Nhưng chính vì phần lớn câu là dạng phán đoán, **những câu còn lại hầu như đều là câu đếm hoặc câu ngưỡng**, và chúng là điểm "cho không" nếu thuộc. Ngưỡng ở note 19 (`<2s`, `≥90%`, `≤3%`, `=0`, `100%`, `≥4,5/5`) là nhóm dễ mất điểm nhất vì trực giác hay đoán "guardrail violations phải thấp" trong khi nguồn ghi thẳng là **bằng 0**.

**Con số nào KHÔNG nên nhớ máy móc:** những con số chỉ mô tả cách nguồn trình bày (ví dụ "6 nhóm công cụ giám sát") thường có ranh giới mờ. Nhớ *danh sách* quan trọng hơn nhớ *số đếm* — vì đề hỏi "cái nào thuộc nhóm này" nhiều hơn hỏi "có mấy nhóm".
`─────────────────────────────────────────────────`

---

## 2. Bảng tra nhanh định danh

| Định danh | Là gì | Chi tiết cần nhớ |
|---|---|---|
| **Microsoft Foundry** | Nền tảng phát triển/triển khai/quản lý ứng dụng & agent AI | ⚠️ Nguồn dùng tên cũ **"Azure Foundry"** |
| **Copilot Studio** | Nền tảng low-code dựng & tuỳ biến agent | Nơi có topics, agent flows, prompt actions, Computer Use, MCP |
| **Microsoft 365 Copilot** | Copilot nhúng trong Word/Excel/Teams/Outlook | Agent ở đây **kế thừa quyền người dùng** |
| **Dataverse** | Kho dữ liệu nền của Power Platform / Dynamics 365 | Nơi lưu **business terms** (fields, option sets, classification metadata) |
| **Microsoft Graph** | API hợp nhất truy cập dữ liệu M365 | Nền của **semantic indexing** |
| **Copilot Retrieval API** | Lấy đoạn văn liên quan từ SharePoint/OneDrive | ⭐ **Tôn trọng quyền của từng người dùng** |
| **Semantic indexing** | Ánh xạ nội dung doanh nghiệp thành biểu diễn từ vựng + ngữ nghĩa | Đáp án của câu quiz Analyze #3 |
| **Foundry Tools** | 5 nhóm công cụ gắn vào agent Foundry | Chọn theo nguyên tắc **độ phức tạp tối thiểu** |
| **Model router** | Một endpoint hợp nhất tự chọn model phù hợp nhất | Theo task type · năng lực model · chi phí · độ trễ · luật tuỳ biến |
| **AI Builder** | Tính năng AI low-code của Power Platform | Một trong 4 thành phần Power Platform AI |
| **AI Hub** | Điểm khám phá & quản lý năng lực AI trong Power Platform | — |
| **Agent Hub** | Trung tâm quản lý agent trong D365 Customer Service | — |
| **Agent Builder** | Công cụ dựng **declarative agent** cho M365 Copilot | — |
| **Prompt Coach** | Template 5 mục để soạn prompt action | Goal · Context · Instructions/Rules · Examples · Output Format |
| **Agent flow** | Tự động hoá **native** trong Copilot Studio | ⭐ Dùng **message capacity**, **không cần license Power Automate** |
| **Generative pages** | Mô tả bằng ngôn ngữ tự nhiên → Power Apps tự sinh layout/binding/form | — |
| **Agent feed** | Lớp AI đưa insight & next-best action vào trong Power App | — |
| **Computer Use** | Agent điều khiển chuột/bàn phím, thao tác UI | ⭐ **Chỉ dùng khi KHÔNG có API** |
| **Deep reasoning** | Chế độ suy luận nhiều bước | Đang ở trạng thái **preview** |
| **MCP** (Model Context Protocol) | **Hợp đồng ngữ cảnh** có cấu trúc cho agent | Trọng tâm nguồn: **D365 Finance & Operations** |
| **A2A** (Agent2Agent) | Giao thức agent nói chuyện với agent | Nguồn AB-100 chỉ nhắc **2 lần** → xem [[../AI-103/10-A2A-Protocol]] |
| **Copilot client plugins** | Cơ chế mở rộng Copilot trong F&O | Viết bằng **X++** |
| **`Enable onbehalfoflogin = true`** ⭐ | Cờ bật OBO token cho custom connector | Nhớ **đúng chính tả cờ này** |
| **Managed identity** | Danh tính do Azure quản lý, không lưu secret | Nền của model security |
| **Microsoft Purview** | Nền tảng governance dữ liệu | Nhãn nhạy cảm · DLP · audit |
| **Microsoft Sentinel** | SIEM của Microsoft | Nhận log agent để phát hiện bất thường |
| **Azure Monitor + KQL** | Telemetry lõi + ngôn ngữ truy vấn log | — |
| **Managed solution** | Gói giải pháp đã đóng | ⭐ **Chỉ managed solution mới được vào Test và Prod** |
| **Model Card** | Tài liệu mô tả model: chỉ số, ràng buộc, phạm vi dùng | **Hiện vật bắt buộc** trong ALM custom model |
| **Golden / red dataset** | gold = đóng băng đã promote; red = biến đổi được, thử nghiệm | — |

---

## 3. Sáu bảng cặp dễ nhầm

### 3.1. Task agent ↔ Autonomous agent ↔ Prompt-and-response agent

Phân biệt bằng **cái gì khởi động chúng**.

| Tiêu chí | **Task agent** | **Autonomous agent** | **Prompt-and-response agent** |
|---|---|---|---|
| Khởi động bởi | **Người dùng giao việc** | ⭐ **Trigger** (sự kiện/lịch), không chờ người hỏi | **Câu hỏi của người dùng** trong hội thoại |
| Số thành phần | **6** | **5** | (không đếm thành phần, xoay quanh 4 khối) |
| Thành phần | Goals · Skills · Actions · Knowledge · Context · Safety & Rules | Goals · **Triggers** · **Instructions** · Knowledge sources · Actions | NLU Boost (Generative Answers) · System topics · Condition nodes · Event triggers |
| Khác biệt then chốt | Có `Skills`, `Context`, `Safety & Rules` | ⭐ **Thay `Skills/Context/Safety` bằng `Triggers/Instructions`** | Không "làm việc", chủ yếu **trả lời** |
| Mức giám sát cần | Trung bình | **Cao nhất** (chạy không có người) | Thấp nhất |
| Dùng khi | Hoàn thành tác vụ cụ thể thay người dùng | Xử lý nền, phản ứng sự kiện | Hỏi–đáp, tra cứu tri thức |

> **Bẫy hay gặp:** thấy chữ *"độc lập / không cần người"* → autonomous. Thấy *"thay mặt người dùng hoàn thành một hành động"* → task. Thấy *"trả lời câu hỏi"* → prompt-and-response.

### 3.2. Standard NLU ↔ Azure CLU ↔ Generative orchestration

| Tiêu chí | **Standard NLU** | **Azure CLU** | **Generative orchestration** |
|---|---|---|---|
| Cơ chế | Luật + mẫu (pattern) | Model phân loại **huấn luyện được** | **LLM** suy luận |
| Tất định? | ⭐ **Có** (cùng input → cùng output) | Gần tất định | **Không** |
| Dùng khi | Quy trình **chịu quản lý**, cần lặp lại chính xác | Cách diễn đạt **đa dạng** nhưng chủ đề vẫn trong ranh giới | Ngôn ngữ **mở/không đoán trước**, cần suy luận, tóm tắt, sinh nội dung |
| Chi phí & độ trễ | Thấp nhất | Trung bình | Cao nhất |
| Nguồn tri thức | Không áp dụng | Không áp dụng | Tối đa **25 nguồn**, lọc bằng độ liên quan GPT |
| Vai trò tri thức | — | — | Tìm **chủ động** (classic orchestration thì tri thức chỉ là **fallback**) |

> ⭐ **Nguyên tắc chọn của nguồn:** *bắt đầu từ NLU/CLU khi tác vụ có cấu trúc; chỉ dùng generative khi thật sự cần.* Đề hay gài đáp án "dùng generative cho mọi thứ vì linh hoạt hơn" — **sai**.

### 3.3. Build ↔ Buy ↔ Extend

| Tiêu chí | **Build** | **Buy** | **Extend** |
|---|---|---|---|
| Chọn khi | Quy trình **độc đáo**, ⭐ **tạo khác biệt cạnh tranh**, cần kiểm soát toàn phần | Quy trình **chuẩn hoá**, cần **time-to-value** nhanh, độ trưởng thành AI của tổ chức còn thấp | **Cân bằng** — nền tảng có sẵn đã gần đủ, chỉ cần tuỳ biến theo lĩnh vực |
| Chi phí ban đầu | Cao nhất | Thấp nhất | Trung bình |
| Thời gian ra giá trị | Chậm nhất | Nhanh nhất | Nhanh hơn Build |
| Mức tuỳ biến | Cao nhất | Thấp nhất | Trung bình–cao |
| Ví dụ nguồn nêu | **Decision engine chuyên biệt tạo khác biệt cạnh tranh** | HR onboarding chuẩn · email triage đơn giản | Mở rộng **Microsoft Copilot** cho lĩnh vực riêng |
| Rủi ro chính | Đội chi phí, kéo dài, thiếu người | Khoá vào nhà cung cấp, không khớp quy trình | Vướng ranh giới của nền tảng |

> **Cùng một trục với "SaaS agent first"** ở note 05: leo thang chỉ khi bậc dưới không đáp ứng.

### 3.4. Copilot Studio ↔ Microsoft Foundry ↔ Microsoft 365 Copilot

| Tiêu chí | **Copilot Studio** | **Microsoft Foundry** | **Microsoft 365 Copilot** |
|---|---|---|---|
| Bậc | **Low-code** | **Pro-code** | **SaaS / prebuilt** |
| Người dùng chính | Maker nghiệp vụ + IT | Kỹ sư AI / dev | Người dùng cuối |
| Dựng cái gì | Agent hội thoại, task/autonomous agent, agent flow | Agent pro-code, **custom model**, tool, orchestration phức tạp | Agent **declarative** mở rộng Copilot sẵn có |
| Nơi agent chạy | Teams, SharePoint, web, Contact Center… | Ứng dụng tuỳ ý, container, GPU | Trong Word/Excel/Teams/Outlook |
| Quyền dữ liệu | Cấu hình theo connector & knowledge source | Tự thiết kế (managed identity, RBAC) | ⭐ **Tự động kế thừa quyền người dùng** |
| Chọn khi | Cần tuỳ biến vừa phải, tốc độ, quản trị qua Power Platform | Cần custom model, chủ quyền dữ liệu, workflow độc đáo | Tương tác chính diễn ra **trong app M365** và muốn thừa hưởng guardrail RAI có sẵn |
| Guardrail RAI | Cấu hình được | Tự dựng | **Dựng sẵn** |

### 3.5. MCP ↔ A2A ↔ Connector

| Tiêu chí | **MCP** (Model Context Protocol) | **A2A** (Agent2Agent) | **Connector** (custom/standard) |
|---|---|---|---|
| Nối cái gì với cái gì | **Agent ↔ nguồn ngữ cảnh có cấu trúc** | **Agent ↔ agent** | **Agent/app ↔ API hoặc hệ thống ngoài** |
| Bản chất | ⭐ **Hợp đồng ngữ cảnh** — định nghĩa agent *được truy cập gì* và *diễn giải ra sao* | Giao thức **cộng tác** giữa các agent độc lập | **Cây cầu tích hợp** tới một API cụ thể |
| Đối tượng phơi ra | Data entity, business process metadata, domain model, quy tắc bản địa hoá | Năng lực (capability) của agent kia | Endpoint REST theo **OpenAPI definition** |
| Kịch bản mẫu của nguồn | **D365 Finance & Operations** — ledger reconciliation assistant | Nguồn AB-100 chỉ nhắc **2 lần** | **Copilot trong D365 Sales** (OAuth 2.0 + Entra ID) |
| Xác thực | Theo cấu hình MCP server | Theo giao thức A2A | **OAuth 2.0 + Microsoft Entra ID**, 2 app registration |
| Đọc thêm | [[../AI-103/06-Custom-Tools-va-MCP-Tools]] | [[../AI-103/10-A2A-Protocol]] | [[10-Connectors-va-Contact-Center]] |

> **Cách nhớ một câu:** *MCP mang **ngữ cảnh** vào, connector mang **hành động** ra, A2A chia việc cho **agent khác**.*

### 3.6. Security ↔ Governance ↔ Compliance

Ba từ này xuất hiện cạnh nhau trong tên module cuối, và đề gài lẫn nhau.

| Tiêu chí | **Security** (bảo mật) | **Governance** (quản trị) | **Compliance** (tuân thủ) |
|---|---|---|---|
| Trả lời câu hỏi | *"Ai được chạm vào cái gì, và làm sao chặn kẻ tấn công?"* | *"Ai sở hữu, ai duyệt, luật nội bộ là gì?"* | *"Ta có đáp ứng luật/chuẩn bên ngoài không, và chứng minh được không?"* |
| Nguồn của quy tắc | Mô hình mối đe doạ | **Tổ chức tự đặt** | **Bên ngoài** (GDPR, luật AI, chuẩn ngành) |
| Công cụ tiêu biểu | Managed identity, RBAC, private endpoint, DLP, threat protection | **Agent registry** (mục đích · môi trường · **mức rủi ro** · quyền dữ liệu), owner, phê duyệt publish | Data residency, sensitivity label, **audit trail**, RAI review |
| Hiện vật | Blueprint hardening 5 bước, luồng truy xuất 5 chặng | Danh sách owner, quy trình phê duyệt, CAB | Báo cáo rà RAI, log bất biến, bằng chứng gate |
| Hỏng thì hậu quả | Rò rỉ dữ liệu, chiếm quyền agent | ⭐ **Agent sprawl**, không ai chịu trách nhiệm | Phạt, cấm vận hành, mất chứng nhận |
| Note | [[23-Bao-mat-Agent-Model-va-Access-Control]] | [[24-Governance-Data-Residency-va-Responsible-AI]] §1 | 24 §3-§4 |

`★ Insight ─────────────────────────────────────`
**Ranh giới hay bị nhoè nhất là governance ↔ compliance.** Mẹo phân biệt trong phòng thi: nếu câu hỏi nhắc tới **một cơ quan, luật, hay vùng địa lý** → compliance. Nếu nhắc tới **owner, phê duyệt, registry, vòng đời** → governance. Nếu nhắc tới **kẻ tấn công, quyền, danh tính, mã hoá** → security.

**Vì sao đề gộp cả ba vào một module:** vì ở tầm solution architect, ba thứ này dùng chung một bộ điều khiển kỹ thuật. Ví dụ **sensitivity label** vừa là công cụ security (chặn truy cập), vừa là governance (phân loại tài sản), vừa là compliance (bằng chứng cho auditor). Đề tận dụng đúng chỗ chồng lấn này để ra câu nhiễu.
`─────────────────────────────────────────────────`

---

## 4. 🔎 Ngoài nguồn — bản đồ 10 mục Skills measured

> 🔎 **Ngoài nguồn** — bảng này lấy từ [study guide chính thức AB-100 trên Microsoft Learn](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ab-100) (cập nhật **22/07/2026**), **không có trong 11 docx**. Điểm đắt giá: 11 docx ánh xạ **1:1** với 10 mục kỹ năng dưới đây, nên có thể quy đổi thẳng "ôn module nào = ăn bao nhiêu điểm".

| # | Functional group | Trọng số | Mục kỹ năng | Module nguồn | Note |
|---|---|---|---|---|---|
| — | *(nhập môn, không tính điểm riêng)* | — | Nền tảng vai trò architect & bản đồ công nghệ | `Introduction_to_agentic_AI_business_solutions` | 01-02 |
| 1 | **Plan** | **25–30%** | Analyze requirements for AI-powered business solutions | `Analyze_requirements…` | 03 |
| 2 | **Plan** | ↑ | Design overall AI strategy for business solutions | `Design_overall_AI_strategy…` | 04-07 |
| 3 | **Plan** | ↑ | Evaluate costs and benefits of AI solutions | `Evaluate_costs_and_benefits…` | 08 |
| 4 | **Design** | **25–30%** | Design AI and agents for business solutions | `Design_AI_agents…` | 09-13 |
| 5 | **Design** | ↑ | Design extensibility of AI solutions | `Design_extensibility…` | 14-15 |
| 6 | **Design** | ↑ | Orchestrate configuration of prebuilt agents and apps | `Orchestrate_configuration…` | 16 |
| 7 | **Deploy** | **40–45%** | Analyze, monitor, and tune AI agents | `Monitor_analyze_and_tune…` | 17-18 |
| 8 | **Deploy** | ↑ | Manage testing of AI-powered business solutions | `Manage_testing…` | 19-20 |
| 9 | **Deploy** | ↑ | Design ALM process for AI-powered business solutions | `Design_ALM_process…` | 21-22 |
| 10 | **Deploy** | ↑ | Design responsible AI, security, governance, risk management and compliance | `Design_responsible_AI_security…` | 23-24 |

⚠️ **Bẫy phân bổ thời gian ôn (nhắc lại vì quan trọng):** 4 module cụm **Deploy** chỉ chiếm **~29% số ký tự** giáo trình nhưng gánh **40–45% điểm**. Nếu ôn theo độ dày tài liệu thì sẽ dành quá nhiều thời gian cho module `Design_overall_AI_strategy` (97K ký tự, thuộc cụm Plan) và thiếu thời gian cho cụm Deploy. **Đảo ngược lại: ôn note 17-24 trước, note 03-08 sau.**

Điểm đỗ **700/1000**. Cert **expert-level** phải **gia hạn hằng năm** bằng bài đánh giá miễn phí trên Microsoft Learn.

---

## 5. Toàn bộ 35 câu Module assessment — dịch & giải thích

> Đếm chính xác bằng nhãn `Correct` trong 11 docx: **35 câu**. Số câu không đều nhau giữa các module (từ **1** ở module ALM tới **4** ở nhiều module khác) — đó là đặc điểm của nguồn, không phản ánh trọng số đề.
>
> Với mỗi câu: **đáp án đúng in đậm ✅**, các đáp án còn lại kèm lý do sai. **Phần "vì sao sai" đáng học hơn phần đáp án đúng** — mỗi đáp án nhiễu là một hiểu lầm mà người ra đề biết là phổ biến.

### 5.1. Module *Introduction to agentic AI business solutions* (3 câu)

**Câu 1.** Đâu là mô tả đúng nhất về **vai trò chính của architect** trong chuyển đổi AI cho doanh nghiệp?

| Đáp án | Nhận xét |
|---|---|
| Phát triển model machine learning | ❌ Đó là việc của data scientist / ML engineer, không phải architect |
| ✅ **Bắc cầu giữa chiến lược kinh doanh và triển khai kỹ thuật** | ✅ Đúng — câu này lặp lại xuyên suốt giáo trình |
| Quản lý ticket hỗ trợ IT | ❌ Vai trò vận hành, không liên quan |
| Thiết kế giao diện người dùng | ❌ Vai trò UX |

> Vì sao đúng: nguồn định nghĩa AI transformation là **thay đổi chiến lược** chứ không phải nâng cấp công nghệ; nên giá trị của architect nằm ở chỗ **dịch mục tiêu kinh doanh thành kiến trúc**.

**Câu 2.** Trách nhiệm then chốt nào của AI architect bảo đảm giải pháp AI **hiệu quả và bám ưu tiên nghiệp vụ**?

| Đáp án | Nhận xét |
|---|---|
| ✅ **Định nghĩa tầm nhìn và lộ trình áp dụng AI** | ✅ Đúng — đây là trách nhiệm số 1 trong 5 nhóm |
| Viết code cho model AI | ❌ Việc kỹ thuật cấp dưới, không bảo đảm bám ưu tiên nghiệp vụ |
| Dựng máy chủ vật lý | ❌ Không liên quan |
| Chỉ tổ chức đào tạo người dùng cuối | ❌ Từ **"chỉ"** làm đáp án này sai — đào tạo là *một phần*, không phải toàn bộ |

**Câu 3.** Best practice nào architect nên theo để **nhân rộng AI ra toàn doanh nghiệp**?

| Đáp án | Nhận xét |
|---|---|
| Chỉ tập trung nâng cấp công nghệ | ❌ Mâu thuẫn thẳng với luận điểm nền "AI không phải nâng cấp công nghệ" |
| ✅ **Áp dụng nguyên tắc thiết kế mô-đun và linh hoạt** | ✅ Đúng — modular & flexible là điều kiện của scalability |
| Tránh hợp tác với lãnh đạo nghiệp vụ | ❌ Ngược với yêu cầu "foster collaboration among stakeholders" |
| Triển khai AI mà không xét nguyên tắc Responsible AI | ❌ Ngược với yêu cầu "prioritize responsible AI" |

> **Mẫu ra đề lộ ra ở đây:** trong 4 đáp án luôn có **1-2 đáp án bị phủ định trực tiếp bởi giáo trình** ("avoid…", "without considering…", "only…"). Loại chúng trước, rồi chọn giữa 2 đáp án còn lại.

### 5.2. Module *Analyze requirements* (4 câu)

**Câu 1.** Đâu là cách chính mà AI agent **tăng năng suất** trong luồng công việc nghiệp vụ?

| Đáp án | Nhận xét |
|---|---|
| Thay toàn bộ quy trình thủ công bằng hệ thống tự trị hoàn toàn | ❌ Từ **"toàn bộ / hoàn toàn"** — nguồn nói agent **hỗ trợ**, không thay tư duy phản biện |
| ✅ **Soạn nội dung và tóm tắt thông tin bằng generative AI** | ✅ Đúng — đây chính là việc Copilot làm trong Word/Outlook/Teams/D365 |
| Bỏ được nhu cầu đào tạo nhân viên | ❌ Ngược lại, nguồn nhấn mạnh **user training** là 1 trong 4 đòn bẩy |
| Bỏ được yêu cầu về business context trong tự động hoá | ❌ Ngược — business context chính là thứ làm agent hữu ích |

**Câu 2.** Chiều nào của dữ liệu grounding bảo đảm agent lấy được thông tin **khớp với kịch bản nghiệp vụ mong muốn**?

| Đáp án | Nhận xét |
|---|---|
| Cleanliness | ❌ Là **sạch/có cấu trúc, không nhiễu** |
| Availability | ❌ Là **truy cập & lập chỉ mục được theo quyền người dùng** |
| ✅ **Relevance** | ✅ Đúng — *"data matches the intended use case"* |
| Timeliness | ❌ Là **mới, cập nhật** |

> ⭐ **Câu này là lý do phải thuộc định nghĩa của cả 5 chiều, không chỉ thuộc tên.** Đề sẽ mô tả *định nghĩa* rồi bắt chọn *tên*.

**Câu 3.** **Semantic indexing** đóng vai trò gì trong giải pháp Microsoft Copilot?

| Đáp án | Nhận xét |
|---|---|
| Tuỳ biến giao diện người dùng | ❌ Không liên quan |
| ✅ **Ánh xạ nội dung doanh nghiệp để truy hồi dữ liệu chính xác** | ✅ Đúng |
| Quản lý danh sách phân phối email | ❌ Không liên quan |
| Tự động hoá giao dịch tài chính | ❌ Không liên quan |

**Câu 4.** Vì sao phải **tập trung hoá và cấu trúc hoá dữ liệu** nghiệp vụ *trước khi* triển khai agent?

| Đáp án | Nhận xét |
|---|---|
| Để giảm số nhân viên cần thiết | ❌ Không phải mục tiêu của việc chuẩn bị dữ liệu |
| ✅ **Để hệ AI truy cập được dữ liệu chất lượng cao, đáng tin cậy** | ✅ Đúng — "AI readiness" |
| Để dữ liệu tiếp tục nằm rải rác trong các silo | ❌ Ngược hẳn với đề bài |
| Để bỏ được nhu cầu quản trị dữ liệu | ❌ Ngược — tập trung hoá **làm tăng** nhu cầu quản trị |

### 5.3. Module *Design overall AI strategy* (3 câu)

**Câu 1.** Sau khi hoàn tất pha **CAF AI Ready** (landing zone, policy, quyền truy cập dữ liệu), **bước tiếp theo tốt nhất** để tránh **agent sprawl** và **security drift** trước khi bắt tay dựng agent là gì?

| Đáp án | Nhận xét |
|---|---|
| Bắt đầu nối mọi hệ thống line-of-business vào một agent mới | ❌ Đây **chính là** cách tạo ra agent sprawl |
| ✅ **Định nghĩa và thực thi agent governance** (vai trò, chính sách, quy trình phát triển) xuyên các team | ✅ Đúng — trong CAF, **Govern** đứng ngay sau **Ready** |
| Mua thêm GPU | ❌ Vấn đề ở đây là quản trị, không phải năng lực tính toán |
| Nhảy thẳng lên production rồi giám sát sau | ❌ Vi phạm chính nguyên tắc "guardrail trước, build sau" |

> ⭐ **Đây là câu mẫu điển hình nhất của AB-100:** cho một trạng thái trong vòng đời, hỏi **bước kế tiếp**. Muốn trả lời được phải thuộc **thứ tự 6 pha CAF** — *Strategy · Plan · **Ready** · **Govern** · Secure · Manage*.

**Câu 2.** Yếu tố nào architect nên xét **đầu tiên** khi quyết định dùng **SaaS agent** hay **build custom agent**?

| Đáp án | Nhận xét |
|---|---|
| Sự sẵn có của cụm GPU | ❌ Đó là ràng buộc kỹ thuật, xét sau |
| ✅ **Agent SaaS có đáp ứng yêu cầu chức năng không** | ✅ Đúng — chính là nguyên tắc **"SaaS agent first"** |
| Số lượng developer trong dự án | ❌ Yếu tố nguồn lực, xét sau |
| Ngôn ngữ lập trình ưa thích | ❌ Yếu tố sở thích, không phải tiêu chí kiến trúc |

**Câu 3.** Bạn thiết kế giải pháp phải xử lý **dữ liệu tài chính mật** và **dữ liệu sản phẩm công khai**, do **hai team khác nhau** sở hữu, **chu kỳ phát hành riêng**. Kiến trúc nào nên bắt đầu?

| Đáp án | Nhận xét |
|---|---|
| Một agent với quyền rộng | ❌ Vi phạm least-privilege và vượt ranh giới bảo mật |
| ✅ **Multi-agent với quyền cô lập và giao diện tường minh** | ✅ Đúng — hội đủ **2 trong 4 bằng chứng** biện minh multi-agent: *vượt ranh giới bảo mật* + *nhiều team sở hữu, chu kỳ phát hành riêng* |
| Một agent dùng chuyển đổi persona | ❌ Persona **không phải** ranh giới bảo mật — dữ liệu mật vẫn nằm trong tầm với |
| Một agent với context window lớn hơn | ❌ Context window là vấn đề kỹ thuật, không giải quyết vấn đề quyền |

> ⚠️ **Bẫy ngược:** mặc định của nguồn là **single-agent**. Nhưng câu này *cố tình* mô tả đủ bằng chứng để lên multi-agent. **Đừng máy móc chọn single-agent** — hãy đếm xem đề đã cho mấy bằng chứng.

### 5.4. Module *Evaluate costs and benefits* (4 câu)

**Câu 1.** Đâu là chỉ báo ROI **tài chính** (financial)?

| Đáp án | Nhận xét |
|---|---|
| Customer satisfaction score | ❌ ROI **chiến lược / mềm** |
| Minutes saved per workflow | ❌ ROI **theo thời gian** (time-based) |
| ✅ **Money saved per successful agent run** | ✅ Đúng — quy được ra **tiền** |
| Employee sentiment rating | ❌ ROI **chiến lược / mềm** |

> ⭐ **Ba loại ROI phải phân biệt được:** *financial (hard value)* · *strategic/intangible (soft value)* · *time-based*. Câu này gài đúng chỗ đó: "minutes saved" **trông giống** tài chính nhưng là time-based.

**Câu 2.** Yếu tố nào **bắt buộc phải có** để bản phân tích ROI được coi là **hoàn chỉnh**?

| Đáp án | Nhận xét |
|---|---|
| Chỉ tiết kiệm tài chính | ❌ Thiếu chi phí ⇒ **thổi phồng lợi ích** |
| Chỉ số giờ công tiết kiệm | ❌ Cũng chỉ là một nửa |
| ✅ **Cả lợi ích đo được LẪN TCO** | ✅ Đúng |
| Chỉ số tác vụ được tự động hoá | ❌ Là chỉ số hoạt động, không phải ROI |

**Câu 3.** Kịch bản nào chỉ dấu mạnh nhất cho hướng **Build**?

| Đáp án | Nhận xét |
|---|---|
| Quy trình onboarding nhân sự chuẩn | ❌ Chuẩn hoá ⇒ **Buy** |
| Tóm tắt tài liệu chính sách nội bộ | ❌ Năng lực có sẵn ⇒ **Buy/Extend** |
| ✅ **Decision engine chuyên biệt tạo khác biệt cạnh tranh** | ✅ Đúng — độc đáo + chiến lược ⇒ **Build** |
| Phân loại email khách hàng đơn giản | ❌ Chuẩn hoá ⇒ **Buy** |

**Câu 4.** Nhóm TCO nào chứa chi phí **làm sạch dữ liệu, gán nhãn và theo dõi data drift**?

| Đáp án | Nhận xét |
|---|---|
| Infrastructure Costs | ❌ Là compute, lưu trữ, mạng |
| Development and Integration Costs | ❌ Là công dựng và tích hợp |
| ✅ **Data Quality and Preparation Costs** | ✅ Đúng |
| Ongoing Operational Costs | ❌ Là vận hành, license, hỗ trợ sau khi chạy |

> ⭐ **Nhóm TCO này là nhóm dễ quên nhất** khi lập business case, và cũng là nhóm đề hỏi. Nhớ: *drift monitoring nằm ở Data Quality & Preparation*, không nằm ở Operations.

### 5.5. Module *Design AI agents for business solutions* (4 câu)

**Câu 1.** Nguyên tắc Responsible AI nào bảo đảm hệ AI **đối xử công bằng với mọi người và tránh thiên lệch gây hại**?

| Đáp án | Nhận xét |
|---|---|
| Privacy & Security | ❌ Bảo vệ dữ liệu cá nhân |
| ✅ **Fairness** | ✅ Đúng |
| Reliability & Safety | ❌ Hoạt động tin cậy, an toàn |
| Transparency | ❌ Hiểu được hệ thống làm gì và vì sao |

**Câu 2.** Khi tuỳ biến Copilot trong **D365 Customer Service**, bước cấu hình nào bảo đảm Copilot dùng **đúng từ vựng của tổ chức** trong bản tóm tắt?

| Đáp án | Nhận xét |
|---|---|
| Đổi màu giao diện CRM | ❌ Không liên quan tới nội dung sinh ra |
| ✅ **Quản lý các trường được dùng trong case summary** | ✅ Đúng — business terms nằm ở **Dataverse fields / option sets / classification metadata**, Copilot đọc thẳng giá trị đó |
| Chỉ sửa quyền của agent | ❌ Quyền quyết định *thấy gì*, không quyết định *dùng từ nào* |
| Cài entity mới thủ công | ❌ Không phải cách cấu hình business terms |

**Câu 3.** Phương thức xác thực nào **bắt buộc** cho custom connector dùng với Copilot trong **D365 Sales**?

| Đáp án | Nhận xét |
|---|---|
| Basic Auth | ❌ Không đủ an toàn, không hỗ trợ OBO |
| API Key | ❌ Không mang danh tính người dùng |
| ✅ **OAuth 2.0 dùng Microsoft Entra ID** | ✅ Đúng — kèm **2 app registration** và `Enable onbehalfoflogin = true` |
| Truy cập ẩn danh | ❌ Không thể chấp nhận với dữ liệu CRM |

**Câu 4.** Lợi ích chính của việc ánh xạ **từ vựng và quy trình của tổ chức** vào **các trường có cấu trúc** cho Copilot trong D365 là gì?

| Đáp án | Nhận xét |
|---|---|
| Cho phép agent tự đổi workflow tuỳ ý | ❌ Ngược với mục đích — cấu trúc hoá là để **ràng buộc**, không phải nới lỏng |
| ✅ **Bảo đảm insight và khuyến nghị do AI sinh phản ánh đúng nghiệp vụ, giọng điệu và yêu cầu tuân thủ riêng của tổ chức** | ✅ Đúng |
| Cho phép dùng connector bên thứ ba | ❌ Không liên quan |
| Cập nhật theme giao diện D365 | ❌ Không liên quan |

### 5.6. Module *Design extensibility of AI solutions* (4 câu)

**Câu 1.** Kịch bản nào chỉ dấu mạnh nhất cho nhu cầu dùng **custom model trong Microsoft Foundry**?

| Đáp án | Nhận xét |
|---|---|
| Soạn email trả lời chuẩn | ❌ Model có sẵn thừa sức |
| Lấy tài liệu chính sách HR từ SharePoint | ❌ Đây là bài toán **grounding/RAG**, không phải custom model |
| ✅ **Hỗ trợ tính toán kỹ thuật chuyên ngành đòi độ chính xác cao** | ✅ Đúng — khớp kịch bản *"ngôn ngữ/lĩnh vực chuyên ngành + quyết định tác động cao"* |
| Dịch các cụm từ nghiệp vụ thông dụng | ❌ Năng lực phổ thông |

> ⭐ **Bẫy kinh điển:** đáp án "lấy tài liệu từ SharePoint" trông rất "AI doanh nghiệp", nhưng **thiếu dữ liệu chuyên ngành thì phải grounding chứ không phải huấn luyện model**. Nhớ: *custom model đổi **hành vi**, grounding đổi **kiến thức***.

**Câu 2.** Nguyên tắc nào **quan trọng nhất** khi thiết kế agent cho **Microsoft 365 Copilot**?

| Đáp án | Nhận xét |
|---|---|
| Thêm càng nhiều năng lực càng tốt | ❌ Ngược với "least privilege" và "defined mission" |
| ✅ **Bảo đảm agent có ý định rõ ràng, guardrail và quyền được giới hạn phạm vi** | ✅ Đúng |
| Thiết kế agent mà không xét ranh giới dữ liệu | ❌ Bị giáo trình phủ định thẳng |
| Bỏ mọi bước người dùng rà soát | ❌ Ngược với human oversight |

**Câu 3.** Hướng thiết kế nào **cải thiện khả năng mở rộng dài hạn** cho agent Copilot Studio cấp doanh nghiệp?

| Đáp án | Nhận xét |
|---|---|
| Nhồi toàn bộ logic vào **một khối instruction duy nhất** | ❌ Chính là anti-pattern |
| ✅ **Dùng skill mô-đun, tích hợp và thành phần instruction tái sử dụng được** | ✅ Đúng |
| Tránh dùng custom action hay connector ngoài | ❌ Cắt mất tầng Integration trong 4 tầng extensibility |
| Chỉ dựa vào pro-code trong VS Code | ❌ Từ **"chỉ"** làm sai — pro-code là **một** trong 4 tầng, không phải tất cả |

**Câu 4.** Kịch bản nào **rõ ràng nhất** cần đến **extensibility dựa trên MCP** trong Copilot Studio?

| Đáp án | Nhận xét |
|---|---|
| Viết email thân mật cho người dùng cuối | ❌ Không cần ngữ cảnh có cấu trúc |
| ✅ **Lấy ngữ cảnh tài chính có cấu trúc để hỗ trợ trợ lý đối soát sổ cái (ledger reconciliation)** | ✅ Đúng — đúng kịch bản **D365 Finance & Operations** mà nguồn nhấn mạnh |
| Sinh ý tưởng brainstorm | ❌ Năng lực sinh nội dung thuần |
| Dịch tin nhắn giữa các ngôn ngữ | ❌ Năng lực phổ thông |

### 5.7. Module *Orchestrate configuration of prebuilt agents and apps* (4 câu)

**Câu 1.** Lợi ích chính của việc **điều phối tính năng Copilot** xuyên các module **D365 Finance và Supply Chain**?

| Đáp án | Nhận xét |
|---|---|
| Chỉ tự động hoá tác vụ nhập liệu một bước | ❌ Quá hẹp — bỏ mất chữ "orchestrate" |
| ✅ **Tạo quy trình nghiệp vụ có AI: gắn kết, tuân thủ và mở rộng được** | ✅ Đúng — đủ ba tính từ *cohesive · compliant · scalable* |
| Tạo dashboard báo cáo tĩnh | ❌ Báo cáo tĩnh không cần điều phối AI |
| Cho phép người dùng sửa tuỳ chọn cá nhân | ❌ Không liên quan |

**Câu 2.** Trong **D365 Customer Service**, kịch bản nào hưởng lợi **nhiều nhất** từ tính năng AI được điều phối?

| Đáp án | Nhận xét |
|---|---|
| Xuất danh sách khách hàng cho marketing | ❌ Tác vụ dữ liệu một bước |
| ✅ **Xử lý case nhiều bước có tra cứu tri thức và leo thang (escalation)** | ✅ Đúng — nhiều bước + nhiều nguồn ⇒ cần điều phối |
| Cập nhật mô tả catalog sản phẩm | ❌ Tác vụ nội dung đơn lẻ |
| Tải tài liệu hướng dẫn người dùng | ❌ Không có AI |

**Câu 3.** Phát biểu nào phản ánh đúng một **agent Microsoft 365 sẵn sàng cho production**?

| Đáp án | Nhận xét |
|---|---|
| Trả lời được câu hỏi về **mọi** chủ đề trong công ty | ❌ Ngược với "defined mission" — phạm vi vô hạn là dấu hiệu **chưa** sẵn sàng |
| ✅ **Có nhiệm vụ được định nghĩa rõ, TỐI THIỂU công cụ để hành động, guardrail để rà soát được, và telemetry đo kết quả** | ✅ Đúng — đúng tinh thần *"treat an agent like a PRODUCT, not a prompt"* |
| Dùng model lớn nhất có thể để tối đa chất lượng | ❌ Model lớn ≠ sẵn sàng production; còn đội chi phí và độ trễ |
| Hỏi xác nhận trước **mọi** hành động | ❌ Từ **"mọi"** làm sai — HITL phải đặt đúng chỗ rủi ro, không rải khắp nơi |

**Câu 4.** Khi mở rộng trải nghiệm Copilot trong **D365 Finance và Supply Chain**, best practice nào nên theo?

| Đáp án | Nhận xét |
|---|---|
| Hard-code mọi extension vào workflow cụ thể | ❌ Chống lại tính bảo trì và ALM |
| ✅ **Giữ extension mô-đun và tuân thủ ranh giới solution** | ✅ Đúng |
| Cho Copilot truy cập mọi dữ liệu không giới hạn | ❌ Vi phạm least-privilege |
| Tránh căn chỉnh extension theo workflow hiện có | ❌ Ngược với yêu cầu bám quy trình nghiệp vụ |

### 5.8. Module *Monitor, analyze, and tune AI agents* (3 câu)

**Câu 1.** Thành phần then chốt khi thiết lập **monitoring operating model** cho agent là gì?

| Đáp án | Nhận xét |
|---|---|
| Bỏ qua các lần guardrail bị kích hoạt | ❌ Guardrail trigger là tín hiệu quan trọng nhất về rủi ro |
| ✅ **Chuẩn hoá định nghĩa metric và nhịp rà soát log** | ✅ Đúng |
| Tắt hết cảnh báo để giảm nhiễu | ❌ Giải pháp cho "alert fatigue" là **tinh chỉnh ngưỡng**, không phải tắt |
| Cho phép cấu hình agent không hạn chế | ❌ Đó là con đường tới agent sprawl |

**Câu 2.** Khi phân tích **backlog** về việc dùng AI và agent, **bước đầu tiên tốt nhất** là gì?

| Đáp án | Nhận xét |
|---|---|
| Lập tức thiết kế lại prompt của agent | ❌ Sửa trước khi hiểu ⇒ vá triệu chứng |
| ✅ **Phân loại backlog vào các domain có ý nghĩa** | ✅ Đúng — 6 domain: Accuracy · Knowledge · Performance · UX · Integration · Governance |
| Lưu trữ feedback cũ để tránh nhiễu | ❌ Vứt mất tín hiệu |
| Tắt agent tới khi sửa xong | ❌ Phản ứng thái quá, mất giá trị nghiệp vụ |

**Câu 3.** Metric nào **chỉ báo tốt nhất** việc người dùng có đạt được kết quả mong muốn của workflow agent?

| Đáp án | Nhận xét |
|---|---|
| Token usage | ❌ Metric **operational**, nói về chi phí |
| ✅ **Task completion rate** | ✅ Đúng — nguồn ghi thẳng *"the best indicator of user success"* |
| Connector quota | ❌ Metric hạ tầng |
| Storage utilization | ❌ Metric hạ tầng |

> ⭐ **Nhớ trục 3 nhóm metric:** *Operational* (hệ chạy thế nào) · *Quality & Reasoning* (trả lời đúng không) · *User-Centered* (người dùng đạt mục tiêu không). Câu hỏi có chữ **"người dùng đạt được kết quả"** ⇒ luôn rơi vào nhóm thứ ba.

### 5.9. Module *Manage testing AI-powered business solutions* (3 câu)

**Câu 1.** Phát biểu nào giải thích đúng nhất **vì sao kiểm thử phần mềm truyền thống không đủ** cho giải pháp AI?

| Đáp án | Nhận xét |
|---|---|
| Giải pháp AI cần nhiều automation UI hơn app thường | ❌ Không phải bản chất khác biệt |
| ✅ **Đầu ra AI mang tính XÁC SUẤT và có thể thay đổi theo ngữ cảnh, dữ liệu và cách diễn đạt câu hỏi** | ✅ Đúng — câu nền của cả module |
| Hệ AI không cần kiểm định tuân thủ hay an toàn | ❌ Ngược hẳn |
| Giải pháp AI chỉ cần test một lần trước khi triển khai | ❌ Ngược — AI cần test **liên tục** vì có drift |

**Câu 2.** Metric nào **quan trọng nhất** khi kiểm định xem giải pháp AI có cho ra kết quả **bám mục tiêu nghiệp vụ** không?

| Đáp án | Nhận xét |
|---|---|
| Độ dài hội thoại | ❌ Không nói lên chất lượng |
| Số người dùng tương tác với AI | ❌ Là metric **adoption**, không phải chất lượng đầu ra |
| ✅ **Độ chính xác và mức liên quan của câu trả lời** | ✅ Đúng |
| Tần suất cập nhật giao diện | ❌ Không liên quan |

**Câu 3.** Vì sao kịch bản test **end-to-end** phải kiểm định **luồng dữ liệu xuyên nhiều app D365**?

| Đáp án | Nhận xét |
|---|---|
| Vì mỗi app D365 cần một model AI riêng | ❌ Sai về mặt kỹ thuật |
| ✅ **Vì chất lượng đầu ra AI phụ thuộc dữ liệu đầu vào nhất quán, đáng tin và đúng thời điểm từ các hệ thống tích hợp** | ✅ Đúng — ví dụ *Order-to-Cash* và *Case-to-Resolution* |
| Vì không thể test từng app riêng lẻ với giải pháp AI | ❌ Test từng app **vẫn làm được**, chỉ là **chưa đủ** |
| Vì app D365 không chia sẻ dữ liệu được nếu không can thiệp thủ công | ❌ Sai về mặt kỹ thuật |

### 5.10. Module *Design ALM process* (1 câu)

**Câu 1.** Dataset nào **sẵn sàng nhất** để promote lên **Production** trong quy trình AI ALM?

| Đáp án | Nhận xét |
|---|---|
| Bản trích Dev mới nhất, phủ mẫu rộng | ❌ "Mới nhất" và "phủ rộng" **không thay thế được** gate và lineage |
| Dataset Test trông cân bằng nhưng **lineage chỉ có một phần** | ❌ **Lineage thiếu ⇒ trượt gate**, dù dữ liệu trông đẹp |
| ✅ **Dataset BẤT BIẾN, CÓ PHIÊN BẢN, có sensitivity label và lineage đầy đủ, đã qua các evaluation gate** | ✅ Đúng — hội đủ 4 điều kiện |
| Dataset nào cho độ trễ chấp nhận được trong pilot | ❌ Độ trễ là metric **hiệu năng**, không phải điều kiện promote dữ liệu |

> ⭐ **Câu này gói trọn triết lý cụm ALM:** promote **không** dựa trên "dữ liệu trông thế nào", mà dựa trên **bằng chứng** — phiên bản, nhãn, lineage, gate đã qua.

### 5.11. Module *Design responsible AI, security, governance…* (2 câu)

**Câu 1.** Lựa chọn nào phản ánh đúng nhất cách tiếp cận **defense in depth** khi thiết kế agent AI cấp doanh nghiệp?

| Đáp án | Nhận xét |
|---|---|
| Cấp quyền rộng để agent lấy được mọi dữ liệu **có thể** cần trong tương lai | ❌ Vi phạm least-privilege; "phòng xa" kiểu này làm **tăng blast radius** |
| ✅ **Dùng các lớp kiểm soát xếp chồng về identity, access, data governance, monitoring và threat protection** | ✅ Đúng — đúng 5 trong 6 vùng defense in depth |
| Để agent tự sửa hành vi rủi ro mà không cần con người giám sát | ❌ Bỏ mất human oversight |
| Tắt logging để giảm chi phí vận hành | ❌ Mất khả năng audit và điều tra sự cố |

**Câu 2.** Cách **hiệu quả nhất** để giảm rủi ro agent AI **làm lộ thông tin nhạy cảm** là gì?

| Đáp án | Nhận xét |
|---|---|
| Cho phép truy cập connector không hạn chế để tăng độ chính xác truy hồi | ❌ Đánh đổi sai hướng |
| **Chỉ** dựa vào chỉ dẫn của model để tránh trả nội dung nhạy cảm | ❌ ⭐ **Bẫy lớn nhất của module** — chỉ dẫn trong prompt **có thể bị ghi đè** bằng prompt injection; phải chặn ở tầng dữ liệu |
| ✅ **Áp DLP, sensitivity label và ranh giới least-privilege trên MỌI nguồn dữ liệu** | ✅ Đúng |
| Lưu dữ liệu nhạy cảm trong prompt để model suy luận chính xác hơn | ❌ Đưa dữ liệu nhạy cảm vào chỗ dễ rò rỉ nhất |

`★ Insight ─────────────────────────────────────`
**Ba mẫu ra đề rút ra từ 35 câu này** — nhận diện được thì loại đáp án rất nhanh:

1. **Từ tuyệt đối là cờ đỏ.** *"mọi / toàn bộ / chỉ / không cần / tránh"* xuất hiện trong đáp án thì gần như luôn sai (câu Intro #2 "chỉ đào tạo", Extensibility #3 "chỉ pro-code", Orchestrate #3 "mọi chủ đề" và "mọi hành động"). Ngoại lệ duy nhất là các **ngưỡng tuyệt đối có thật** trong note 19: *guardrail violations = **0***, *sensitive output bị chặn **100%***.

2. **Đáp án đúng thường là đáp án DÀI NHẤT và có NHIỀU MỆNH ĐỀ NHẤT.** Vì kiến trúc doanh nghiệp hiếm khi có câu trả lời một vế: *"nhiệm vụ rõ + tối thiểu công cụ + guardrail + telemetry"*, *"bất biến + có phiên bản + có nhãn + có lineage + qua gate"*. Đây không phải mẹo đoán mò — nó phản ánh đúng cách nguồn định nghĩa "sẵn sàng production".

3. **Đáp án nhiễu hay là một khái niệm ĐÚNG nhưng ĐẶT SAI CHỖ.** Ví dụ *"minutes saved per workflow"* là ROI thật, nhưng thuộc nhóm time-based chứ không phải financial; *"lấy tài liệu HR từ SharePoint"* là bài toán AI thật, nhưng cần grounding chứ không cần custom model. Muốn né bẫy này phải thuộc **nhóm nào chứa gì**, không chỉ thuộc tên.
`─────────────────────────────────────────────────`

---

## 6. Q&A phỏng vấn — tầm solution architect

> [!question] **Nhà tuyển dụng:** *"Khách hàng muốn dựng agent AI cho toàn bộ phòng kinh doanh. Bạn bắt đầu từ đâu?"*
> **Trả lời:** Không bắt đầu từ công nghệ. Ba việc theo thứ tự:
> 1. **Business outcome đo được** — agent này làm giảm cái gì, tăng cái gì, đo bằng metric nào. Nếu khách hàng chưa trả lời được thì chưa nên dựng.
> 2. **Rà dữ liệu grounding theo 5 chiều** *Accuracy · Relevance · Timeliness · Cleanliness · Availability*. Dữ liệu không đạt thì agent nào cũng sẽ "confidently incorrect".
> 3. **Áp nguyên tắc SaaS agent first** — hỏi "agent dựng sẵn của M365/D365 có đáp ứng yêu cầu chức năng không?". Có thì dùng luôn. Không thì mới leo lên Copilot Studio, rồi mới tới Foundry.
>
> Và trước khi build bất cứ thứ gì: **định nghĩa governance** (owner, agent registry, mức rủi ro, quy trình phê duyệt). Trong CAF, `Govern` đứng **trước** `Build` — bỏ qua bước này là công thức tạo ra agent sprawl.

> [!question] **Nhà tuyển dụng:** *"Khi nào bạn dùng multi-agent, khi nào không?"*
> **Trả lời:** Mặc định là **single-agent**. Tôi chỉ lên multi-agent khi có **bằng chứng cụ thể**, ít nhất một trong bốn:
> - Giải pháp **vượt ranh giới bảo mật hoặc tuân thủ** (ví dụ dữ liệu tài chính mật và dữ liệu công khai trong cùng một luồng).
> - **Nhiều team sở hữu tri thức riêng và có chu kỳ phát hành riêng.**
> - Có **lộ trình rõ ràng** mở rộng ra 3-5+ chức năng.
> - Nghiệp vụ đòi **chuỗi hành động phụ thuộc nhau qua ≥2 luồng công việc**.
>
> Lý do thận trọng: multi-agent nhân bội chi phí vận hành, giám sát và bề mặt tấn công. Chuyển đổi persona **không phải** ranh giới bảo mật — nếu ai đó đề xuất "một agent, đổi persona theo người dùng" cho dữ liệu mật thì đó là lỗi thiết kế.

> [!question] **Nhà tuyển dụng:** *"Vì sao kiểm thử agent AI khác kiểm thử phần mềm thường?"*
> **Trả lời:** Vì **đầu ra của AI mang tính xác suất**: cùng một ý định, diễn đạt khác đi, ngữ cảnh khác đi, hoặc dữ liệu grounding đổi thì kết quả đổi. Kiểm thử tất định kiểu *"input X phải ra output Y"* không dùng được.
> Thay vào đó tôi test theo **4 loại**: scenario-based (gồm cả **đầu vào mơ hồ và thiếu**), performance & reliability (phiên đồng thời, hội thoại dài), safety & compliance (**đối kháng** — cố tình ép agent vi phạm), usability.
> Và tôi test theo **ngưỡng** chứ không theo khớp chính xác: *latency < 2 giây · accuracy ≥ 90% · thông tin sai ≤ 3% · **vi phạm guardrail = 0** · đầu ra nhạy cảm bị chặn **100%** · hài lòng ≥ 4,5/5*. Hai ngưỡng cuối là tuyệt đối vì chúng là vấn đề an toàn, không phải vấn đề chất lượng.

> [!question] **Nhà tuyển dụng:** *"Agent trả lời sai cho khách hàng. Bạn điều tra thế nào?"*
> **Trả lời:** Theo **quy trình chẩn đoán 6 bước**: *Monitor → Identify anomalies → Correlate signals → Determine root cause → Apply targeted tuning → Validate improvements*.
> Điều quan trọng là **đọc conversation transcript, không chỉ telemetry** — telemetry cho thấy latency tăng hay error spike, nhưng nguyên nhân gốc kiểu "người dùng hỏi theo cách agent không hiểu" thì chỉ transcript mới lộ ra.
> Sau khi biết nguyên nhân, tôi chọn **đúng một trong 4 lớp tuning**: *Knowledge* (nội dung cũ/thiếu) · *Behavioral* (prompt, orchestration, fallback) · *Performance* (workflow, connector) · *Governance-aligned* (DLP, quyền, nhãn nhạy cảm). Sai lớp thì vá triệu chứng chứ không sửa gốc.

> [!question] **Nhà tuyển dụng:** *"Làm sao bạn ngăn agent làm lộ dữ liệu nhạy cảm?"*
> **Trả lời:** Nguyên tắc nền: **không bao giờ trông cậy vào chỉ dẫn trong prompt** — prompt injection ghi đè được chỉ dẫn. Phải chặn ở **tầng dữ liệu và tầng danh tính**:
> - **DLP, sensitivity label và ranh giới least-privilege trên mọi nguồn dữ liệu.**
> - **Mỗi agent một danh tính hạng nhất**, dùng **managed identity** để không còn secret trong code.
> - **Luồng truy xuất có kiểm soát 5 chặng**: *Prompt → Policy Check → Search Index → Sanitization Layer → Model Context Injection* — chính sách chạy **trước** khi chạm chỉ mục, và có lớp làm sạch **trước** khi nhét vào ngữ cảnh model.
> - **Audit trail bất biến ghi METADATA, không ghi NỘI DUNG** — đủ để điều tra mà không tự tạo ra một kho dữ liệu nhạy cảm mới.

> [!question] **Nhà tuyển dụng:** *"Khi nào cần custom model, khi nào chỉ cần grounding?"*
> **Trả lời:** Đây là câu tôi thấy nhiều người nhầm nhất. **Grounding đổi KIẾN THỨC của agent; custom model đổi HÀNH VI của model.**
> Nếu vấn đề là *"agent không biết chính sách nội bộ của công ty"* → grounding/RAG, không cần custom model.
> Custom model chỉ khi hội đủ lý do trong **5 kịch bản**: ngôn ngữ/lĩnh vực chuyên ngành sâu · quyết định tác động cao đòi độ chính xác vượt model chung · chủ quyền dữ liệu · workflow độc đáo · tối ưu chi phí inference ở khối lượng rất lớn.
> Và trước khi quyết, cân đủ **5 Fit**: *Business · Model · Data · Cost · Operational Fit*. Thiếu **Operational Fit** (đội ngũ có nuôi nổi model không, có MLOps không, có xử lý drift được không) là lý do phổ biến nhất khiến dự án custom model chết sau 6 tháng.

> [!question] **Nhà tuyển dụng:** *"Chứng minh ROI của một dự án agent cho ban lãnh đạo — bạn trình bày thế nào?"*
> **Trả lời:** Tôi luôn trình **hai vế cạnh nhau, không bao giờ trình một vế**:
> - **Lợi ích** theo 3 loại: *financial* (tiền tiết kiệm mỗi lần agent chạy thành công) · *strategic/intangible* (hài lòng khách hàng, tuân thủ, nhất quán) · *time-based* (phút tiết kiệm mỗi workflow, thời gian chu kỳ giảm).
> - **TCO đủ 5 nhóm**: *Infrastructure · Development & Integration · **Data Quality & Preparation** · Expertise & Staffing · Operations & Licensing*.
>
> Nhóm hay bị bỏ quên là **Data Quality & Preparation** — làm sạch, gán nhãn, và **theo dõi data drift**. Bỏ nhóm này thì ROI trông đẹp trong slide và vỡ sau quý đầu.
> Và số liệu phải **neo vào phân tích sử dụng thực tế** (Copilot Studio ROI analytics / Savings Calculator), không phải ước đoán — đó là tiêu chuẩn thứ tư của một mô hình ROI tốt.

---

## Tự kiểm tra

Trả lời không nhìn note. Câu nào bí thì mở đúng note được trỏ.

**Con số & danh sách**
1. **Năm chiều** chất lượng dữ liệu grounding? Chiều nào trả lời "khớp kịch bản nghiệp vụ"?
2. **Sáu pha CAF** theo đúng thứ tự? Pha nào đứng ngay sau `Ready`?
3. **Năm mẫu điều phối** của Microsoft Agent Framework?
4. Ba con số giới hạn của knowledge source trong Copilot Studio (**500 / 25 / 5** — mỗi con số ứng với gì)?
5. **Năm nhóm TCO**? Chi phí theo dõi **data drift** nằm ở nhóm nào?
6. Task agent có **mấy** thành phần, autonomous agent **mấy**, và autonomous **thay** thành phần nào bằng thành phần nào?
7. **Bốn chặng** pipeline grounded AI? Chế độ tìm kiếm mặc định là gì?
8. **Năm trụ** Power Platform WAF? Trụ nào **khác** Azure WAF?
9. **Năm tầng giám sát** theo thứ tự leo thang?
10. **Sáu bước** quy trình chẩn đoán? Metric nào là chỉ báo tốt nhất cho thành công của người dùng?
11. Đọc thuộc **6 ngưỡng validation** của custom model (latency, accuracy, thông tin sai, guardrail, đầu ra nhạy cảm, hài lòng). Hai ngưỡng nào là **tuyệt đối**?
12. **Sáu vùng** defense in depth? **Năm chặng** luồng truy xuất grounding?
13. Ba mức **retention** audit log và điều kiện áp dụng từng mức?
14. **Bảy giai đoạn** vòng đời custom model? Hiện vật bắt buộc là gì?

**Phân biệt**
15. Ba loại agent phân biệt bằng **cái gì**? Cho một tình huống bất kỳ, chọn loại nào?
16. Khi nào chọn **CLU** thay vì **Standard NLU**, và khi nào mới leo lên **generative orchestration**?
17. **Build / Buy / Extend** — cho ba tình huống, phân loại từng cái.
18. Ba nền tảng **Copilot Studio / Foundry / M365 Copilot** — cái nào tự động kế thừa quyền người dùng?
19. **MCP / A2A / connector** — mỗi cái nối cái gì với cái gì? Nói lại bằng một câu.
20. **Security / governance / compliance** — cho ba câu hỏi, phân loại từng câu thuộc nhóm nào.

**Bẫy đề**
21. Vì sao "lấy tài liệu HR từ SharePoint" **không phải** lý do dựng custom model?
22. Vì sao "chuyển đổi persona trong một agent" **không** giải quyết được bài toán ranh giới bảo mật?
23. Vì sao "chỉ dựa vào chỉ dẫn của model để tránh lộ dữ liệu nhạy cảm" là **sai**?
24. Vì sao dataset "trông cân bằng nhưng lineage chỉ có một phần" **không** được promote lên Production?
25. Ba mẫu ra đề đã rút ra ở §5 là gì? Ngoại lệ của mẫu "từ tuyệt đối là cờ đỏ" nằm ở đâu?

**Tổng hợp**
26. Trọng số ba cụm là bao nhiêu? Cụm nào có tỷ lệ **điểm/độ dày tài liệu** cao nhất, và điều đó đổi thứ tự ôn thế nào?
27. Điểm đỗ? Cert này gia hạn ra sao?

## Liên quan
- [[00-MOC-AB100]] — MOC bộ AB-100, bản đồ toàn bộ 25 note
- [[24-Governance-Data-Residency-va-Responsible-AI]] — note trước: governance, lỗ hổng AI, Responsible AI, data residency
- [[01-Vai-tro-AI-Solution-Architect]] — quay lại đầu: vai trò architect & khung chuyển đổi
- [[19-Testing-Quy-trinh-Metrics-va-Validation]] — nguồn của bảng ngưỡng validation
- [[../AI-103/00-MOC-AI-103|MOC: AI-103]] — nền tảng kỹ thuật Foundry-era cho AB-100
- [[../00-MOC-Azure]] — MOC Azure tổng
- [[../../../00-INDEX|🏠 Index tổng]]
