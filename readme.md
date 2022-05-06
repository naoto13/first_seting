
# 行うこと

## zshのインストール

```sh
$ brew install zsh
# ログインシェルを変更します。
$ chsh -s /usr/local/bin/zsh
# 確認
TEST-USER% echo $SHELL
```

## oh-my-zshのインストール
zshのフレームワーク。さまざまなプラグインを使用可能に

```sh
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### テーマ変更

```
$ vim ~/.zshrc
```

以下を変更
~/.zshrc
```
ZSH_THEME="candy"
```

変更後は再読み込み
```
$ source ~/.zshrc
```

以下同様に行う


### シンタックスハイライト

~/.zshrc
```
# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
# plugins=(git)
# シンタックスハイライト
plugins=(git zsh-syntax-highlighting)
```


```sh
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### 補完機能
```sh
$ git clone https://github.com/zsh-users/zsh-completions ~/.oh-my-zsh/custom/plugins/zsh-completions
```

~/.zshrc
```
plugins=(git zsh-syntax-highlighting zsh-completions)

# zsh-completionsの設定
autoload -U compinit && compinit -u
```

### zsh-autosuggestions 予測変換

```
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

~/.zshrc
```
# zsh-autosuggestions 予測変換
plugins=(zsh-autosuggestions)
```

### その他

```
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

alias vi='vim'
alias rs='rails s'
alias rc='rails c'
alias code='cd ~/Users/naoto_yamaura_4/Desktop/code'

# 文字コードの指定
export LANG=ja_JP.UTF-8

# 日本語ファイル名を表示可能にする
setopt print_eight_bit

# cdなしでディレクトリ移動
setopt auto_cd

# cd -<tab>で以前移動したディレクトリを表示
setopt auto_pushd

# ヒストリ(履歴)を保存、数を増やす
HISTFILE=~/.zsh_history
HISTSIZE=100000
SAVEHIST=100000

# 直前と同じコマンドの場合は履歴に追加しない
setopt hist_ignore_dups

# キーバインディングをemacs風にする
bindkey -d
bindkey -e

# 補完で小文字でも大文字にマッチさせる
zstyle ':completion:*' matcher-list 'm:{a-z}={A-Z}'

```


## 参考サイト

- 初心者向け：Zshの導入(https://qiita.com/iwaseasahi/items/a2b00b65ebd06785b443)
- [Zshメモ : zsh-autosuggestionsで履歴からコマンド候補を表示](https://wonderwall.hatenablog.com/entry/2016/06/25/222803)



## 入れるアプリ
- Slack
- Brave
- Chrome
- Spectacle(画面分割:https://www.spectacleapp.com/)
