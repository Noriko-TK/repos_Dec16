# repos_Dec16

## git commit --amend
一旦コミットしてからちょっとした修正を入れた場合に、この修正も元のコミットに含めてしまいたいことがある
(細かい修正が漏れていたのに、あとから気づいたような場合)
そのような場合に、このコマンドを使用する。

## git commit
変更点をremoteに反映（事前にaddが必要）

## git checkout -b fix/42
ブランチの作成と新しいブランチへの切り替えを同時に行う。

次のふたつのコマンドの実行と同じ。

```
$ git branch fix/42
$ git checkout fix/42
```

