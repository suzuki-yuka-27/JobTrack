# JobTrack

転職活動の記録を一元管理するサービス

## 開発背景
自身の転職活動において、複数の求人媒体や転職エージェントを利用していたため、応募企業や面接予定、選考状況などの情報がさまざまな場所に分散してしまい、全体の把握や整理に多くの時間を要していました。
また、面接内容や振り返りを記録する場所も統一されておらず、次回の面接に向けた改善点を十分に活かせないこともありました。
そこで、応募企業の管理から選考状況の把握、面接の振り返りまでを一元管理できるサービスがあれば、転職活動をより効率的かつ戦略的に進められるのではないかと考え、本アプリを開発しようと考えました。


## 機能一覧
- マイページ
- ログイン機能
- 転職活動管理機能
- 企業管理機能
- 面接管理機能
- タスク管理機能

## 使用技術
- PHP 
- Laravel 
- Tailwind CSS
- PostgreSQL
- OpenAI API
- Docker

## テーブル定義

### users
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | ユーザーID |
| name | varchar(255) | ユーザー名 |
| email | varchar(255) | メールアドレス |
| password | varchar(255) | パスワード |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

### social_accounts
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | ソーシャルアカウントID |
| user_id | bigint | ユーザーID |
| provider | int | ソーシャルアカウントの種類 |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

### job_applications
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | 転職記録ID |
| user_id | bigint | ユーザーID |
| company_id | bigint | 企業記録ID |
| status | int | 転職ステータス |
| interest_level | int | 志望度 |
| phase | int | 面接フェーズ |
| interview_date | datetime | 面接日 |
| application_source | varchar(100) | 応募媒体 |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

### companies
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | 企業ID |
| name | varchar(100) | 企業名 |
| company_url | varchar(255) | 企業URL |
| interview_times | int | 面接回数 |
| reference_url | text | 参考資料 |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

### interviews
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | 面接記録ID |
| job_application_id | bigint | 転職記録ID |
| questions | text | 質問 |
| rating | int | 評価 |
| memo| text | 振り返りメモ |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

### tasks
| カラム名 | 型 | 説明 |
|----------|----|------|
| id | bigint | タスクID |
| job_application_id | bigint | 転職記録ID |
| name | varchar(100) | タスク名 |
| content | text | タスク内容 |
| status | int | ステータス |
| due_date | date | 締切日 |
| created_at | timestamp | 作成日時 |
| updated_at | timestamp | 更新日時 |

## ER図
<img width="500" height="700" alt="Job_Track" src="https://github.com/user-attachments/assets/84fe867a-4116-40bb-ba60-5aa1887f0328" />

## 画面遷移図
<img width="600" height="700" alt="Job Track" src="https://github.com/user-attachments/assets/9f98f73b-399c-4261-9550-7a662c7e2b67" />

[Figmaで開く](https://www.figma.com/board/Jitq9INvGLKXGo7eVglpLU/Job-Track?node-id=9-1307&t=jz9xCDBzhTAIdDHs-0)

## ワイヤーフレーム

## 工夫した点
