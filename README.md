# repos_Dec16

##git init
現在のフォルダをリポジトリとする。

##git remote add、git fetch
remoteのリポジトリを追加して、リモートリポジトリの状態を取得する（作業環境には反映しない）


##git clone
既存のリポジトリの複製を作る


## git merge
ブランチのマージを行う。
引数を省略した場合はアップストリームとして指定されたブランチとマージする
(すみません、良く分からない・・・)

## git merge --no-ff
ブランチを`merge`したときに、必ずマージコミットを作る。

## git merge --ff-only
ふたつのブランチが`fast-forward` の関係にないときは処理を行わない。


## git commit --amend
一旦コミットしてからちょっとした修正を入れた場合に、この修正も元のコミットに含めてしまいたいことがある
(細かい修正が漏れていたのに、あとから気づいたような場合)
そのような場合に、このコマンドを使用する。

 使用例
 # aというファイルを追加し、一旦コミットする
 $ git commit -m "add a file"

 # その後、aに修正を入れる
 $ git status
 Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   a # <- aが修正されている

 $ git add . # 変更をインデックスに登録
 $ git commit --amend --no-edit # 登録されたインデックスを直前のコミットにまとめる 
                                # --no-editはコミットコメントは変更なし、という指定。
                                # 指定しないと新しいコメントを打つためにエディタが上がる
 $ git status
 On branch master
 nothing to commit, working directory clean

## git commit
変更点をリポジトリーに反映（事前にaddが必要）

## git checkout -b fix/42
ブランチの作成と新しいブランチへの切り替えを同時に行う。

次のふたつのコマンドの実行と同じ。

```
$ git branch fix/42
$ git checkout fix/42
```

## git rebase -i
 iはinteractiveのi。
 --interactiveでも同じ指定になる。
 rebaseといっても普通のrebaseと異なり、他ブランチにrebaseするわけではなく、
 ローカルのコミット履歴の編集をインタラクティブに行う。
 	
 
## git commit -a
 変更のあったファイルすべてをコミットする

## git reset --hard master
ローカルリポジトリをリモートのmaster に合わせる。

## git cherry-pick
他のブランチの任意のコミットを現在のブランチに適用します。

使用方法
git cherry-pick 82d796dbc484316fc0f6d9ad94d05027b1adbd2a