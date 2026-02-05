# claw-checkin

ClawdCon check-in service (separate from demos/voting).

## Goals
- Fast door check-in (QR scan + fallback search)
- Integrate with Luma API (server-side `LUMA_API_KEY`)
- Produce a durable **"human verified"** signal: **any ClawdCon check-in ever**
- Expose a small API that other ClawdCon apps can call

## Pilot mapping
- `claw-con-denver-2026` → Luma event id `evt-ERBCC1uBPoAdSWe`

## Environment
Copy `.env.example` to `.env.local` for local dev. In production, set env vars in Vercel.

## Development
```bash
npm install
npm run dev
```

## Planned API (draft)
- `POST /api/checkin/lookup` (QR payload or search query → candidate guest)
- `POST /api/checkin/mark` (mark check-in + write audit log)
- `GET /api/human-status` (is this identity human verified?)

## Notes
This repo is intentionally small and API-first. It should be deployable independently at `checkin.clawdcon.com`.
