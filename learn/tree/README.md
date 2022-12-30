# 決定木
- 利点
> - 可視化することができる
> - データの前処理があまり必要ない(正規化などを行わずに済む)
> - 学習の正しさの判定がしやすい
- 欠点
> - 過学習に陥りがちで汎化性能が低い
- 環境構築
```
// 決定木による分類を可視化するためのソフトウェア
$ brew install graphviz
// python でライブラリを追加する
$ pip install graphviz
```
- 流れ
```
from sklearn import tree

// max_depth は、慣習的に分類は5、回帰は1くらいがいいらしい
decision_tree = tree.DecisionTreeClassifier(max_depth=5).fit(
    independent_variables, dependent_variables)

# 「test」の説明変数を使って「my_tree_one」のモデルで予測
prediction = decision_tree.predict(test_independent_variables)
```
- 応用
  - ランダムフォレストを使うことで過学習を対策することができる。
```
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(max_depth=5).fit(
    independent_variables, dependent_variables)

prediction = model.predict(result_independent_variables)
```
- 参考
  - [scikit-learn で決定木分析 (CART 法)](https://pythondatascience.plavox.info/scikit-learn/scikit-learn%E3%81%A7%E6%B1%BA%E5%AE%9A%E6%9C%A8%E5%88%86%E6%9E%90)

