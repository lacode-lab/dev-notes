# Prisma Studio（通常はこのポートで起動）
http://localhost:5555

# PostgreSQL接続確認用（環境による）
# DATABASE_URL="postgresql://user:password@localhost:5432/dbname"


# 開発フロー例
# 1. スキーマ編集後
pnpm prisma format

# 2. マイグレーション作成
pnpm prisma migrate dev --name add_user_table

# 3. Prisma Client再生成（通常は自動）
pnpm prisma generate

# 4. DBの内容確認
pnpm prisma studio