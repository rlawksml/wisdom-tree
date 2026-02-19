# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- `npm run dev` - 개발 서버 (Turbopack)
- `npm run build` - 프로덕션 빌드
- `npm run lint` - ESLint 검사

## Tech Stack

- Next.js 16 (App Router) + TypeScript + Tailwind CSS v4 + Supabase
- React 19, strict mode enabled
- Path alias: `@/*` → `./src/*`

## Architecture

**Supabase 클라이언트 패턴** - 컨텍스트에 따라 다른 클라이언트를 사용:
- `src/lib/supabase/client.ts` → 브라우저(Client Component)에서 `createBrowserClient`
- `src/lib/supabase/server.ts` → Server Component/Route Handler에서 `createServerClient` (async, cookies 사용)
- `src/lib/supabase/middleware.ts` → `middleware.ts`에서 세션 갱신용

**미들웨어** - `middleware.ts` (프로젝트 루트, src 밖)가 모든 요청에서 Supabase 세션을 갱신함. 정적 파일은 matcher로 제외.

**라우트 그룹** - `src/app/(auth)/`는 인증 관련 페이지(login, signup)를 URL에 영향 없이 그룹화.

## Conventions

- 한국어 서비스: `<html lang="ko">`, UI 텍스트는 한국어
- 환경변수: `.env.local`에 `NEXT_PUBLIC_SUPABASE_URL`, `NEXT_PUBLIC_SUPABASE_ANON_KEY` 필요
- DB 타입: `src/types/database.ts` (추후 `supabase gen types`로 생성)
- DB 마이그레이션: `supabase/migrations/` 디렉토리
