---
title: 語音和圖像壓縮的計算機科學原理
---

> 給你一個英語的語句，比如
"London bridge is falling down"，
把它完全倒裝過來，
"down falling is bridge London"，
如何不使用額外的存儲空間完成這個倒裝過程？

首先會想到把這個句子切割成一個個單詞，然後把它們存到一個數組裏
把這個數組順序存入，逆序取出來就可以完成語句倒裝的問題。
但是，這種算法要**額外地使用存儲空間**。

**用計算機解決這個問題的關鍵，恰恰是要把單詞先搞亂，再規整起來。**

第一步，先將整個句子看成是一個完整的字符串，以字母為單位頭尾對調，這樣上麵的句子就變成了下麵這樣一個亂七八糟的字符串：
“nwod gnillaf si egdirb nodnoL”

第二步，把用空格分割的每一個字串以字母為單位，頭尾對調。比如第一個字串是nwod，頭尾對調後是down，也就是原來句子中的最後一個單詞。第二個字串是gnillaf，字母頭尾對調後是falling，原來句子中倒數第二個單詞。這樣一個個地做，直到最後一個字串裏的字母對調完畢。這樣就得到了下麵的倒裝句子：
“down falling is bridge London.”

於平時的思維定式，特別是不敢把整個句子變成無意義的字串，很多人想不到先要把整個句子變得無意義，才能得到的後麵有意義的單詞。

## 語音和圖像處理的基礎

第一步，將有意義的單詞變成無意義的字串，看似把問題搞亂了，但其實完成了兩件事，
一個是把文字信息置換了位置，另一個是記錄了每一個單詞的長度，保留了下來，這就避免了那種試圖將整個單詞搬家的算法，很難搞清楚每個單詞長度的缺陷。這種方法能夠工作，很重要的一個原因是，它的每一步操作，其實都保證了信息不丟失，雖然那些處於中間狀態的信息你未必看得懂。

這種先把看得懂的信息，變成你看不懂，但是沒有任何損失的中間信息的做法，是今天語音和圖像處理的基礎。如果我們把人的語音錄下來，顯示在螢幕上，它是一段聲波的波形，雖然你看不出它是什麼音，但是至少能看出波動；對於圖像，則更加直觀了，一張風景畫就是風景畫，一張肖像就是肖像。

## 語音和圖像的壓縮

能否將語音和圖像壓縮一下? 無論是把平滑的語音抽掉一些樣點，或者把圖像去掉一些像素，語音的清晰度，或者圖像的分辨率都損失很大。那麼在語音和圖像壓縮中，科學家們是怎麼設計算法的呢？這就和上述算法有相似之處了。

第一步，先把語音或者圖像從直觀的信號，變成人根本看不懂的頻率信號。
第二步，根據壓縮的比例，把高頻的信號過濾掉，隻保留低頻的即可。當播放語音，或者顯示圖片時，再從頻率信號恢複為語音波形，或者圖像即可。

你如果有攝影經驗，可能能體會原圖像文件Raw File，和壓縮的JPEG文件的細微差別。簡單地講，原圖是一個像素一個像素存儲的，而JPEG文件其實存儲的是圖像的頻率，你可以認為是一大片一大片存儲的，因此像藍天、白雲、大海這樣變化不是很多的色塊，壓縮的JPEG文件基本上把它們變成一種顔色了。通常JPEG文件壓縮10倍，你肉眼看不出什麼區別。類似地，語音壓縮十倍，你基本上也聽不出區別。

講到語音和圖像的壓縮。它們的共同點在於，計算機在處理信息時，通常要把信息變成另一種形式才好處理，而那種形式，並非是人所熟悉的。因此，搞計算機和信息處理，一定要走出人日常的認知。

參考：谷歌方法論
