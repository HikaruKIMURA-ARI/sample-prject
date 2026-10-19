# ディレクトリ構造

以下のように責務の分離を徹底し、テスト容易性、変更用意性、可読性を最大限に保つこと
例外は必要な場合はユーザーに判断を仰ぐこと

```
src/
├── frontend/                              # React
│   ├── components/                        # Atomic Design / Presentation専用
│   │   ├── atoms/
│   │   ├── molecules/
│   │   ├── organisms/
│   │   └── templates/
│   │
│   ├── pages/
│   │   └── users/
│   │       ├── index.tsx                  # ページのエントリーポイント
│   │       ├── container.tsx              # Hook呼び出し・Props受け渡しのみ
│   │       ├── components/
│   │       │   └── UserList.tsx           # ページ専用Presentation
│   │       └── hooks/
│   │           └── useUsers.ts            # 状態管理・イベント処理・API呼び出し
│   │
│   ├── hooks/                             # 共通Hook
│   ├── routes/                            # TanStack Router
│   └── api/                               # Hono APIクライアント
│
└── backend/                               # Hono / Clean Architecture
    ├── presentation/
    │   ├── routes/
    │   │   └── users.ts                   # エンドポイント定義
    │   ├── handlers/
    │   │   └── UserHandler.ts            # HTTPとUseCaseの橋渡し
    │   └── dto/                           # API入出力の型
    │
    ├── application/
    │   ├── use-cases/
    │   │   ├── GetUsersUseCase.ts         # ユースケース実装
    │   │   ├── input-boundaries/
    │   │   │   └── IGetUsersUseCase.ts    # 入力インターフェース
    │   │   ├── input-data/
    │   │   ├── output-boundaries/
    │   │   │   └── IUsersPresenter.ts     # 出力インターフェース
    │   │   └── output-data/
    │   └── ports/
    │       └── repositories/
    │           └── IUserRepository.ts     # 永続化の抽象
    │
    ├── domain/
    │   ├── aggregates/
    │   ├── entities/
    │   │   └── User.ts                    # ドメインEntity
    │   ├── value-objects/
    │   ├── domain-services/
    │   ├── domain-events/
    │   └── factories/
    │
    └── infrastructure/
        ├── repositories/
        │   └── DrizzleUserRepository.ts   # Repositoryの具象実装
        ├── external-services/             # 外部サービス連携
        └── config/                        # DI・環境設定
```
