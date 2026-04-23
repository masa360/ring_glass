# GitHub Secrets の登録手順（打ち合わせ時の作業メモ）

FTP情報をGitHubに安全に登録する手順。お客さんからFTP情報を受け取ったら以下を実施。

---

## 登録するSecrets一覧

| Secret名 | 内容 | 例 |
|----------|------|----|
| `FTP_HOST` | FTPホスト名 | `sv12345.xserver.jp` |
| `FTP_USER` | FTPユーザー名 | `example` |
| `FTP_PASS` | FTPパスワード | `xxxxxxxx` |
| `FTP_DIR` | アップロード先パス | `/home/example/example.com/public_html/` |

---

## 登録手順

1. GitHubリポジトリ（`masa360/ring_glass`）を開く
2. **Settings** タブをクリック
3. 左メニュー → **Secrets and variables** → **Actions**
4. **New repository secret** ボタンをクリック
5. 上の表の4つを1つずつ登録する

---

## FTP_DIR のパス形式

エックスサーバーの場合、パスは以下の形式：

```
/home/（FTPユーザー名）/（ドメイン名）/public_html/
```

例：ユーザー名が `example`、ドメインが `example.com` の場合
```
/home/example/example.com/public_html/
```

---

## 動作確認

Secrets登録後、mainブランチに何かpushすると自動でデプロイが走る。
GitHubの **Actions** タブで進捗・エラーを確認できる。
