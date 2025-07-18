# Requirements Document

## Introduction

Supabaseを学習するための簡易的なTodoアプリケーションです。Next.jsフレームワークを使用し、最終的にVercelにデプロイして実際に使用できるWebアプリケーションとして構築します。このプロジェクトの主な目的は、Supabaseの基本機能（認証、データベース、リアルタイム機能）を実践的に学ぶことです。

## Requirements

### Requirement 1

**User Story:** ユーザーとして、アカウントを作成してログインできるようにしたい。そうすることで、自分専用のTodoリストを管理できる。

#### Acceptance Criteria

1. WHEN ユーザーがサインアップページにアクセス THEN システムはメールアドレスとパスワードの入力フォームを表示する
2. WHEN ユーザーが有効なメールアドレスとパスワードを入力してサインアップ THEN システムはアカウントを作成し、確認メールを送信する
3. WHEN ユーザーがログインページにアクセス THEN システムはメールアドレスとパスワードの入力フォームを表示する
4. WHEN ユーザーが正しい認証情報でログイン THEN システムはユーザーをTodoリストページにリダイレクトする
5. WHEN ユーザーがログアウトボタンをクリック THEN システムはユーザーをログアウトし、ログインページにリダイレクトする

### Requirement 2

**User Story:** ログインユーザーとして、新しいTodoアイテムを作成できるようにしたい。そうすることで、やるべきタスクを記録できる。

#### Acceptance Criteria

1. WHEN ログインユーザーがTodoリストページにアクセス THEN システムは新しいTodoを追加するための入力フォームを表示する
2. WHEN ユーザーがTodoのタイトルを入力して追加ボタンをクリック THEN システムは新しいTodoアイテムをデータベースに保存し、リストに表示する
3. WHEN Todoアイテムが作成される THEN システムは作成日時を自動的に記録する
4. IF Todoのタイトルが空の場合 THEN システムはエラーメッセージを表示し、保存を実行しない

### Requirement 3

**User Story:** ログインユーザーとして、自分のTodoアイテムの一覧を表示できるようにしたい。そうすることで、現在のタスク状況を把握できる。

#### Acceptance Criteria

1. WHEN ログインユーザーがTodoリストページにアクセス THEN システムはそのユーザーのTodoアイテムのみを表示する
2. WHEN Todoリストが表示される THEN システムは各アイテムのタイトル、作成日時、完了状態を表示する
3. WHEN 他のユーザーがTodoを追加または更新 THEN システムは現在のユーザーのリストに影響を与えない
4. WHEN Todoアイテムが存在しない場合 THEN システムは「Todoがありません」というメッセージを表示する

### Requirement 4

**User Story:** ログインユーザーとして、Todoアイテムを完了済みとしてマークできるようにしたい。そうすることで、完了したタスクを管理できる。

#### Acceptance Criteria

1. WHEN ユーザーがTodoアイテムのチェックボックスをクリック THEN システムはそのアイテムを完了済みとしてマークし、データベースを更新する
2. WHEN Todoアイテムが完了済みにマークされる THEN システムは視覚的に完了状態を示す（取り消し線など）
3. WHEN ユーザーが完了済みのTodoアイテムのチェックボックスを再度クリック THEN システムはそのアイテムを未完了状態に戻す
4. WHEN 完了状態が変更される THEN システムは変更を即座にデータベースに反映する

### Requirement 5

**User Story:** ログインユーザーとして、不要になったTodoアイテムを削除できるようにしたい。そうすることで、リストを整理できる。

#### Acceptance Criteria

1. WHEN ユーザーがTodoアイテムの削除ボタンをクリック THEN システムは削除確認ダイアログを表示する
2. WHEN ユーザーが削除を確認 THEN システムはそのアイテムをデータベースから削除し、リストから除去する
3. WHEN ユーザーが削除をキャンセル THEN システムはアイテムを削除せず、ダイアログを閉じる
4. WHEN アイテムが削除される THEN システムは削除操作を元に戻すことはできない

### Requirement 6

**User Story:** 開発者として、アプリケーションをVercelにデプロイできるようにしたい。そうすることで、実際のWebアプリケーションとして使用できる。

#### Acceptance Criteria

1. WHEN アプリケーションがVercelにデプロイされる THEN システムは本番環境で正常に動作する
2. WHEN 本番環境でアクセスされる THEN システムはSupabaseの本番データベースに接続する
3. WHEN 環境変数が設定される THEN システムは開発環境と本番環境で適切な設定を使用する
4. WHEN デプロイが完了する THEN システムはHTTPS経由でアクセス可能になる

### Requirement 7

**User Story:** ユーザーとして、レスポンシブなデザインでアプリケーションを使用できるようにしたい。そうすることで、モバイルデバイスでも快適に使用できる。

#### Acceptance Criteria

1. WHEN ユーザーがモバイルデバイスでアクセス THEN システムはモバイル向けに最適化されたレイアウトを表示する
2. WHEN ユーザーがタブレットでアクセス THEN システムはタブレット向けに適切なレイアウトを表示する
3. WHEN ユーザーがデスクトップでアクセス THEN システムはデスクトップ向けの広いレイアウトを表示する
4. WHEN 画面サイズが変更される THEN システムは適切にレイアウトを調整する
