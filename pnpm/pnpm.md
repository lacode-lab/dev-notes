pnpmへの移行について

miseを使えるようにする
corepack enable

pnpmの少し古いバージョン入れる
mise use -g pnpm@10.0.0

corepack prepare pnpm@10.0.0 --activate


プロジェクトから一回、下を消しておく。



rm -rf node_modules package-lock.json
// これで１ヶ月前までのしかできない。
pnpm config set --location=project minimumReleaseAge 43200


//これで飛ばせるところを飛ばす
pnpm install --ignore-scripts
```
通常のinstall:
パッケージダウンロード → preinstall実行 → インストール → postinstall実行
                         ↑ ここで攻撃コード実行

--ignore-scripts:
パッケージダウンロード → インストール（スクリプト実行なし）

```


// これでlockfileと完全一致しないとダメになるから必ずこれにすること
pnpm install --frozen-lockfile


結構厳密なので足りないパッケージは
addする必要が出てくる。