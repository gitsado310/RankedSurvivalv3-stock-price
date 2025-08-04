<!DOCTYPE html>
<html lang = "ja">
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
          本題のプログラムの説明
        </h2>
      <p>
        まずプログラムの説明から行きます<br>
        皆さんがいじるのはstart_jstとend_jstです<br>
        コメントには書いてありますが<br>
        時刻を設定します<br>
        秒単位で設定できます<br>
        というかgithubにスクリプトを埋め込められなかったので(Node.jsは謎にできなかった)<br>
        ということで下のプログラムを普通の文字ですが普通にコピペしてね
      </p>
        <h2>
        プログラム・そのままコピペして<a href= "paiza.io" target="_blank" >paiza.io</a>に貼ってください
        </h2>
    <p>

import math<br>
import datetime<br><br>

def f(x):<br>
    return (<br>
        5 * math.cos(x / math.sqrt(3500)) +<br>
        math.cos(3 * x) +<br>
        (2 + math.sin(x / math.sqrt(500))) *<br>
        (math.cos(2 * x) - math.cos(x / 10) + math.sin(math.sqrt(2) * x))<br>
    )<br><br>

def g(x):<br>
    return math.floor(30000 + 5000 * f(x / 1000000))<br><br>

start_jst = datetime.datetime(2025, 8, 4, 0, 0, 0) #初めの年,月,日,時,分,秒<br>
start_utc = start_jst - datetime.timedelta(hours=9)<br><br>

end_jst = datetime.datetime(2025, 8, 4, 23, 59, 59) #初めの年,月,日,時,分,秒<br>
end_utc = end_jst - datetime.timedelta(hours=9)<br><br>

epoch = datetime.datetime(1970, 1, 1)<br><br>

start_ms = int((start_utc - epoch).total_seconds() * 1000)<br>
end_ms = int((end_utc - epoch).total_seconds() * 1000)<br><br>

step = 1000<br><br>

max_price = None<br>
min_price = None<br>
max_time = None<br>
min_time = None<br><br>

for x in range(start_ms, end_ms + 1, step):<br>
    price = g(x)<br>
    if max_price is None or price > max_price:<br>
        max_price = price<br>
        max_time = x<br>
    if min_price is None or price < min_price:<br>
        min_price = price<br>
        min_time = x<br><br>

def ms_to_jst(ms):<br>
    utc_time = epoch + datetime.timedelta(milliseconds=ms)<br>
    jst_time = utc_time + datetime.timedelta(hours=9)<br>
    return jst_time<br><br>

print(f"最高値: {max_price} at {ms_to_jst(max_time)} JST")<br>
print(f"最安値: {min_price} at {ms_to_jst(min_time)} JST")<br><br>
    </p>
    </body>
</html>
