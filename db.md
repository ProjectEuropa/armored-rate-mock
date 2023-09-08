| テーブル名        | カラム名         | データ型        | 説明                                       | その他         |
|-------------------|------------------|-----------------|--------------------------------------------|----------------|
| **users**         | id               | Integer         | ユーザーID                                 | 主キー          |
|                   | name             | String          | ユーザー名                                 |                |
|                   | email            | String          | メールアドレス                             |                |
|                   | password         | String          | パスワード（ハッシュ）                     |                |
|                   | created_at       | Timestamp       | 作成日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **admin_users**   | id               | Integer         | 管理者ID                                   | 主キー          |
|                   | user_id          | Integer         | ユーザーID                                 | 外部キー        |
|                   | created_at       | Timestamp       | 作成日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **online_users**  | id               | Integer         | オンラインID                               | 主キー          |
|                   | user_id          | Integer         | ユーザーID                                 | 外部キー        |
|                   | last_active_at   | Timestamp       | 最後のアクティブ時間                       |                |
| **live_matches**  | id               | Integer         | ライブ対戦ID                               | 主キー          |
|                   | room_id          | Integer         | 部屋ID                                     | 外部キー        |
|                   | status           | String          | 対戦状態（例: 'in_progress', 'completed'） |                |
|                   | created_at       | Timestamp       | 対戦開始時間                               |                |
|                   | updated_at       | Timestamp       | 最後の更新時間                             |                |
|                   | winner_id        | Integer         | 勝者ID                                     | 外部キー（Nullable）|
| **ratings**       | id               | Integer         | レーティングID                             | 主キー          |
|                   | user_id          | Integer         | ユーザーID                                 | 外部キー        |
|                   | season_id        | Integer         | シーズンID                                 | 外部キー        |
|                   | rating           | Integer         | 現在のレーティング                         |                |
|                   | created_at       | Timestamp       | 作成日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **seasons**       | id               | Integer         | シーズンID                                 | 主キー          |
|                   | name             | String          | シーズン名                                 |                |
|                   | start_date       | Date            | 開始日                                     |                |
|                   | end_date         | Date            | 終了日                                     |                |
|                   | created_at       | Timestamp       | 作成日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **matches**       | id               | Integer         | 対戦ID                                     | 主キー          |
|                   | player1_id       | Integer         | プレイヤー1のID                            | 外部キー        |
|                   | player2_id       | Integer         | プレイヤー2のID                            | 外部キー        |
|                   | winner_id        | Integer         | 勝者のID                                   | 外部キー        |
|                   | created_at       | Timestamp       | 対戦日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **rooms**         | id               | Integer         | 部屋ID                                     | 主キー          |
|                   | name             | String          | 部屋名                                     |                |
|                   | host_id          | Integer         | ホストのID                                 | 外部キー        |
|                   | status           | String          | 部屋の状態                                 |                |
|                   | tier_limit       | String          | ティア制限                                 |                |
|                   | created_at       | Timestamp       | 作成日時                                   |                |
|                   | updated_at       | Timestamp       | 更新日時                                   |                |
| **room_members**  | id               | Integer         | メンバーID                                 | 主キー          |
|                   | room_id          | Integer         | 部屋ID                                     | 外部キー        |
|                   | user_id          | Integer         | ユーザーID                                 | 外部キー        |
|                   | joined_at        | Timestamp       | 参加日時                                   |                |
