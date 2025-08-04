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
