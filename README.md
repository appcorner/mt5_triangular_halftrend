# stupid_bot

## Triangular HalfTrede MT5 (python)

open forex order for Triangular Arbitrage

## disclaimer (ข้อจำกัดความรับผิดชอบ)
- ผู้พัฒนาไม่สามารถรับผิดชอบ ความเสียหายที่เกิดจาก การใช้งาน บัค error หรือ อื่นๆ ได้ ผู้ใช้โปรแกรมต้องยอมรับความเสี่ยงที่เกิดขึ้นเอง โดย ทดลอง ทดสอบ ให้มั่นใจก่อนนำไปใช้ในการลงทุน
- ผู้พัฒนาไม่อนุญาติให้นำโปรแกรมไปแสวงหาผลประโยชน์จากบุคคลอื่น หากทราบ จะหยุดการพัฒนาและเผยแพร่โปรแกรมโดยทันที

## V1.0
- เริ่มการทดลอง Triangular Arbitrage

## config.ini (rename จาก config_sample.ini)

    [mt5]
    login = 
    password = 
    server = 
    ;# ระบุ path ของ terminal.exe ของ MT5 ที่ติดตั้งไว้
    ; path = D:\mt5_terminal\FBS_02\terminal64.exe

    [line]
    notify_token = 

    [app_config]
    ;# สามารถข้ามส่วนนี้ไปได้ โดยใช้ค่าที่กำหนดให้ได้เลย
    ;TIME_SHIFT = 5
    ;# level การบันทึก log file ทั่วไปให้ใช้แบบ INFO
    ;# CRITICAL 50, ERROR 40, WARNING 30, INFO 20, DEBUG 10, NOTSET 0
    ;LOG_LEVEL = 10
    ;# กำหนดรอบเวลาในแสดง update balancec และ trailing stop
    ;# 0=timeframe, 1=10, 2=15, 3=20, 4=30, 5=60, 6=timeframe/2 
    ;UB_TIMER_MODE = 1

    [setting]
    ;# 1m, 3m, 5m, 15m, 30m, 1h, 2h, 4h, 6h, 12h, 1d
    timeframe = 5m
    signal_index = -2
    magic_number = 999111

    symbol = USDJPY
    triangle_symbols = EURUSD, EURJPY
    lot = 0.02
    deviation = 20


    atrlen = 100
    amplitude = 3
    channel_deviation = 2

    ;# check สัญญาณ macd ก่อนเปิด order default = on
    confirm_macd = off

    ;# เพิ่มการเปิด order ด้วยสัญญาน macd cross (MACD ตัด MACDs) default = off
    macd_cross = off

    ;# เปิด order เมื่อเกิดสัญญาน จากทั้งกลุ่ม default = off
    triangular_signal = off

    martingale_mode = on
    martingale_factor = 1.0
    martingale_max = 16
    ;# ถ้า martingale_factor > 1.0 จะเป็นการเพิ่ม lot ตามเทคนิค martingale (ทวีคูณ)
    ;martingale_factor = 2.0
    ;martingale_max = 8

    auto_tpsl = off
    sl = 0
    tp = 0
    ;# สามารถกำหนดค่าเป็นเปอร์เซ็นต์ได้
    ;sl = 0.7%
    ;tp = 1.2%

    ;# ปิด order เมื่อ profit ของกลุ่ม (USDJPY+EURUSD+EURJPY) ที่เปิด Order พร้อมกัน มากกว่า tp_amount
    tp_amount = 6

    trailing_stop = off