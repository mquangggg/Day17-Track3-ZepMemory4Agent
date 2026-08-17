# Báo cáo Nộp bài Lab 17 - Multi-Memory Agent với Zep

**Họ và tên / Mã học viên:** Vũ Minh Quang - 2A202601515
**Ngày thực hiện:** 2026-08-17

---

## 1. Kết quả Đánh giá Benchmark (Practice Set E01-E11)

- **Student Hit Rate (Practice Set E01-E11):** **11/11 PASS (100%)**
- **Golden Set Hit Rate (G01-G20):** **20/20 PASS (100% - Điểm cộng tuyệt đối +10/10)**
- **Baseline (No-memory) Hit Rate:** **2/11 PASS (18.2%)** (Chỉ vượt qua các case Short-term local)
- **Artefacts sinh ra:** `reports/benchmark.md`, `reports/benchmark_no_memory.md`, `reports/comparison.md`, `reports/golden_benchmark.md`

---

## 2. Phân tích Kết quả Benchmark & So sánh

1. **Layer có hit rate thấp nhất ở Baseline:** Tất cả các layer bền vững (Long-term, Episodic, Semantic) ở bài test No-memory đều bị FAIL (0% hit rate) do không truy xuất được chứng cứ lịch sử/tri thức.
2. **Case retrieve nhiều token nhất:** Case `E08` và `E06` (truy xuất danh sách facts/episodes và semantic rules dài nhất).
3. **Case hỗn hợp (E07 - Mixed):** Cần kết hợp Long-term Memory (để biết sở thích ngôn ngữ Python của Minh) và Semantic Memory (để biết quy tắc retry payment `Idempotency-Key`).
4. **Token reduction vs Hit rate:** Baseline No-memory có tỷ lệ giảm token cao vì không đính kèm thông tin bộ nhớ nào, nhưng làm giảm sút hit rate thảm hại (chỉ đạt 18.2%).

---

## 3. Câu hỏi Thu hoạch (README Submission - 3 câu bắt buộc)

### Câu 1: Layer bộ nhớ nào quan trọng nhất trong bộ test này? Chỉ ra các test case minh họa.
- **Trả lời:** Layer **Long-term Memory** (kết hợp Context Block) đóng vai trò quan trọng nhất trong bộ test này.
- **Minh họa:** Các case **E02, E03, E08, E09**. Ví dụ, case `E08` yêu cầu truy xuất sở thích dự án `BLUEBIRD-42` (TypeScript + NestJS) từ phiên làm việc trước; case `E09` thử nghiệm User Isolation đảm bảo không rò rỉ dữ liệu giữa người dùng `lan-lab17` và `minh-lab17`.

### Câu 2: Trade-off giữa việc dùng Zep Context Block (Managed Memory) so với việc tự xây dựng trên Redis + Qdrant?
- **Zep Context Block (Managed):**
  - *Ưu điểm:* Tự động tổng hợp facts, quản lý User Graph, giải quyết xung đột thông tin (recency/conflict resolution), cung cấp API đơn giản (`get_user_context`).
  - *Nhược điểm:* Phụ thuộc vào dịch vụ bên ngoài, phát sinh độ trễ mạng (network latency) và chi phí SaaS.
* **Redis + Qdrant (Self-managed):**
  - *Ưu điểm:* Hoàn toàn chủ động dữ liệu, độ trễ rất thấp (local), phù hợp lưu KV profile đơn giản.
  - *Nhược điểm:* Phải tự viết logic chắt lọc facts, tự giải quyết mâu thuẫn dữ liệu và tự quản lý index/chunking phức tạp khi quy mô lớn.

### Câu 3: Guardrail chống Memory Poisoning (Nhiễm độc bộ nhớ) cho AI Agent?
- **Trả lời:** 
  1. **Validation & Sanitization:** Kiểm tra tính hợp lệ và loại bỏ các câu lệnh độc hại/prompt injection trước khi lưu vào durable memory.
  2. **Opt-in & Consent Control:** Áp dụng Privacy-by-design (như `data/consent.json`), chỉ ghi nhận bộ nhớ khi được consent.
  3. **Verification / Heartbeat Audit:** Định kỳ lọc de-duplicate, đánh dấu stale tasks và không tự động cấp thêm quyền/instruction mới vào durable memory qua background jobs.

---

## 4. Bằng chứng Privacy Drill (Right to be Forgotten)

- **Lệnh xóa user:** `python -m src.forget --user-id minh-lab17`
- **Kết quả Verify (`--verify-only`):**
  ```text
  Zep user absent: True
  Redis user keys remaining: 0
  Shared semantic KB remains intact because it stores domain knowledge, not user PII.
  ```
- **Xác nhận:** Đã xóa triệt để thông tin cá nhân của user `minh-lab17` trên Zep và Redis mà không ảnh hưởng tới Knowledge Base dùng chung.
