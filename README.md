# python3 の正規表現メモ (作成中）

|アンカー|説明|正規表現|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
^|行または文字列の先頭にマッチ|^s|start|end|
$|行または文字列の末尾にマッチ|d$|end|start|
\b|区切り文字（スペース、アンダーバー以外の記号）にマッチ|\bcat\b|cat|concatinate|
\B|区切り文字（スペース、アンダーバー以外の記号）以外にマッチ|\Bcat\B|concatinate|cat|

|文字クラス|説明|正規表現|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
[ ]|[ ]の一文字にマッチ|[abc]|a, b, c|e|
[ - ]|範囲内の一文字にマッチ|[a-c]|a, b, c|e|
[^ ]|[ ]の一文字以外にマッチ|[^a-c]|e|a, b, c|
