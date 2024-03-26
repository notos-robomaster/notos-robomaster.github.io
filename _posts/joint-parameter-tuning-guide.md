---
layout: post
title:  "joint parameter tuning guide!"
date:   2024-03-26 18:13:26 +0000
categories: jekyll update
---

# 聯調指南

---

## **notice**

**開機先開整車電源，再開miniPC供電**

**關機先關miniPC，再斷miniPC供電，再關整車電源，直接關整車小心miniPC系統崩潰**

**斷miniPC供電最好斷開穩壓板，不然穩壓板一直在運行**

---

## 視覺調參

### 上場準備
1. 相機線，串口線，電源線是否插穩
2. 調到合適的相機物理光圈，焦距
3. Terminal是否打開串口
```bash
sudo chmod 777 /dev/ttyUSB0
```
4. WatchDog是否打開
5. 相機代碼曝光參數，可以正確識別數字
6. build不了，調整系統時間
```bash
sudo date -s "2022-07-18 10:28"
```
7. 裝甲板顏色
8. 確認射速是否正確
9. 是否打開卡爾曼和接收電控數據
10. 串口收發是否成功
11. 關閉所有debug選項，關閉圖形界面，減少系統開銷

### 平時調參
1. 上場準備1, 2, 3, 5, 6, 7
2. 關閉卡爾曼
3. 調整GUN_CAM_DISTANCE_X和GUN_CAM_DISTANCE_Y，找一個靜止裝甲板為目標，放在正前方2-4米，關閉重力補償，啟動自描，連續發射子彈，調整參數，直致pitch, yaw為正中，yaw有一點重力可忽略 `注意pitch, yaw需要歸0`
4. 調整setBulletSpeed，把裝甲板放2-6米靜止，打開重力補償，啟動自描，連續發射子彈，調整參數，直致射中裝甲板，再重複把裝甲板放不同位置測試 `注意pitch, yaw需要歸0`
5. 打開卡爾曼，被擊打車關閉小陀螺，勻速平移，調整車的卡爾曼參數，直致能正確擊打

### 使用建議
1. 6米內為正常識別範圍
2. 自描看被擊打車越久，預測越准。根據剩餘子彈評估是否應該多看一下再打
3. 距離近更易打中
4. 卡爾曼看效果決定是否打開

## 電控問題

### 平時調參
1. 先看能否收到視覺數據，數據是否正常
2. 調PID；P越大速度越快，力越小；I為補償，pitch, yaw更好歸0；D為消抖
3. pitch, yaw的比例系數有合適值，越大容易瘋
4. pitch, yaw能穩住不抖迅速歸0
5. miniPC能否接收到32數據，能否利用收到的數據自動做出選擇
6. 能否自動發彈

## 機械問題

### 平時調參
1. pitch調不穩，機械是否有重力補償 `理想應為雲台無力時水平靜止，pitch有一點點自然向下的角度為正常`
2. 是否有線擋住摩打或miniPC風扇運行
3. 小心上場彈丸打到相機或miniPC接口，機械要做好保護


You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/