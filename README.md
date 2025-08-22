**tab_report_batch**

| ID  | message_template | customer_category | batch_name       | status  |
| --- | ---------------- | ----------------- | ---------------- | ------- |
| 1   | 001              | Individual        | weekly_positions | CREATED |
|     |                  |                   |                  |         |
**tab_report**

| ID  | batchId | name (predefined list) | type |     |
| --- | ------- | ---------------------- | ---- | --- |
| 1   | 1       | fund_position          | PDF  |     |
| 2   | 1       | cash_position          | PDF  |     |
| 3   | 1       | account_statement      | xlsx |     |

for each tab_report_batch trb:
	customers = fetch all customers with trb.customer_category
	for each customers cust:
		for each trb.report rep:
			link = generate_report(rep.name, cust);
			insert tab_report_attachment with name, cust, link...

**tab_report_attachment**

| ID  | batchId | report_id | customer | report_link        | status  |
| --- | ------- | --------- | -------- | ------------------ | ------- |
| 1   | 1       | 1         | 1000003  | dl/XLMSONDindkmmc  | created |
| 2   | 1       | 2         | 1000003  | dl/XLMSONDindkmee  | created |
| 3   | 1       | 3         | 1000003  | dl/XLMSONDind345g  | created |
| 4   | 1       | 1         | 1000004  | dl/XLMSONDindkm55  | created |
| 5   | 1       | 2         | 1000004  | dl/XLMSONDindkme4e | created |
| 6   | 1       | 3         | 1000004  | d44/XLMSONDind345g | created |
