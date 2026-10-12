# Trackable — Cloudflare deploy (zero-backend)

## Deploy (2 minutes)
Dashboard → Workers & Pages → Create → Pages → **Upload assets** →
drag this folder in. Add your custom domain. Done — no build, no Git,
no Functions needed.

## Form setup (5 minutes, pick one)

### Formspree (recommended)
1. formspree.io → new form → copy its endpoint (https://formspree.io/f/XXXX).
2. In index.html find `PASTE_YOUR_FORM_ENDPOINT_HERE` and paste it.
3. Re-upload. Leads arrive by email; subject carries firm + platform
   ([LEAD] Firm — PowerTrack (AlsoEnergy)) so Tier 1 self-flags.
   Free tier: 50 submissions/month — plenty for launch.

### Web3Forms (no-account alternative)
1. web3forms.com → enter your email → they send an access key.
2. ENDPOINT='https://api.web3forms.com/submit', ACCESS_KEY='your-key'.
3. Re-upload.

Honeypot is client-side: bots that fill the hidden field get a fake
success and nothing is sent.

## Later, if you ever want leads through your own domain
Migrate to a Worker with static assets (`wrangler deploy` with an assets
binding) and restore the /api/lead handler with Cloudflare's send-email
binding. Not needed for launch.

## Post-launch checklist
- [x] Endpoint configured: https://formspree.io/f/xwlkkjnn
- [ ] Devtools test: fill hidden company_url field → fake success, no email
- [x] Fallback address set: JAMES@TRACKABLE.SYSTEMS
- [ ] Enable Web Analytics on the Pages project (free, cookie-free)
- [ ] Add site URL to outreach signatures + deck closing slide
