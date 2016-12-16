# repos_Dec16

#git clone
既存のリポジトリの複製を作る


## git merge
ブランチのマージを行う。
引数を省略した場合はアップストリームとして指定されたブランチとマージする
(すみません、良く分からない・・・)

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

## git rebase -i
 iはinteractiveのi。
 --interactiveでも同じ指定になる。
 インタラクティブにrebaseを行う。
 