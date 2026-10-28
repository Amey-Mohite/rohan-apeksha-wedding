# Rohan & Apeksha — wedding website source

This ZIP contains the full Cloudflare Worker, including the invitation, admin editor, AR logo, artwork and audio. All media is embedded in worker/index.js. This is a server application, not a file to double-click in your browser.

## Deploy to your own Cloudflare account
1. Install Node.js 22 or newer, unzip this folder, and open a terminal here.
2. Run `npx wrangler@latest login --device --browser=false` and authorize your account.
3. Run `npx wrangler@latest r2 bucket create rohan-apeksha-wedding` (skip if already created).
4. Run `node scripts/configure-admin.mjs` to choose a username and password and securely configure the admin secret.
5. Run `npx wrangler@latest deploy`.

The Worker name is jabvmeta. If the selected account owns apeksharohan.workers.dev, its URL will be https://jabvmeta.apeksharohan.workers.dev/.

The public invitation is at /. The password-protected editor is at /admin. Changes save in the bound R2 bucket. Use the admin password-change form to rotate your password later.

Current hosted runtime credentials and live database contents are NOT in this ZIP. The source includes the original supplied wedding information. Any later edits saved through the hosted admin page must be migrated separately.

For local preview after configuring credentials, run `npx wrangler@latest dev`. Local and remote R2 data are separate. Remote secret configuration is not automatically available to local preview.
