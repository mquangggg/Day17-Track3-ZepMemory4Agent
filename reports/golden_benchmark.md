# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1063.1 ms**
- Average token reduction vs full source context: **6.3%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.1 | 133 | 0.0% |  |
| G08 | long_term | PASS | 1513.8 | 821 | 0.0% |  |
| G09 | long_term | PASS | 1729.8 | 1428 | 0.0% |  |
| G12 | semantic | PASS | 252.4 | 418 | 8.9% |  |
| G14 | semantic | PASS | 259.2 | 270 | 30.2% |  |
| G15 | semantic | PASS | 279.7 | 270 | 41.2% |  |
| G19 | mixed | PASS | 1840.0 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1655.2 | 1428 | 0.0% |  |
| G04 | long_term | PASS | 1819.4 | 1434 | 0.0% |  |
| G05 | long_term | PASS | 1446.5 | 1430 | 0.0% |  |
| G10 | episodic | PASS | 295.3 | 350 | 0.0% |  |
| G11 | episodic | PASS | 585.7 | 527 | 0.0% |  |
| G13 | semantic | PASS | 267.0 | 416 | 26.4% |  |
| G16 | mixed | PASS | 1729.3 | 581 | 0.0% |  |
| G18 | mixed | PASS | 586.3 | 500 | 11.5% |  |
| G20 | mixed | PASS | 2065.1 | 831 | 0.0% |  |
| G06 | long_term | PASS | 1547.1 | 1425 | 0.0% |  |
| G07 | long_term | PASS | 1481.1 | 1425 | 0.0% |  |
| G17 | mixed | PASS | 1908.4 | 581 | 8.1% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G08 - long_term

`<USER_SUMMARY> Lan's main pursuit is the LOTUS-88 project, with a focus on Java and Spring Boot for backend development. Lan explicitly avoids using Python in the backend.  Lan prefers Java and Spring Boot for backend development and does not want Python used in the backend. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 `

### G09 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G12 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transi`

### G14 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marke`

### G15 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marke`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan's main pursuit is the LOTUS-88 project, with a focus on Java and Spring Boot for backend development. Lan explicitly avoids using Python in the backend.  Lan prefers Java and Spring Boot for backend development and does not want Python used in the backend. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:45:29     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Lan uu tien stack backend nao cho LOTUS-88?   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assis`

### G03 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G04 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G05 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G10 - episodic

`EPISODE: Toi nay minh muon viet cho tron ven cai retry payment ma vua dung so thich stack ca nhan cua minh, vua theo dung policy thanh toan chinh thuc, vua tranh dam lai dung cai su co asyn EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Tuan nay minh moi bi keo vao cai du an ben cong ty va sep hoi lien tuc ve chuyen chuan hoa backend, ma minh thi hoi mo ho vi truoc gio minh xai nhieu thu khac nhau cho project rien EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngo`

### G11 - episodic

`EPISODE: Minh dang ngoi mot minh viet cho xong cai ham retry cho POST payment de toi nay demo, va minh muon no vua dung dung ngon ngu ma minh thich khi lam viec ca nhan, vua bam sat dung po EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay min EPISODE: Toi nay minh muon viet cho tron ven cai retry payment ma vua dung so thich stack ca nhan cua minh, vua theo dung policy thanh toan chinh thuc, vua tranh dam lai dung cai su co asyn EPISODE: Tuan nay minh moi bi keo vao cai du an ben cong ty va sep hoi lien tuc ve chuyen chuan hoa backend, ma minh thi hoi mo ho`

### G13 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream s`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining`

### G18 - mixed

`<EPISODIC> EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay min EPISODE: Toi nay minh muon viet cho tron ven cai retry payment ma vua dung so thich stack ca nhan cua minh, vua theo dung policy thanh toan chinh thuc, vua tranh dam lai dung cai su co asyn EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Tuan nay minh moi bi keo vao cai du an ben cong ty va sep hoi lien tuc ve chuyen chuan hoa backend, ma minh thi hoi mo ho vi tr`

### G20 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining`

### G06 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G07 - long_term

`<USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining async/await`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is studying async/await and is working on a personal project named ORCHID-27. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, not Python. Python is still preferred for personal demos like ORCHID-27. Minh is debugging async HTTP requests and focused on resolving connection churn issues. Minh also has a task to complete a benchmark report by Friday at 16:00, designated as OPEN LOOP LAB-REPORT-1600.  Minh likes Python and dislikes Java. When explaining code, Minh prefers short examples. Minh's effective solution for async HTTP request issues involves reusing an aiohttp ClientSession and setting concurrency to 20.  When explaining`
