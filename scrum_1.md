# 由 scrum_1 組員40223102所寫的專案一考試報告
在模數和傳動比给定的情况下，小齒輪的齒數 越小，大齒輪齒數 以及齒數和( + )也越小，齒輪機構的中心距、尺寸和重量也减小。
因此設計時希望把 取得盡可能小。
  但是對漸開線標準齒輪，其最少齒數是有限制的。如下公式所示:
2/(sin壓力角)^2=過切最小齒數
  所以當壓力角為20度時，代入公式  2/(sin 20)^2
2/(sin 20)/(sin 20)=17
即壓力角為20度時齒輪的最小齒數為17。
  在應用以上的原理，並用程式繪製出互相嚙合的齒輪。


  首先下載2015scrum解壓縮後，複製到v槽裡面，用leo開啟cp_project，進入index編輯。如下圖所示:

![](https://copy.com/bjyqrip9R1MHNFWZ)
midx=400在x軸方向移動400。

![](https://copy.com/GWxK8i71Vtx8o46J)
紅框的部分midx=400+3*rp，原本設定midx=400+ra了時後圖示會出現干涉，後來將原本的400+ra改為400+3*rp(節圓半徑)，因為大齒輪直徑為小齒輪的兩倍，故我們尺寸為這樣設定。

![](https://copy.com/cBwDGk8uOaucHWhR)
更改完成後，可以看得出來大小齒輪已嚙合。

# 由 scrum_1 組員40223104所寫的專案一考試報告
這次作業我負責的是利用Creo繪製3D齒輪，要在leo當中設定參數，然後讓程式計算齒數、模數、壓力角等數據。
![](https://copy.com/rHurBZ9gs1DaLxiF)
↑定義所要設定的變數名稱，例如module是模數的名稱。

1111111111111111111111111111111111111
↑除了設定名稱之外，還要做好其他的定義，要讓每個定義的變數都有個對應的名稱。

↓完成程式編寫後上傳到近端，並在creo的頁面上輸入網址。
111111111111111111111111111111111111111

輸入之後就會開始計算，並呈現出計算後的齒輪模樣。
111111111111111111111111

一開始我並不知道該怎麼完成分配到的任務，還好有組長的教導才能順利的完成這次的作業。



# 由 scrum_1 組員40223102所寫的七齒輪嚙合考試報告
這次我負責的地方是七個齒輪嚙合中，第二齒的部分。
首先開啟ger.leo →進入index 
在第一齒輪下方打上
第2齒數:cinput type=text name=N1和br /
如下圖所示↓
![](https://copy.com/SXZps2O71dTmOTpu)

接下來進入 mygeartest2
如圖所示，輸入第二齒所要的顏色跟數據 
Gear(midx, midy, rp, n=20, pa=20, color="black"):
第2齒輪齒數
n_g2 = '''+str(N1)+'''
![](https://copy.com/bU9yiSYZ2PVSPlTh)

寫出計算第二齒輪的節圓半徑
rp_g2 = m*n_g2/2
第2齒輪的圓心座標
x_g2 = x_g1 + rp_g1 + rp_g2
y_g2 = y_g1
x=第一齒的圓心座標+第一齒的節圓半徑+第二齒的節圓半徑
y=y軸不變所以跟齒輪一一樣
![](https://copy.com/Dfw4ng8rtaRki14R)

如下圖所示，接下來在第一齒角度後面輸入
 將第2齒輪逆時鐘轉 90 度之後, 再多轉一齒, 以便與第1齒輪進行囓合
ctx.save()
 translate to the origin of second gear
ctx.translate(x_g2, y_g2)
 rotate to engage
ctx.rotate(-pi/2-pi/n_g2)
 put it back
ctx.translate(-x_g2, -y_g2)
spur.Spur(ctx).Gear(x_g2, y_g2, rp_g2, n_g2, pa, "black")
ctx.restore()
![](https://copy.com/vdGQ9ucqYNFkOCF0)

以下就是完成的七齒輪嚙合圖!
![](https://copy.com/VFQKXMWXznSOZMxV)