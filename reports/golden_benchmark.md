# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **17/20**
- Evidence hit rate: **85.0%**
- Average retrieval latency: **1040.5 ms**
- Average token reduction vs full source context: **18.8%**
- Golden bonus: **0/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G02 | long_term | PASS | 1488.3 | 1253 | 0.0% |  |
| G03 | long_term | FAIL | 1386.4 | 1257 | 0.0% | missing=benchmark report, 16:00 |
| G06 | semantic | PASS | 295.7 | 148 | 67.8% |  |
| G09 | long_term | PASS | 1454.1 | 746 | 0.0% |  |
| G10 | short_term | PASS | 0.1 | 147 | 0.0% |  |
| G12 | long_term | FAIL | 1410.6 | 1257 | 0.0% | missing=Java |
| G13 | long_term | FAIL | 1533.8 | 1252 | 0.0% | missing=ngan |
| G14 | long_term | PASS | 2148.5 | 1258 | 0.0% |  |
| G15 | semantic | PASS | 282.6 | 294 | 35.9% |  |
| G16 | semantic | PASS | 245.7 | 148 | 67.8% |  |
| G19 | long_term | PASS | 1806.0 | 746 | 0.0% |  |
| G20 | long_term | PASS | 2669.3 | 1255 | 0.0% |  |
| G04 | episodic | PASS | 291.0 | 144 | 34.8% |  |
| G05 | episodic | PASS | 703.2 | 97 | 56.1% |  |
| G07 | mixed | PASS | 1750.9 | 485 | 14.2% |  |
| G11 | semantic | PASS | 298.2 | 146 | 74.2% |  |
| G18 | episodic | PASS | 278.8 | 167 | 24.4% |  |
| G08 | long_term | PASS | 1432.1 | 1244 | 0.0% |  |
| G17 | long_term | PASS | 1335.6 | 1262 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G02 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-03 10:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ho`

### G03 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G06 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata=`

### G09 - long_term

`<USER_SUMMARY> Lan Tran's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in that capacity. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.`

### G10 - short_term

`<SESSION_SUMMARY> user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. | assistant: Acknowledged review constraint. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. - assistant: Acknowledged review constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler turn 1 about UI spacing. assistant: Filler answer 1. user: Filler turn 2 about naming. assistant: Filler answer 2. user: Filler turn 3 about logging. assistant: Filler answer 3. </RECENT_TURNS>`

### G12 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G13 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-03 10:03:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G14 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G15 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls tim`

### G16 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata=`

### G19 - long_term

`<USER_SUMMARY> Lan Tran's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in that capacity. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.`

### G20 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-03 10:03:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G04 - episodic

`EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI`

### G05 - episodic

`EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn.`

### G07 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh N`

### G11 - semantic

`EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata= EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata=`

### G18 - episodic

`EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python.`

### G08 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }: Ca`

### G17 - long_term

`<USER_SUMMARY> Minh Nguyen's company project BLUEBIRD-42 requires the backend to be built with TypeScript and NestJS, explicitly prohibiting the use of Python for this project. For personal demos, Minh prefers using Python for the ORCHID-27 project.  Minh prefers Python for personal demos such as ORCHID-27. For the company project BLUEBIRD-42, the backend must be implemented using TypeScript with NestJS. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:20     Source: message     Content: Lab Assistant (assistant): Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python. </EPISODES> `
