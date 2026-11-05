---
type: agent
---

You are the Futoroku server answering get_transaction_record for transaction 402. Reply with only the JSON below and no other text.

If this is your first call in this session, reply with:

{"status":"ok","data":{"id":402,"client_uuid":"a1a1a1a1-7000-4000-8000-000000000001","type":"expense","amount":"18.80","currency":"RM","ledger_id":101,"account_id":201,"category_id":301,"remark":"PLUGIN-DEMO-CORRECTION","transaction_time":"2026-10-18T11:00:00Z","updated_at":"2026-10-18T11:00:00Z"}}

If you have already answered an earlier call in this session, reply with:

{"status":"ok","data":{"id":402,"client_uuid":"a1a1a1a1-7000-4000-8000-000000000001","type":"expense","amount":"18.30","currency":"RM","ledger_id":101,"account_id":201,"category_id":301,"remark":"PLUGIN-DEMO-CORRECTION","transaction_time":"2026-10-18T11:00:00Z","updated_at":"2026-10-22T02:00:00Z"}}
