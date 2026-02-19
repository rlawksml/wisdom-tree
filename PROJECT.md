# WisdomTree

## 개요
WisdomTree - 지혜의 나무

## 레포지토리
https://github.com/rlawksml/wisdom-tree

## 기술 스택
- **프레임워크**: Next.js 15 (App Router)
- **언어**: TypeScript
- **스타일링**: Tailwind CSS
- **백엔드/DB**: Supabase
- **배포**: (TBD)

## 프로젝트 구조
```
wisdom-tree/
├── src/
│   ├── app/              # Next.js App Router (페이지 & API)
│   ├── components/       # 재사용 컴포넌트
│   │   ├── ui/           # 기본 UI 컴포넌트
│   │   └── layout/       # 레이아웃 컴포넌트
│   ├── lib/              # 유틸리티 & 설정
│   │   └── supabase/     # Supabase 클라이언트
│   ├── hooks/            # 커스텀 React Hooks
│   ├── types/            # TypeScript 타입 정의
│   └── constants/        # 상수 정의
├── public/               # 정적 파일
├── supabase/             # Supabase 로컬 설정 & 마이그레이션
└── middleware.ts          # Next.js 미들웨어
```

## 환경 설정
1. `.env.local.example`을 `.env.local`로 복사
2. Supabase 프로젝트 URL과 Anon Key를 설정

## 스크립트
- `npm run dev` - 개발 서버 실행
- `npm run build` - 프로덕션 빌드
- `npm run start` - 프로덕션 서버 실행
- `npm run lint` - ESLint 검사
