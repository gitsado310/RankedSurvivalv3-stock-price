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
