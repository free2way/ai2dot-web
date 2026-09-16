# AI2Dot marketing website

This repository is the standalone Next.js marketing website for `www.ai2note.com`. The AI2Dot product application lives separately at `https://ai.ai2dot.com/`.

## Local development

```bash
npm install
npm run dev
```

The product CTA target is defined once in `lib/site.ts` and points to `https://ai.ai2dot.com/`.

## Contact form

Copy `.env.example` to `.env.local` and configure:

- `RESEND_API_KEY`: Resend API key
- `CONTACT_TO_EMAIL`: inbox that receives enterprise leads
- `CONTACT_FROM_EMAIL`: verified sender, for example `AI2Dot <business@updates.example.com>`

Without these variables, the form returns a clear configuration error and does not claim that a message was sent.

## Vercel deployment

Create a Vercel project from this repository. The application is already at the repository root, so no custom Root Directory is required.

1. Import `free2way/ai2dot-web` as a new Vercel project.
2. Keep Framework Preset as Next.js. Build and output settings can stay automatic.
3. Add the three contact-form environment variables for Production and Preview.
4. Add `www.ai2note.com` under Domains.
5. Configure the DNS record exactly as Vercel displays, then verify the domain.

This produces two isolated deployments:

- Product application: `ai.ai2dot.com`, repository `free2way/ai2dot`
- Marketing website: `www.ai2note.com`, repository `free2way/ai2dot-web`

## Verification

```bash
npm run lint
npm run typecheck
npm run build
```
