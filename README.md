# python3 の正規表現メモ (作成中）

|アンカー|説明|使用例|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
^|行または文字列の先頭にマッチ|^s|start|end|
$|行または文字列の末尾にマッチ|d$|end|start|
\b|区切り文字（スペース、アンダースコア以外の記号）にマッチ|\bcat\b|cat|concatinate|
\B|区切り文字（スペース、アンダースコア以外の記号）以外にマッチ|\Bcat\B|concatinate|cat|

|文字クラス|説明|使用例|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
[ ]|[ ]の一文字にマッチ|[abc]|a, b, c|e|
[ - ]|範囲内の一文字にマッチ|[a-c]|a, b, c|e|
[^ ]|[ ]の一文字以外にマッチ|[^a-c]|e|a, b, c|
.|任意の一文字にマッチ|f.x|fox|fx|
\t|タブにマッチ|\t|タブ|スペース|
\r||||
\d|[0-9]と同じ|\d|0|a|
\D|[^0-9]と同じ|\D|a|0|
\w|[a-zA-Z0-9\_]と同じ|\w\w\w|3DS|3.14|
\W|[^a-zA-Z0-9\_]と同じ|\W\W|.+|4$|
\s|[ \t\r\n\v]と同じ|\s|タブ、スペース|a|
\S|[^ \t\r\n\v]と同じ|\S|0|タブ、スペース|


|繰り返し|説明|使用例|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
\*|0回以上の繰り返し|ca\*t|ct, cat, caat||
+|1回以上の繰り返し|ca+t|cat, caat|ct|
?|0回または1回にマッチ|https?|http, https|
\*?|0回以上の繰り返し（最短）|ca\*?t|caaat, cat, ct||
+?|1回以上の繰り返し（最短）|ca+?t|caaat, cat|ct|
??|0回または1回にマッチ（最短）|https??|https, http||
{m}|m回の繰り返し|a{3}|aaa|aab|
{m,n}|m回以上n回以下の繰り返し|a{2,4}|aa, aaa, aaaa|a|

|( )表現|説明|使用例|マッチする|マッチしない|
|:---|:---|:---|:---|:---|
(...)|()内にマッチした文字列をキャプチャ. \1, \2 ... で後方参照|([ab])\1|aa, bb|ab|
(?:...)|()内にマッチした文字列をキャプチャしない|(?:[ab])|a, b||
(?=...)|肯定先読み|Tom(?='s)|Tom's|Tom|
(?!...)|否定先読み|file(?!\.bat)||file.txt|file.bat
(?<=...)|肯定後読み
(?<!...)|否定後読み
(?P...)|グループ名を指定
