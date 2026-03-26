# morning-paper データディレクトリ

パーソナル朝刊スキル (`~/.claude/skills/morning-paper/`) のデータ保存先。

## 構造

```
morning-paper/
├── data/                  # 日次の取材ログ・配信記録
│   └── 2026-03-26.json    # 取材結果 + 採用/不採用 + 配信済み記事
├── feedback/              # ユーザーフィードバックの蓄積
│   └── 2026-03-26.json    # Notionから取得したフィードバック
└── sources.yaml           # 情報ソース設定（スキルから参照）
```

## data/*.json の構造

各日付のファイルに、全取材記事と編集判断を記録:

```json
{
  "date": "2026-03-26",
  "articles": [
    {
      "title": "...",
      "url": "...",
      "category": "tech",
      "source": "Zenn",
      "summary": "...",
      "selected": true,
      "size": "large",
      "reason_selected": "Angular開発者に直結する重要アップデート"
    }
  ],
  "notion_page_id": "..."
}
```

## feedback/*.json の構造

```json
{
  "date": "2026-03-26",
  "ratings": {
    "overall": 4,
    "most_useful": ["記事タイトル1", "記事タイトル2"],
    "least_useful": ["記事タイトル3"],
    "comments": "エンタメ枠もう少し多めが嬉しい"
  }
}
```
