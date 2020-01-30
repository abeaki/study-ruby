# Rubyの学習メモ

## セットアップ

- Rubyのバージョン管理ツールをインストール

```bash
brew install rbenv
```

- パスの設定と初期化処理

```bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
```

- ターミナルを再度立ち上げ直して、以下のコマンドでバージョンが表示されるか確認

```bash
rbenv -v
```

- バージョンを指定してRubyをインストール

```bash
rbenv install x.x.x
```

- システム全体で使用するRubyのバージョンを指定

```bash
rbenv global x.x.x
```

- システム全体ではなくプロジェクト毎に設定する場合は以下のコマンド

```bash
rbenv local x.x.x
```

- 利用しているバージョンの確認

```bash
ruby -v
which ruby
```

## RubyGems

- Rubyのパッケージ管理ツール
- Rubyに同梱されている

### アップデート

```bash
gem update --system
```

### バージョン確認

```bash
gem -v
```

### インストール済みのgemの確認

```bash
gem list
```

## Bundler

- プロジェクト毎に利用するgemを管理するためのツール
- プロジェクトのディレクトリに[Gemfile]という名前のファイルを作成し、gemの名前を記載しておくとその通りにインストール、Rubyから利用することができる

### インストール

```bash
gem install bundler
```

### コマンド

- bundle install もしくは bundle
  - Gemfileに記載したgemをインストールする。
  - インストール時に「Gemfile.lock」というファイルが作成され、実際にBundlerが管理するgemのバージョンや依存関係が記録される。
- bundle exec [コマンド]
  - Bundlerが管理するgemを利用できる状態でコマンドを実行する
- bundle init
  - 初期状態のGemfileをカレントディレクトリに作成する。
- bundle update
  - Bundlerが管理するgemのバージョンをアップデートする。
