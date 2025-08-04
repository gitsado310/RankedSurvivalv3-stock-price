<!DOCTYPE html>
<html lang = "ja">
    <head>
        <title>サバイバルv3株価予想/Bloxd</title>
        <meta charset="UTF-8">
    </head>
    <body>
        <h1>
           サバイバルv3株価予想
        </h1>
        <h2>
          あいさつ
        </h2>
        <p>
            朝か昼か夜かわからないけどこんにちはどうもいつものsadoです<br>
        </p>
        <h2>
          概要
        </h2>
        <p>
            今回はGithubを使ってサバイバルv3の株価プログラムの最安値と最高値を予測できるプログラムをつくりました。ぜひ見ていってください
        </p>
        <h2>
          説明
        </h2>
        <p>
          サバイバルv3とは何なのか 株価とは何かについて説明します 知っている方は飛ばしてもよろしいです<br>
          ・<a href= "Bloxd.io" target="_blank" >Bloxd.io</a>というゲームにはサバイバル(英:Survival)というゲームモードがあります。そこにはサバイバルでもちろん遊べるので<br>
          　すが、サバイバルでサーバーを作ることができます。その中に<strong>サバイバルv3</strong>というサーバーがあります。<br>
          ここまででbloxd.ioとサバイバルv3のサーバーについて説明しました。次に株価について説明します<br><br>
          ・現実の株とは少し違く、資金調達の面などはなく、金額が変化して売る時などどれだけ有利に進められるかなどというやりこ<br>
           　み要素の面で追加されます。<br>
           <font size="1">(自分の思い込み 鯖主(knkt_yuzu)がどういう風に思っているはわからないよ)</font><br>
          ・株価というのはランダムではなくsin波などの波の合成で作られているのでぶっちゃけ予想することが可能となります。
          ・それを夜に頑張ってプログラム書きました<br><br>
          説明が終わりました<br>
          次にプログラムのコードについてです。<br>
          ・予想してみたかったので一回作ってみたいと思い作って公開しました。<br>
          ・使用言語はPythonです。<br>
          ・ブラウザでも動くようにしてあるのでコードをコピーし下のサイトを参照して使ってみてください。<br>
          <a href= "paiza.io" target="_blank" >paiza.io</a><br>
          ・そのサイトの使い方ですが<b>右上</b>を参照してそこに緑のボタンがあります。そのプログラミング言語(javaなど)が書い<br>
          　てあるボタンを押します。<br>
          ・そうするとプログラミング言語一覧が出てくるので<strong>Python3</strong>のボタンを押します。<br>
          ・そしてプログラムをコピーします(ctrl + c)そして<a href= "paiza.io" target="_blank" >paiza.io</a>のプログラムを書くとこにペースト(ctrl + v)してください。
        </p>
        <h2>
          本題のプログラム
        </h2>
      <p>
        まずプログラムの説明から行きます<br>
        皆さんがいじるのはstart_jstとend_jstです<br>
        コメントには書いてありますが<br>
        時刻を設定します<br>
        秒単位で設定できます<br>
      </p>
<script type="text/javascript">

import math
import datetime

def f(x):
    return (
        5 * math.cos(x / math.sqrt(3500)) +
        math.cos(3 * x) +
        (2 + math.sin(x / math.sqrt(500))) *
        (math.cos(2 * x) - math.cos(x / 10) + math.sin(math.sqrt(2) * x))
    )

def g(x):
    return math.floor(30000 + 5000 * f(x / 1000000))

start_jst = datetime.datetime(2025, 8, 4, 0, 0, 0)   # 初めの時刻 年,月,日,時,分,秒 まで指定できる
start_utc = start_jst - datetime.timedelta(hours=9)

end_jst = datetime.datetime(2025, 8, 4, 23, 59, 59)  # 初めの時刻 年,月,日,時,分,秒 まで指定できる
end_utc = end_jst - datetime.timedelta(hours=9)

epoch = datetime.datetime(1970, 1, 1)

start_ms = int((start_utc - epoch).total_seconds() * 1000)
end_ms = int((end_utc - epoch).total_seconds() * 1000)

step = 1000

max_price = None
min_price = None
max_time = None
min_time = None

for x in range(start_ms, end_ms + 1, step):
    price = g(x)
    if max_price is None or price > max_price:
        max_price = price
        max_time = x
    if min_price is None or price < min_price:
        min_price = price
        min_time = x

def ms_to_jst(ms):
    utc_time = epoch + datetime.timedelta(milliseconds=ms)
    jst_time = utc_time + datetime.timedelta(hours=9)
    return jst_time

print(f"最高値: {max_price} at {ms_to_jst(max_time)} JST")
print(f"最安値: {min_price} at {ms_to_jst(min_time)} JST")

</script>
