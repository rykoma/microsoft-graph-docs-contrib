# patch-17 ブランチの削除方法

このドキュメントでは、`patch-17` ブランチを削除する方法について説明します。

## 現在の状況

リモートリポジトリに `patch-17` ブランチが存在していることを確認しました。

## 削除方法

### オプション 1: GitHub Web インターフェースを使用（推奨）

1. GitHub リポジトリページに移動: https://github.com/rykoma/microsoft-graph-docs-contrib
2. 「branches」タブをクリック
3. `patch-17` ブランチを探す
4. ブランチの横にあるゴミ箱アイコンをクリック
5. 削除を確認

### オプション 2: Git コマンドラインを使用

リモートブランチを削除するには、適切な権限を持つユーザーが以下のコマンドを実行する必要があります：

```bash
git push origin --delete patch-17
```

または

```bash
git push origin :patch-17
```

### オプション 3: GitHub CLI を使用

GitHub CLI がインストールされている場合：

```bash
gh api -X DELETE repos/rykoma/microsoft-graph-docs-contrib/git/refs/heads/patch-17
```

## 注意事項

- リモートブランチを削除するには、リポジトリへの書き込み権限が必要です
- ブランチを削除する前に、マージされていない重要な変更がないことを確認してください
- ローカルにこのブランチがある場合は、`git branch -d patch-17` でローカルブランチも削除できます

## 確認

ブランチが削除されたことを確認するには：

```bash
git ls-remote --heads origin | grep patch-17
```

何も表示されなければ、ブランチは正常に削除されています。
