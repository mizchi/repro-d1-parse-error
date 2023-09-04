# repro-d1-parse-error

```bash
$ pnpm install
# pnpm wrangler d1 create mydb2
$ pnpm wrangler d1 execute mydb2 --file test.sql --batch-size 1 --yes
```

output

```
$ pnpm wrangler d1 execute mydb2 --file test.sql --batch-size 1 --yes
--------------------
🚧 D1 is currently in open alpha and is not recommended for production data and traffic
🚧 Please report any bugs to https://github.com/cloudflare/workers-sdk/issues/new/choose
🚧 To request features, visit https://community.cloudflare.com/c/developers/d1
🚧 To give feedback, visit https://discord.gg/cloudflaredev
--------------------

🌀 Mapping SQL input into an array of statements
🌀 Parsing 2 statements
✔ ⚠️  Too much SQL to send at once, this execution will be sent as 2 batches.
ℹ️  Each batch is sent individually and may leave your DB in an unexpected state if a later batch fails.
⚠️  Make sure you have a recent backup. Ok to proceed? … yes
🌀 Let's go
🌀 Executing on mydb2 (837018aa-cde8-49ce-ac2a-68225f45dea8):
  select 1
🚣 Executed 1 commands in 0.18669099733233452ms
  -- comment;
select 2

✘ [ERROR] A request to the Cloudflare API (/accounts/f90b16619da21adbec058f5c09b1de53/d1/database/837018aa-cde8-49ce-ac2a-68225f45dea8/query) failed.

  SQL code did not contain a statement. [code: 7500]
  
  If you think this is a bug, please open an issue at:
  https://github.com/cloudflare/workers-sdk/issues/new/choose
```

## LICENSE

MIT