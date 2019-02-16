![](https://img.shields.io/badge/%E7%B0%A1%E4%B8%AD%E7%BF%BB%E8%AD%AF-%E6%9D%8E%E7%AC%91%E4%BE%86-lightgrey.svg)
![](https://img.shields.io/badge/%E7%B9%81%E4%B8%AD%E7%BF%BB%E8%AD%AF-Chen%20Po%20Wei-blue.svg)

# 以太坊（Ethereum ）:下一代智慧合約和去中心化應用平臺

當中本聰在2009年1月啟動比特幣區塊鏈時，他同時向世界引入了兩種未經測試的革命性的新概念。第一種就是比特幣（bitcoin），一種去中心化的點對點的網上貨幣，在沒有任何資產擔保、內在價值或者中心發行者的情況下維持著價值。到目前為止，比特幣已經吸引了大量的公眾注意力，就政治方面而言它是一種沒有中央銀行的貨幣並且有著劇烈的價格波動。然而，中本聰的偉大試驗還有與比特幣同等重要的一部分：基於工作量證明的區塊鏈概念使得人們可以就交易順序達成共識。作為應用的比特幣可以被描述為一個先申請（first-to-file）系統：如果某人有50BTC並且同時向A和B傳送這50BTC，只有被首先被確認的交易才會生效。沒有固有方法可以決定兩筆交易哪一筆先到，這個問題阻礙了去中心化數字貨幣的發展許多年。中本聰的區塊鏈是第一個可靠的去中心化解決辦法。現在，開發者們的注意力開始迅速地轉向比特幣技術的第二部分，區塊鏈怎樣應用於貨幣以外的領域。

常被提及的應用包括使用鏈上數字資產來代表定製貨幣和金融工具（彩色幣），某種基礎物理裝置的所有權（智慧資產），如域名一樣的沒有可替代性的資產（域名幣）以及如去中心化交易所，金融衍生品，點到點賭博和鏈上身份和信譽系統等更高階的應用。另一個常被問詢的重要領域是“智慧合約”- 根據事先任意制訂的規則來自動轉移數字資產的系統。例如，一個人可能有一個儲存合約，形式為“A可以每天最多提現X個幣，B每天最多Y個，A和B一起可以隨意提取，A可以停掉B的提現權”。這種合約的符合邏輯的擴充套件就是去中心化自治組織（DAOs）-長期的包含一個組織的資產並把組織的規則編碼的智慧合約。以太坊的目標就是提供一個帶有內建的成熟的圖靈完備語言的區塊鏈，用這種語言可以建立合約來編碼任意狀態轉換功能，使用者只要簡單地用幾行程式碼來實現邏輯，就能夠建立以上提及的所有系統以及許多我們還想象不到的的其它系統。

### 歷史
 
去中心化的數字貨幣概念，正如財產登記這樣的替代應用一樣，早在幾十年以前就被提出來了。1980和1990年代的匿名電子現金協議，大部分是以喬姆盲籤技術（Chaumian blinding）為基礎的。這些電子現金協議提供具有高度隱私性的貨幣，但是這些協議都沒有流行起來，因為它們都依賴於一箇中心化的中介機構。1998年，戴偉（Wei Dai）的b-money首次引入了通過解決計算難題和去中心化共識創造貨幣的思想，但是該建議並未給出如何實現去中心化共識的具體方法。2005年，芬尼（Hal Finney）引入了“可重複使用的工作量證明機制”（reusable proofs of work）概念，它同時使用b-money的思想和Adam Back提出的計算困難的雜湊現金（Hashcash）難題來創造密碼學貨幣。但是，這種概念再次迷失於理想化，因為它依賴於可信任的計算作為後端。

因為貨幣是一個先申請應用，交易的順序至關重要，所以去中心化的貨幣需要找到實現去中心化共識的方法。比特幣以前的所有電子貨幣協議所遇到的主要障礙是，儘管對如何建立安全的拜占庭問題容錯（Byzantine-fault-tolerant）多方共識系統的研究已經歷時多年，但是上述協議只解決了問題的一半。這些協議假設系統的所有參與者是已知的，併產生如“如果有N方參與到系統中，那麼系統可以容忍N/4的惡意參與者”這樣形式的安全邊界。然而這個假設的問題在於，在匿名的情況下，系統設定的安全邊界容易遭受女巫攻擊，因為一個攻擊者可以在一臺伺服器或者僵屍網路上建立數以千計的節點，從而單方面確保擁有多數份額。

中本聰的創新是引入這樣一個理念：將一個非常簡單的基於節點的去中心化共識協議與工作量證明機制結合在一起。節點通過工作量證明機制獲得參與到系統的權利，每十分鐘將交易打包到“區塊”中，從而創建出不斷增長的區塊鏈。擁有大量算力的節點有更大的影響力，但獲得比整個網路更多的算力比建立一百萬個節點困難得多。儘管比特幣區塊鏈模型非常簡陋，但是實踐證明它已經足夠好用了，在未來五年，它將成為全世界兩百個以上的貨幣和協議的基石。

### 作為狀態轉換系統的比特幣

![](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/statetransition.png)

從技術角度講，比特幣賬本可以被認為是一個狀態轉換系統，該系統包括所有現存的比特幣所有權狀態和“狀態轉換函數”。狀態轉換函數以當前狀態和交易為輸入，輸出新的狀態。例如，在標準的銀行系統中，狀態就是一個資產負債表，一個從A賬戶向B賬戶轉賬X美元的請求是一筆交易，狀態轉換函數將從A賬戶中減去X美元，向B賬戶增加X美元。如果A賬戶的餘額小於X美元，狀態轉換函數就會返回錯誤提示。所以我們可以如下定義狀態轉換函數：

    APPLY(S,TX) > S' or ERROR

在上面提到的銀行系統中，狀態轉換函數如下：

    APPLY({ Alice: $50, Bob: $50 },"send $20 from Alice to Bob") = { Alice: $30,Bob: $70 }
 
但是：
 
    APPLY({ Alice: $50, Bob: $50 },"send $70 from Alice to Bob") = ERROR
 
比特幣系統的“狀態”是所有已經被挖出的、沒有花費的比特幣（技術上稱為“未花費的交易輸出，unspent transaction outputs 或UTXO”）的集合。每個UTXO都有一個面值和所有者（由20個位元組的本質上是密碼學公鑰的地址所定義[1]）。一筆交易包括一個或多個輸入和一個或多個輸出。每個輸入包含一個對現有UTXO的引用和由與所有者地址相對應的私鑰建立的密碼學簽名。每個輸出包含一個新的加入到狀態中的UTXO。
 
在比特幣系統中，狀態轉換函數`APPLY(S,TX)->S’`大體上可以如下定義：

1. 交易的每個輸入：
    * 如果引用的UTXO不存在於現在的狀態中（`S`），返回錯誤提示
    * 如果簽名與UTXO所有者的簽名不一致，返回錯誤提示
2.  如果所有的UTXO輸入面值總額小於所有的UTXO輸出面值總額，返回錯誤提示
3.  返回新狀態`S’`,新狀態`S’`中移除了所有的輸入UTXO，增加了所有的輸出UTXO。

第一步的第一部分防止交易的傳送者花費不存在的比特幣，第二部分防止交易的傳送者花費其他人的比特幣。第二步確保價值守恆。比特幣的支付協議如下。假設Alice想給Bob傳送11.7BTC。事實上，Alice不可能正好有11.7BTC。假設，她能得到的最小數額比特幣的方式是：6+4+2=12。所以，她可以建立一筆有3個輸入，2個輸出的交易。第一個輸出的面值是11.7BTC，所有者是Bob（Bob的比特幣地址），第二個輸出的面值是0.3BTC，所有者是Alice自己，也就是找零。

### 挖礦

![](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/block.png)

如果我們擁有可信任的中心化服務機構，狀態轉換系統可以很容易地實現，可以簡單地將上述功能準確編碼。然而，我們想把比特幣系統建成為去中心化的貨幣系統，為了確保每個人都同意交易的順序，我們需要將狀態轉換系統與一個共識系統結合起來。比特幣的去中心化共識程序要求網路中的節點不斷嘗試將交易打包成“區塊”。網路被設計為大約每十分鐘產生一個區塊，每個區塊包含一個時間戳、一個隨機數、一個對上一個區塊的引用（即雜湊）和上一區塊生成以來發生的所有交易列表。這樣隨著時間流逝就創建出了一個持續增長的區塊鏈，它不斷地更新，從而能夠代表比特幣賬本的最新狀態。

依照這個正規化，檢查一個區塊是否有效的演算法如下：

1.  檢查區塊引用的上一個區塊是否存在且有效。
2.  檢查區塊的時間戳是否晚於以前的區塊的時間戳，而且早於未來2小時[2]。
3.  檢查區塊的工作量證明是否有效。
4.  將上一個區塊的最終狀態賦於`S[0]`。
5.  假設TX是區塊的交易列表，包含n筆交易。對於屬於0……n-1的所有i,進行狀態轉換`S[i+1] = APPLY(S[i],TX[i])`。如果任何一筆交易i在狀態轉換中出錯，退出程式，返回錯誤。
6.  返回正確，狀態`S[n]`是這一區塊的最終狀態。

本質上，區塊中的每筆交易必須提供一個正確的狀態轉換，要注意的是，“狀態”並不是編碼到區塊的。它純粹只是被校驗節點記住的抽象概念，對於任意區塊都可以從創世狀態開始，按順序加上每一個區塊的每一筆交易，（妥妥地）計算出當前的狀態。另外，需要注意礦工將交易收錄進區塊的順序。如果一個區塊中有A、B兩筆交易，B花費的是A建立的UTXO，如果A在B以前，這個區塊是有效的，否則，這個區塊是無效的。

區塊驗證演算法的有趣部分是“工作量證明”概念：對每個區塊進行SHA256雜湊處理，將得到的雜湊視為長度為256位元的數值，該數值必須小於不斷動態調整的目標數值，本書寫作時目標數值大約是2^190。工作量證明的目的是使區塊的建立變得困難，從而阻止女巫攻擊者惡意重新生成區塊鏈。因為SHA256是完全不可預測的偽隨機函數，建立有效區塊的唯一方法就是簡單地不斷試錯，不斷地增加隨機數的數值，檢視新的雜湊數值是否小於目標數值。如果當前的目標數值是2^192，就意味著平均需要嘗試2^64次才能生成有效的區塊。一般而言，比特幣網路每隔2016個區塊重新設定目標數值，保證平均每十分鐘生成一個區塊。為了對礦工的計算工作進行獎勵，每一個成功生成區塊的礦工有權在區塊中包含一筆憑空發給他們自己25BTC的交易。另外，如果交易的輸入大於輸出，差額部分就作為“交易費用”付給礦工。順便提一下，對礦工的獎勵是比特幣發行的唯一機制，創世狀態中並沒有比特幣。

為了更好地理解挖礦的目的，讓我們分析比特幣網路出現惡意攻擊者時會發生什麼。因為比特幣的密碼學基礎是非常安全的，所以攻擊者會選擇攻擊沒有被密碼學直接保護的部分：交易順序。攻擊者的策略非常簡單：

1.  向賣家傳送100BTC購買商品（尤其是無需郵寄的電子商品）。
2.  等待直至商品發出。
3.  建立另一筆交易，將相同的100BTC傳送給自己的賬戶。
4.  使比特幣網路相信傳送給自己賬戶的交易是最先發出的。

一旦步驟（1）發生，幾分鐘後礦工將把這筆交易打包到區塊，假設是第270000個區塊。大約一個小時以後，在此區塊後面將會有五個區塊，每個區塊間接地指向這筆交易，從而確認這筆交易。這時賣家收到貨款，並向買家發貨。因為我們假設這是數字商品，攻擊者可以即時收到貨。現在，攻擊者建立另一筆交易，將相同的100BTC傳送到自己的賬戶。如果攻擊者只是向全網廣播這一訊息，這一筆交易不會被處理。礦工會執行狀態轉換函數`APPLY(S,TX)`，發現這筆交易將花費已經不在狀態中的UTXO。所以，攻擊者會對區塊鏈進行分叉，將第269999個區塊作為父區塊重新生成第270000個區塊，在此區塊中用新的交易取代舊的交易。因為區塊資料是不同的，這要求重新進行工作量證明。另外，因為攻擊者生成的新的第270000個區塊有不同的雜湊，所以原來的第270001到第270005的區塊不指向它，因此原有的區塊鏈和攻擊者的新區塊是完全分離的。在發生區塊鏈分叉時，區塊鏈長的分支被認為是誠實的區塊鏈，合法的的礦工將會沿著原有的第270005區塊後挖礦，只有攻擊者一人在新的第270000區塊後挖礦。攻擊者為了使得他的區塊鏈最長，他需要擁有比除了他以外的全網更多的算力來追趕（即51%攻擊）。

### 默克爾樹

![](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/spv1.png)

圖1：僅提供默克爾樹（Merkle tree）上的少量節點已經足夠給出分支的合法證明。

![](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/spv2.png)

圖2：任何對於默克爾樹的任何部分進行改變的嘗試都會最終導致鏈上某處的不一致。  

比特幣系統的一個重要的可擴充套件特性是：它的交易儲存在多層次的資料結構中。一個區塊的雜湊實際上只是區塊頭的雜湊，區塊頭是包含時間戳、隨機數、上個區塊雜湊和儲存了所有的區塊交易的默克爾樹的根雜湊的長度大約為200位元組的一段資料。

默克爾樹是一種二叉樹，由一組葉節點、一組中間節點和一個根節點構成。最下面的大量的葉節點包含基礎資料，每個中間節點是它的兩個子節點的雜湊，根節點也是由它的兩個子節點的雜湊，代表了默克爾樹的頂部。默克爾樹的目的是允許區塊的資料可以零散地傳送：節點可以從一個源下載區塊頭，從另外的源下載與其有關的樹的其它部分，而依然能夠確認所有的資料都是正確的。之所以如此是因為雜湊向上的擴散：如果一個惡意使用者嘗試在樹的下部加入一個偽造的交易，所引起的改動將導致樹的上層節點的改動，以及更上層節點的改動，最終導致根節點的改動以及區塊雜湊的改動，這樣協議就會將其記錄為一個完全不同的區塊（幾乎可以肯定是帶著不正確的工作量證明的）。

默克爾樹協議對比特幣的長期持續性可以說是至關重要的。在2014年4月，比特幣網路中的一個全節點-儲存和處理所有區塊的全部資料的節點-需要佔用15GB的記憶體空間，而且還以每個月超過1GB的速度增長。目前，這一儲存空間對臺式計算機來說尚可接受，但是手機已經負載不了如此巨大的資料了。未來只有商業機構和愛好者才會充當完整節點。簡化支付確認（SPV)協議允許另一種節點存在，這樣的節點被成為“輕節點”，它下載區塊頭，使用區塊頭確認工作量證明，然後只下載與其交易相關的默克爾樹“分支”。這使得輕節點只要下載整個區塊鏈的一小部分就可以安全地確定任何一筆比特幣交易的狀態和賬戶的當前餘額。

### 其它的區塊鏈應用
 
將區塊鏈的思想應用到其它領域的想法早就出現了。在2005年，尼克薩博提出了“用所有權為財產冠名”的概念，文中描述了複製資料庫技術的發展如何使基於區塊鏈的系統可以應用於登記土地所有權，建立包括例如房產權、違法侵佔和喬治亞州土地稅等概念的詳細框架。然而，不幸的是在那時還沒有實用的複製資料庫系統，所以這個協議沒有被付諸實踐。不過，自2009年比特幣系統的去中心化共識開發成功以來，許多區塊鏈的其它應用開始快速出現。

* **域名幣（namecoin）**- 創建於2010年，被稱為去中心化的名稱註冊資料庫。像Tor、Bitcoin和BitMessage這樣的去中心化協議，需要一些確認賬戶的方法，這樣其他人才能夠與使用者進行互動。但是，在所有的現存的解決方案中僅有的可用的身份標識是象`1LW79wp5ZBqaHW1jL5TciBCrhQYtHagUWy`這樣的偽隨機雜湊。理想的情況下，人們希望擁有一個帶有象“george”這樣的名稱的賬戶。然而，問題是如果有人可以建立“george”賬戶，那麼其他人同樣也可以建立“george”賬戶來假扮。唯一的解決方法是先申請原則（first-to-file），只有第一個註冊者可以成功註冊，第二個不能再次註冊同一個賬戶。這一問題就可以利用比特幣的共識協議。域名幣是利用區塊鏈實現名稱註冊系統的最早的、最成功的系統。
* **彩色幣（Colored coins）**- 彩色幣的目的是為人們在比特幣區塊鏈上建立自己的數字貨幣，或者，在更重要的一般意義上的貨幣 – 數字令牌提供服務。依照彩色幣協議，人們可以通過為某一特別的比特幣UTXO指定顏色，發行新的貨幣。該協議遞迴地將其它UTXO定義為與交易輸入UTXO相同的顏色。這就允許使用者保持只包含某一特定顏色的UTXO，傳送這些UTXO就像傳送普通的比特幣一樣，通過回溯全部的區塊鏈判斷收到的UTXO顏色。
* **元幣（Metacoins）**- 元幣的理念是在比特幣區塊鏈上建立新的協議，利用比特幣的交易儲存元幣的交易，但是採用了不同的狀態轉換函數APPLY’。因為元幣協議不能阻止比特幣區塊鏈上的無效的元幣交易，所以增加一個規則如果APPLY'(S,TX)返回錯誤，這一協議將預設APPLY'(S,TX) = S。這為建立任意的、先進的不能在比特幣系統中實現的密碼學貨幣協議提供了一個簡單的解決方法，而且開發成本非常低，因為挖礦和網路的問題已經由比特幣協議處理好了。

因此，一般而言，建立共識協議有兩種方法：建立一個獨立的網路和在比特幣網路上建立協議。雖然像域名幣這樣的應用使用第一種方法已經獲得了成功，但是該方法的實施非常困難，因為每一個應用需要建立獨立的區塊鏈和建立、測試所有狀態轉換和網路程式碼。另外，我們預測去中心化共識技術的應用將會服從冪律分佈，大多數的應用太小不足以保證自由區塊鏈的安全，我們還注意到大量的去中心化應用，尤其是去中心化自治組織，需要進行應用之間的互動。

另一方面，基於比特幣的方法存在缺點，它沒有繼承比特幣可以進行簡化確認支付（SPV) 的特性。比特幣可以實現簡化確認支付，因為比特幣可以將區塊鏈深度作為有效性確認代理。在某一點上，一旦一筆交易的祖先們距離現在足夠遠時，就可以認為它們是合法狀態的一部分。與之相反，基於比特幣區塊鏈的元幣協議不能強迫區塊鏈不包括不符合元幣協議的交易。因此，安全的元幣協議的簡化支付確認需要後向掃描所有的區塊，直到區塊鏈的初始點，以確認某一交易是否有效。目前，所有基於比特幣的元幣協議的“輕”實施都依賴可信任的伺服器提供資料，這對主要目的之一是消除信任需要的密碼學貨幣而言，只是一個相當次優的結果。

### 指令碼
 
即使不對比特幣協議進行擴充套件，它也能在一定程度上實現”智慧合約”。比特幣的UTXO可以不只被一個公鑰擁有，也可以被用基於堆棧的程式語言所編寫的更加複雜的指令碼所擁有。在這一模式下，花費這樣的UTXO，必須提供滿足指令碼的資料。事實上，基本的公鑰所有權機制也是通過指令碼實現的：指令碼將橢圓曲線簽名作為輸入，驗證交易和擁有這一UTXO的地址，如果驗證成功，返回1，否則返回0。更加複雜的指令碼用於其它不同的應用情況。例如，人們可以建立要求集齊三把私鑰中的兩把才能進行交易確認的指令碼（多重簽名），對公司賬戶、儲蓄賬戶和某些商業代理來說，這種指令碼是非常有用的。指令碼也能用來對解決計算問題的使用者傳送獎勵。人們甚至可以建立這樣的指令碼“如果你能夠提供你已經發送一定數額的的狗幣給我的簡化確認支付證明，這一比特幣UTXO就是你的了”，本質上，比特幣系統允許不同的密碼學貨幣進行去中心化的兌換。

然而，比特幣系統的指令碼語言存在一些嚴重的限制：

* **缺少圖靈完備性** – 這就是說，儘管比特幣指令碼語言可以支援多種計算，但是它不能支援所有的計算。最主要的缺失是迴圈語句。不支援迴圈語句的目的是避免交易確認時出現無限迴圈。理論上，對於指令碼程式設計師來說，這是可以克服的障礙，因為任何迴圈都可以用多次重複if 語句的方式來模擬，但是這樣做會導致指令碼空間利用上的低效率，例如，實施一個替代的橢圓曲線簽名演算法可能將需要256次重複的乘法，而每次都需要單獨編碼。
* **價值盲（Value-blindness）**。UTXO指令碼不能為賬戶的取款額度提供精細的的控制。例如，預言機合約（oracle contract）的一個強大應用是對衝合約，A和B各自向對衝合約中傳送價值1000美元的比特幣，30天以後，指令碼向A傳送價值1000美元的比特幣，向B傳送剩餘的比特幣。雖然實現對衝合約需要一個預言機（oracle）決定一比特幣值多少美元，但是與現在完全中心化的解決方案相比，這一機制已經在減少信任和基礎設施方面有了巨大的進步。然而，因為UTXO是不可分割的，為實現此合約，唯一的方法是非常低效地採用許多有不同面值的UTXO（例如對應於最大為30的每個k，有一個2^k的UTXO)並使預言機挑出正確的UTXO傳送給A和B。
* **缺少狀態** – UTXO只能是已花費或者未花費狀態，這就沒有給需要任何其它內部狀態的多階段合約或者指令碼留出生存空間。這使得實現多階段期權合約、去中心化的交換要約或者兩階段加密承諾協議（對確保計算獎勵非常必要）非常困難。這也意味著UTXO只能用於建立簡單的、一次性的合約，而不是例如去中心化組織這樣的有著更加複雜的狀態的合約，使得元協議難以實現。二元狀態與價值盲結合在一起意味著另一個重要的應用-取款限額-是不可能實現的。
* **區塊鏈盲（Blockchain-blindness）**- UTXO看不到區塊鏈的資料，例如隨機數和上一個區塊的雜湊。這一缺陷剝奪了指令碼語言所擁有的基於隨機性的潛在價值，嚴重地限制了博彩等其它領域應用。

我們已經考察了在密碼學貨幣上建立高階應用的三種方法：建立一個新的區塊鏈，在比特幣區塊鏈上使用指令碼，在比特幣區塊鏈上建立元幣協議。建立新區塊鏈的方法可以自由地實現任意的特性，成本是開發時間和培育努力。使用指令碼的方法非常容易實現和標準化，但是它的能力有限。元幣協議儘管非常容易實現，但是存在擴充套件性差的缺陷。在以太坊系統中，我們的目的是建立一個能夠同時具有這三種模式的所有優勢的通用框架。

## 以太坊
 
以太坊的目的是基於指令碼、競爭幣和鏈上元協議（on-chain meta-protocol）概念進行整合和提高，使得開發者能夠建立任意的基於共識的、可擴充套件的、標準化的、特性完備的、易於開發的和協同的應用。以太坊通過建立終極的抽象的基礎層-內建有圖靈完備程式語言的區塊鏈-使得任何人都能夠建立合約和去中心化應用並在其中設立他們自由定義的所有權規則、交易方式和狀態轉換函數。域名幣的主體框架只需要兩行程式碼就可以實現，諸如貨幣和信譽系統等其它協議只需要不到二十行程式碼就可以實現。智慧合約-包含價值而且只有滿足某些條件才能開啟的加密箱子-也能在我們的平臺上建立，並且因為圖靈完備性、價值知曉（value-awareness）、區塊鏈知曉（blockchain-awareness）和多狀態所增加的力量而比比特幣指令碼所能提供的智慧合約強大得多。

### 以太坊賬戶

在以太坊系統中，狀態是由被稱為“賬戶”（每個賬戶由一個20位元組的地址）的物件和在兩個賬戶之間轉移價值和資訊的狀態轉換構成的。以太坊的賬戶包含四個部分：

* 隨機數，用於確定每筆交易只能被處理一次的計數器
* 賬戶目前的以太幣餘額
* 賬戶的合約程式碼，如果有的話
* 賬戶的儲存（預設為空）

以太幣（Ether）是以太坊內部的主要加密燃料，用於支付交易費用。一般而言，以太坊有兩種類型的賬戶：外部所有的賬戶（由私鑰控制的）和合約賬戶（由合約程式碼控制）。外部所有的賬戶沒有程式碼，人們可以通過建立和簽名一筆交易從一個外部賬戶傳送訊息。每當合約賬戶收到一條訊息，合約內部的程式碼就會被啟用，允許它對內部儲存進行讀取和寫入，和傳送其它訊息或者建立合約。

### 訊息和交易

以太坊的訊息在某種程度上類似於比特幣的交易，但是兩者之間存在三點重要的不同。第一，以太坊的訊息可以由外部實體或者合約建立，然而比特幣的交易只能從外部建立。第二，以太坊訊息可以選擇包含資料。第三，如果以太坊訊息的接受者是合約賬戶，可以選擇進行迴應，這意味著以太坊訊息也包含函數概念。

以太坊中“交易”是指儲存從外部賬戶發出的訊息的簽名資料包。交易包含訊息的接收者、用於確認傳送者的簽名、以太幣賬戶餘額、要傳送的資料和兩個被稱為STARTGAS和GASPRICE的數值。為了防止程式碼的指數型爆炸和無限迴圈，每筆交易需要對執行程式碼所引發的計算步驟-包括初始訊息和所有執行中引發的訊息-做出限制。STARTGAS就是限制，GASPRICE是每一計算步驟需要支付礦工的費用。如果執行交易的過程中，“用完了瓦斯”，所有的狀態改變恢復原狀態，但是已經支付的交易費用不可收回了。如果執行交易中止時還剩餘瓦斯，那麼這些瓦斯將退還給傳送者。建立合約有單獨的交易類型和相應的訊息類型；合約的地址是基於賬號隨機數和交易資料的雜湊計算出來的。

訊息機制的一個重要後果是以太坊的“頭等公民”財產-合約與外部賬戶擁有同樣權利，包括髮送訊息和建立其它合約的權利。這使得合約可以同時充當多個不同的角色，例如，使用者可以使去中心化組織（一個合約）的一個成員成為一箇中介賬戶（另一個合約），為一個偏執的使用定製的基於量子證明的蘭波特簽名（第三個合約）的個人和一個自身使用由五個私鑰保證安全的賬戶（第四個合約）的共同簽名實體提供居間服務。以太坊平臺的強大之處在於去中心化的組織和代理合約不需要關心合約的每一參與方是什麼類型的賬戶。

### 以太坊狀態轉換函數

![ethertransition.png](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/ethertransition.png)

以太坊的狀態轉換函數：`APPLY(S,TX) -> S'`，可以定義如下：

1.  檢查交易的格式是否正確（即有正確數值）、簽名是否有效和隨機數是否與傳送者賬戶的隨機數匹配。如否，返回錯誤。
2.  計算交易費用:`fee=STARTGAS * GASPRICE`，並從簽名中確定傳送者的地址。從傳送者的賬戶中減去交易費用和增加發送者的隨機數。如果賬戶餘額不足，返回錯誤。
3.  設定初值`GAS = STARTGAS`，並根據交易中的位元組數減去一定量的瓦斯值。
4.  從傳送者的賬戶轉移價值到接收者賬戶。如果接收賬戶還不存在，建立此賬戶。如果接收賬戶是一個合約，執行合約的程式碼，直到程式碼執行結束或者瓦斯用完。
5.  如果因為傳送者賬戶沒有足夠的錢或者程式碼執行耗盡瓦斯導致價值轉移失敗，恢復原來的狀態，但是還需要支付交易費用，交易費用加至礦工賬戶。
6.  否則，將所有剩餘的瓦斯歸還給傳送者，消耗掉的瓦斯作為交易費用傳送給礦工。
例如，假設合約的程式碼如下：

```
python
if not self.storage[calldataload(0)]:
    self.storage[calldataload(0)] = calldataload(32)
``` 

需要注意的是，在現實中合約程式碼是用底層以太坊虛擬機器（EVM）程式碼寫成的。上面的合約是用我們的高階語言Serpent語言寫成的，它可以被編譯成EVM程式碼。假設合約儲存器開始時是空的，一個值為10以太，瓦斯為2000，瓦斯價格為0.001以太並且64位元組資料，第一個三十二位元組的塊代表號碼2和第二個代表詞`CHARLIE`。的交易傳送後，狀態轉換函數的處理過程如下：

1. 檢查交易是否有效、格式是否正確。
2. 檢查交易傳送者至少有2000*0.001=2個以太幣。如果有，從傳送者賬戶中減去2個以太幣。
3. 初始設定gas=2000,假設交易長為170位元組，每位元組的費用是5，減去850，所以還剩1150。
4. 從傳送者賬戶減去10個以太幣，為合約賬戶增加10個以太幣。
5. 執行程式碼。在這個合約中，執行程式碼很簡單：它檢查合約儲存器索引為2處是否已使用，注意到它未被使用，然後將其值置為CHARLIE。假設這消耗了187單位的瓦斯，於是剩餘的瓦斯為1150 - 187 = 963。
6. 向傳送者的賬戶增加963*0.001=0.963個以太幣，返回最終狀態。


如果沒有合約接收交易，那麼所有的交易費用就等於GASPRICE乘以交易的位元組長度，交易的資料就與交易費用無關了。另外，需要注意的是，合約發起的訊息可以對它們產生的計算分配瓦斯限額，如果子計算的瓦斯用完了，它只恢復到訊息發出時的狀態。因此，就像交易一樣，合約也可以通過對它產生的子計算設定嚴格的限制，保護它們的計算資源。

### 程式碼執行
 
以太坊合約的程式碼使用低階的基於堆棧的位元組碼的語言寫成的，被稱為“以太坊虛擬機器程式碼”或者“EVM程式碼”。程式碼由一系列位元組構成，每一個位元組代表一種操作。一般而言，程式碼執行是無限迴圈，程式計數器每增加一（初始值為零）就執行一次操作，直到程式碼執行完畢或者遇到錯誤，`STOP`或者`RETURN`指令。操作可以訪問三種儲存資料的空間：

* **堆棧**，一種後進先出的資料儲存，32位元組的數值可以入棧，出棧。
* **記憶體**，可無限擴充套件的位元組佇列。
* **合約的長期儲存**，一個祕鑰/數值的儲存，其中祕鑰和數值都是32位元組大小，與計算結束即重置的堆棧和記憶體不同，儲存內容將長期保持。
 
程式碼可以象訪問區塊頭資料一樣訪問數值，傳送者和接受到的訊息中的資料，程式碼還可以返回資料的位元組佇列作為輸出。
 
EVM程式碼的正式執行模型令人驚訝地簡單。當以太坊虛擬機器執行時，它的完整的計算狀態可以由元組`(block_state, transaction, message, code, memory, stack, pc, gas)`來定義，這裡`block_state`是包含所有賬戶餘額和儲存的全局狀態。每輪執行時，通過調出程式碼的第`pc`（程式計數器）個位元組，當前指令被找到，每個指令都有定義自己如何影響元組。例如，`ADD`將兩個元素出棧並將它們的和入棧，將`gas`（瓦斯）減一併將`pc`加一，`SSTORE`將頂部的兩個元素出棧並將第二個元素插入到由第一個元素定義的合約儲存位置，同樣減少最多200的gas值並將`pc`加一，雖然有許多方法通過即時編譯去優化以太坊，但以太坊的基礎性的實施可以用幾百行程式碼實現。
 
### 區塊鏈和挖礦

雖然有一些不同，但以太坊的區塊鏈在很多方面類似於比特幣區塊鏈。它們的區塊鏈架構的不同在於，以太坊區塊不僅包含交易記錄和最近的狀態，還包含區塊序號和難度值。以太坊中的區塊確認演算法如下：

1.  檢查區塊引用的上一個區塊是否存在和有效。
2.  檢查區塊的時間戳是否比引用的上一個區塊大，而且小於15分鐘。
3.  檢查區塊序號、難度值、 交易根，叔根和瓦斯限額（許多以太坊特有的底層概念）是否有效。
4.  檢查區塊的工作量證明是否有效。
5.  將`S[0]`賦值為上一個區塊的`STATE_ROOT`。
6.  將`TX`賦值為區塊的交易列表，一共有`n`筆交易。對於屬於`0……n-1`的`i`，進行狀態轉換`S[i+1] = APPLY(S[i],TX[i])`。如果任何一個轉換髮生錯誤，或者程式執行到此處所花費的瓦斯（gas）超過了`GASLIMIT`，返回錯誤。
7.  用`S[n]`給`S_FINAL`賦值, 向礦工支付區塊獎勵。
8.  檢查`S_FINAL`是否與`STATE_ROOT`相同。如果相同，區塊是有效的。否則，區塊是無效的。
 
這一確認方法乍看起來似乎效率很低，因為它需要儲存每個區塊的所有狀態，但是事實上以太坊的確認效率可以與比特幣相提並論。原因是狀態儲存在樹結構中（tree structure），每增加一個區塊只需要改變樹結構的一小部分。因此，一般而言，兩個相鄰的區塊的樹結構的大部分應該是相同的，因此儲存一次資料，可以利用指針（即子樹雜湊）引用兩次。一種被稱為“帕特里夏樹”（“Patricia Tree”）的樹結構可以實現這一點，其中包括了對默克爾樹概念的修改，不僅允許改變節點，而且還可以插入和刪除節點。另外，因為所有的狀態資訊是最後一個區塊的一部分，所以沒有必要儲存全部的區塊歷史-這一方法如果能夠可以應用到比特幣系統中，經計算可以對儲存空間有10-20倍的節省。

## 應用

一般來講，以太坊之上有三種應用。第一類是金融應用，為使用者提供更強大的用他們的錢管理和參與合約的方法。包括子貨幣，金融衍生品，對衝合約，儲蓄錢包，遺囑，甚至一些種類的全面的僱傭合約。第二類是半金融應用，這裡有錢的存在但也有很重的非金錢的方面，一個完美的例子是為解決計算問題而設的自我強制懸賞。最後，還有線上投票和去中心化治理這樣的完全的非金融應用。

### 令牌系統

鏈上令牌系統有很多應用，從代表如美元或黃金等資產的子貨幣到公司股票，單獨的令牌代表智慧資產，安全的不可偽造的優惠券，甚至與傳統價值完全沒有聯絡的用來進行積分獎勵的令牌系統。在以太坊中實施令牌系統容易得讓人吃驚。關鍵的一點是理解，所有的貨幣或者令牌系統，從根本上來說是一個帶有如下操作的資料庫：從A中減去X單位並把X單位加到B上，前提條件是(1)A在交易之前有至少X單位以及(2)交易被A批准。實施一個令牌系統就是把這樣一個邏輯實施到一個合約中去。

用Serpent語言實施一個令牌系統的基本程式碼如下：

```
python
def send(to, value):
    if self.storage[from] >= value:
        self.storage[from] = self.storage[from] - value
        self.storage[to] = self.storage[to] + value
```

這從本質上來說是本文將要進一步描述的“銀行系統”狀態轉變功能的一個最小化實施。需要增加一些額外的程式碼以提供在初始和其它一些邊緣情況下分發貨幣的功能，理想情況下會增加一個函數讓其它合約來查詢一個地址的餘額。就足夠了。理論上，基於以太坊的充當子貨幣的令牌系統可能包括一個基於比特幣的鏈上元幣所缺乏的重要功能：直接用這種貨幣支付交易費的能力。實現這種能力的方法是在合約裡維護一個以太幣賬戶以用來為傳送者支付交易費，通過收集被用來充當交易費用的內部貨幣並把它們在一個不斷執行的拍賣中拍賣掉，合約不斷為該以太幣賬戶注資。這樣使用者需要用以太幣“啟用”他們的賬戶，但一旦賬戶中有以太幣它將會被重複使用因為每次合約都會為其充值。

### 金融衍生品和價值穩定的貨幣

金融衍生品是“智慧合約”的最普遍的應用，也是最易於用程式碼實現的之一。實現金融合約的主要挑戰是它們中的大部分需要參照一個外部的價格釋出器；例如，一個需求非常大的應用是一個用來對衝以太幣（或其它密碼學貨幣）相對美元價格波動的智慧合約，但該合約需要知道以太幣相對美元的價格。最簡單地方法是通過由某特定機構（例如納斯達克）維護的“資料提供“合約進行，該合約的設計使得該機構能夠根據需要更新合約，並提供一個介面使得其它合約能夠通過傳送一個訊息給該合約以獲取包含價格資訊的回覆。

當這些關鍵要素都齊備，對衝合約看起來會是下面的樣子：

1. 等待A輸入1000以太幣。.
2. 等待B 輸入1000以太幣。
3. 通過查詢資料提供合約，將1000以太幣的美元價值，例如，x美元，記錄至儲存器。
4. 30天后，允許A或B“重新啟用“合約以傳送價值x美元的以太幣（重新查詢資料提供合約以獲取新價格並計算）給A並將剩餘的以太幣傳送給B。

這樣的合約在密碼學商務中有非同尋常的潛力。密碼學貨幣經常被詬病的一個問題就是其價格的波動性；雖然大量的使用者和商家可能需要密碼學資產所帶來的安全和便利，可他們不太會樂意麵對一天中資產跌去23%價值的情形。直到現在，最為常見的推薦方案是發行者背書資產；思想是發行者建立一種子貨幣，對此種子貨幣他們有權發行和贖回，給予（線下）提供給他們一個單位特定相關資產（例如黃金，美元）的人一個單位子貨幣。發行者承諾當任何人送還一個單位密碼學資產時。發還一個單位的相關資產。這種機制能夠使任何非密碼學資產被“升級“為密碼學資產，如果發行者值得信任的話。

然而實踐中發行者並非總是值得信任的，並且一些情況下銀行體系太脆弱，或者不夠誠實守信從而使這樣的服務無法存在。金融衍生品提供了一種替代方案。這裡將不再有提供儲備以支撐一種資產的單獨的發行者，取而代之的是一個由賭一種密碼學資產的價格會上升的投機者構成的去中心化市場。與發行者不同，投機者一方沒有討價還價的權利，因為對衝合約把他們的儲備凍結在了契約中。注意這種方法並非是完全去中心化的，因為依然需要一個可信任的提供價格資訊的資料來源，儘管依然有爭議這依然是在降低基礎設施需求（與發行者不同，一個價格釋出器不需要牌照並且似乎可歸為自由言論一類）和降低潛在欺詐風險方面的一個巨大的進步。

### 身份和信譽系統

最早的替代幣，域名幣，嘗試使用一個類比特幣塊鏈來提供一個名稱註冊系統，在那裡使用者可以將他們的名稱和其它資料一起在一個公共資料庫註冊。最常用的應用案例把象“bitcoin.org“（或者在域名幣中，”bitcoin.bit“）一樣的域名與一個IP地址對應的域名系統。其它的應用案例包括電子郵件驗證系統和潛在的更先進的信譽系統。這裡是以太坊中提供與域名幣類似的的名稱註冊系統的基礎合約：

```
python
def register(name, value):
    if !self.storage[name]:
        self.storage[name] = value
```

合約非常簡單；就是一個以太坊網路中的可以被新增但不能被修改或移除的資料庫。任何人都可以把一個名稱註冊為一個值並永遠不變。一個更復雜的名稱註冊合約將包含允許其他合約查詢的“功能條款“，以及一個讓一個名稱的”擁有者“（即第一個註冊者）修改資料或者轉讓所有權的機制。甚至可以在其上新增信譽和信任網路功能。

### 去中心化儲存

在過去的幾年裡出現了一些大眾化的線上檔案儲存初創公司，最突出的是Dropbox，它尋求允許使用者上傳他們的硬碟備份，提供備份儲存服務並允許使用者訪問從而按月向用戶收取費用。然而，在這一點上這個檔案儲存市場有時相對低效；對現存服務的粗略觀察表明，特別地在“神祕谷“20-200GB這一既沒有免費空間也沒有企業級使用者折扣的水平上，主流檔案儲存成本每月的價格意味著支付在一個月裡支付整個硬碟的成本。以太坊合約允許去中心化儲存生態的開發，這樣使用者通過將他們自己的硬碟或未用的網路空間租出去以獲得少量收益，從而降低了檔案儲存的成本。

這樣的設施的基礎性構件就是我們所謂的“去中心化Dropbox合約“。這個合約工作原理如下。首先，某人將需要上傳的資料分成塊，對每一塊資料加密以保護隱私，並且以此構建一個默克爾樹。然後建立一個含以下規則的合約，每N個塊，合約將從默克爾樹中抽取一個隨機索引（使用能夠被合約程式碼訪問的上一個塊的雜湊來提供隨機性）， 然後給第一個實體X以太以支撐一個帶有類似簡化驗證支付（SPV）的在樹中特定索引處的塊的所有權證明。當一個使用者想重新下載他的檔案，他可以使用微支付通道協議（例如每32k位元組支付1薩博）恢復檔案；從費用上講最高效的方法是支付者不到最後不釋出交易，而是用一個略微更合算的帶有同樣隨機數的交易在每32k位元組之後來代替原交易。

這個協議的一個重要特徵是，雖然看起來象是一個人信任許多不準備丟失檔案的隨機節點，但是他可以通過祕密分享把檔案分成許多小塊，然後通過監視合同得知每個小塊都還被某個節點的儲存著。如果一個合約依然在付款，那麼就提供了某個人依然在儲存檔案的證據。

### 去中心化自治組織

通常意義上“去中心化自治組織（DAO, decentralized autonomous organization）”的概念指的是一個擁有一定數量成員或股東的虛擬實體，依靠比如67%多數來決定花錢以及修改程式碼。成員會集體決定組織如何分配資金。分配資金的方法可能是懸賞，工資或者更有吸引力的機制比如用內部貨幣獎勵工作。這僅僅使用密碼學塊鏈技術就從根本上覆制了傳統公司或者非營利組織的法律意義以實現強制執行。至此許多圍繞DAO的討論都是圍繞一個帶有接受分紅的股東和可交易的股份的“去中心化自治公司（DAC，decentralized autonomous corporation）”的“資本家”模式；作為替代者，一個被描述為“去中心化自治社群（decentralized autonomous community）”的實體將使所有成員都在決策上擁有同等的權利並且在增減成員時要求67%多數同意。每個人都只能擁有一個成員資格這一規則需要被群體強制實施。

下面是一個如何用程式碼實現DO的綱要。最簡單地設計就是一段如果三分之二成員同意就可以自我修改的程式碼。雖然理論上程式碼是不可更改的，然而通過把程式碼主幹放在一個單獨的合約內並且把合約呼叫的地址指向一個可更改的儲存依然可以容易地繞開障礙而使程式碼變得可修改，在一個這樣的DAO合約的簡單實現中有三種交易類型，由交易提供的資料區分：

* `[0,i,K,V]` 註冊索引為i 的對儲存地址索引為K 至 v 的內容的更改建議。
* `[1,i]` 註冊對建議i 的投票。
* `[2,i]` 如有足夠投票則確認建議i。

然後合約對每一項都有具體的條款。它將維護一個所有開放儲存的更改記錄以及一個誰投票表決的表。還有一個所有成員的表。當任何儲存內容的更改獲得了三分之二多數同意，一個最終的交易將執行這項更改。一個更加複雜的框架會增加內建的選舉功能以實現如傳送交易，增減成員，甚至提供委任制民主一類的投票代表（即任何人都可以委託另外一個人來代表自己投票，而且這種委託關係是可以傳遞的，所以如果A委託了B然後B委託了C那麼C將決定A的投票）。這種設計將使DAO作為一個去中心化社群有機地成長， 使人們最終能夠把挑選合適人選的任務交給專家，與當前系統不同，隨著社群成員不斷改變他們的站隊假以時日專家會容易地出現和消失。
一個替代的模式是去中心化公司，那裡任何賬戶可以擁有0到更多的股份，決策需要三分之二多數的股份同意。一個完整的框架將包括資產管理功能-可以提交買賣股份的訂單以及接受這種訂單的功能（前提是合約裡有訂單匹配機制）。代表依然以委任制民主的方式存在，產生了“董事會”的概念。

更先進的組織治理機制可能會在將來實現；現在一個去中心化組織（DO）可以從去中心化自治組織（DAO）開始描述。DO和DAO的區別是模糊的，一個大致的分割線是治理是否可以通過一個類似政治的過程或者一個“自動”過程實現，一個不錯的直覺測試是“無通用語言”標準：如果兩個成員不說同樣的語言組織還能正常執行嗎？顯然，一個簡單的傳統的持股式公司會失敗，而象比特幣協議這樣的卻很可能成功，羅賓·漢森的“futarchy”，一個通過預測市場實現組織化治理的機制是一個真正的說明“自治”式治理可能是什麼樣子的好例子。注意一個人無需假設所有DAO比所有DO優越；自治只是一個在一些特定場景下有很大優勢的，但在其它地方未必可行的正規化，許多半DAO可能存在。

### 進一步的應用 

1. **儲蓄錢包**。 假設Alice想確保她的資金安全，但她擔心丟失或者被黑客盜走私鑰。她把以太幣放到和Bob簽訂的一個合約裡，如下所示，這合同是一個銀行： 
  * Alice單獨每天最多可提取1%的資金。
  * Bob單獨每天最多可提取1%的資金，但Alice可以用她的私鑰建立一個交易取消Bob的提現許可權。
  * Alice 和 Bob 一起可以任意提取資金。
一般來講，每天1%對Alice足夠了，如果Alice想提現更多她可以聯絡Bob尋求幫助。如果Alice的私鑰被盜，她可以立即找到Bob把她的資金轉移到一個新合同裡。如果她弄丟了她的私鑰，Bob可以慢慢地把錢提出。如果Bob表現出了惡意，她可以關掉他的提現許可權。

2. **作物保險**。一個人可以很容易地以天氣情況而不是任何價格指數作為資料輸入來建立一個金融衍生品合約。如果一個愛荷華的農民購買了一個基於愛荷華的降雨情況進行反向賠付的金融衍生品，那麼如果遇到乾旱，該農民將自動地收到賠付資金而如果有足量的降雨他會很開心因為他的作物收成會很好。

3. **一個去中心化的資料釋出器**。 對於基於差異的金融合約，事實上通過“謝林點”協議將資料釋出器去中心化是可能的。謝林點的工作原理如下：N方為某個指定的資料提供輸入值到系統（例如ETH/USD價格），所有的值被排序，每個提供25%到75%之間的值的節點都會獲得獎勵，每個人都有激勵去提供他人將提供的答案，大量玩家可以真正同意的答案明顯預設就是正確答案，這構造了一個可以在理論上提供很多數值，包括ETH/USD價格，柏林的溫度甚至某個特別困難的計算的結果的去中心化協議。

5.**雲端計算**。EVM技術還可被用來建立一個可驗證的計算環境，允許使用者邀請他人進行計算然後選擇性地要求提供在一定的隨機選擇的檢查點上計算被正確完成的證據。這使得建立一個任何使用者都可以用他們的桌上型電腦，膝上型電腦或者專用伺服器參與的雲端計算市場成為可能，現場檢查和安全保證金可以被用來確保系統是值得信任的（即沒有節點可以因欺騙獲利）。雖然這樣一個系統可能並不適用所有任務；例如，需要高階程序間通訊的任務就不易在一個大的節點雲上完成。然而一些其它的任務就很容易實現並行；SETI@home, folding@home和基因演算法這樣的項目就很容易在這樣的平臺上進行。

6.**點對點賭博**。任意數量的點對點賭博協議都可以搬到以太坊的區塊鏈上，例如Frank Stajano和Richard Clayton的Cyberdice。 最簡單的賭博協議事實上是這樣一個簡單的合約，它用來賭下一個區塊的哈稀值與猜測值之間的差額, 據此可以建立更復雜的賭博協議，以實現近乎零費用和無欺騙的賭博服務。

7.**預測市場**。 不管是有神諭還是有謝林幣，預測市場都會很容易實現，帶有謝林幣的預測市場可能會被證明是第一個主流的作為去中心化組織管理協議的“futarchy”應用。

8.鏈上去中心化市場，以身份和信譽系統為基礎。

## 雜項和關注

### 改進版幽靈協議的實施

 “幽靈“協議（"Greedy Heaviest Observed Subtree" (GHOST) protocol）是由Yonatan Sompolinsky 和 Aviv Zohar在2013年12月引入的創新。幽靈協議提出的動機是當前快速確認的塊鏈因為區塊的高作廢率而受到低安全性困擾；因為區塊需要花一定時間（設為t）擴散至全網，如果礦工A挖出了一個區塊然後礦工B碰巧在A的區塊擴散至B之前挖出了另外一個區塊，礦工B的區塊就會作廢並且沒有對網路安全作出貢獻。此外，這裡還有中心化問題：如果A是一個擁有全網30%算力的礦池而B擁有10%的算力，A將面臨70%的時間都在產生作廢區塊的風險而B在90%的時間裡都在產生作廢區塊。因此，如果作廢率高，A將簡單地因為更高的算力份額而更有效率，綜合這兩個因素，區塊產生速度快的塊鏈很可能導致一個礦池擁有實際上能夠控制挖礦過程的算力份額。

正如Sompolinsky 和 Zohar所描述的，通過在計算哪條鏈“最長”的時候把廢區塊也包含進來，幽靈協議解決了降低網路安全性的第一個問題；這就是說，不僅一個區塊的父區塊和更早的祖先塊，祖先塊的作廢的後代區塊（以太坊術語中稱之為“叔區塊”）也被加進來以計算哪一個區塊擁有支援其的最大工作量證明。我們超越了Sompolinsky 和 Zohar所描述的協議以解決第二個問題 – 中心化傾向，以太坊付給以“叔區塊”身份為新塊確認作出貢獻的廢區塊87.5%的獎勵，把它們納入計算的“侄子區塊”將獲得獎勵的12.5%，不過，交易費用不獎勵給叔區塊。
以太坊實施了一個只下探到第五層的簡化版本的幽靈協議。其特點是，廢區塊只能以叔區塊的身份被其父母的第二代至第五代後輩區塊，而不是更遠關係的後輩區塊（例如父母區塊的第六代後輩區塊，或祖父區塊的第三代後輩區塊）納入計算。這樣做有幾個原因。首先，無條件的幽靈協議將給計算給定區塊的哪一個叔區塊合法帶來過多的複雜性。其次，帶有以太坊所使用的補償的無條件的幽靈協議剝奪了礦工在主鏈而不是一個公開攻擊者的鏈上挖礦的激勵。最後，計算表明帶有激勵的五層幽靈協議即使在出塊時間為15s的情況下也實現了了95%以上的效率，而擁有25%算力的礦工從中心化得到的益處小於3%。

### 費用

因為每個釋出的到區塊鏈的交易都佔用了下載和驗證的成本，需要有一個包括交易費的規範機制來防範濫發交易。比特幣使用的預設方法是純自願的交易費用，依靠礦工擔當守門人並設定動態的最低費用。因為這種方法是“基於市場的”，使得礦工和交易傳送者能夠按供需來決定價格，所以這種方法在比特幣社群被很順利地接受了。然而，這個邏輯的問題在於，交易處理並非一個市場；雖然根據直覺把交易處理解釋成礦工給傳送者提供的服務是很有吸引力的，但事實上一個礦工收錄的交易是需要網路中每個節點處理的，所以交易處理中最大部分的成本是由第三方而不是決定是否收錄交易的礦工承擔的。於是，非常有可能發生公地悲劇。

然而，當給出一個特殊的不夠精確的簡化假設時，這個基於市場的機制的漏洞很神奇地消除了自己的影響。論證如下。假設：

1. 一個交易帶來 k 步操作, 提供獎勵 kR給任何收錄該交易的礦工，這裡 R 由交易釋出者設定， k 和 R 對於礦工都是事先（大致上）可見的。
2. 每個節點處理每步操作的成本都是 C (即所有節點的效率一致)。
3. 有 N 個挖礦節點，每個算力一致(即全網算力的1/N)。
4. 沒有不挖礦的全節點。
 
當預期獎勵大於成本時，礦工願意挖礦。這樣，因為礦工有1/N 的機會處理下一個區塊，所以預期的收益是 kR/N , 礦工的處理成本簡單為 kC. 這樣當 kR/N > kC， 即 R > NC時。礦工願意收錄交易。注意 R 是由交易傳送者提供的每步費用，是礦工從處理交易中獲益的下限。 NC 是全網處理一個操作的成本。所以，礦工僅有動機去收錄那些收益大於成本的交易。
然而，這些假設與實際情況有幾點重要的偏離：

1. 因為額外的驗證時間延遲了塊的廣播因而增加了塊成為廢塊的機會，處理交易的礦工比其它的驗證節點付出了更高的成本。
2. 不挖礦的全節點是存在的。
3. 實踐中算力分佈可能最後是極端不平均的。
4. 以破壞網路為己任的投機者，政敵和瘋子確實存在，並且他們能夠聰明地設定合同使得他們的成本比其它驗證節點低得多。
上面第1點驅使礦工收錄更少的交易，第2點增加了 NC; 因此這兩點的影響至少部分互相抵消了. 第3點和第4點是主要問題；作為解決方案我們簡單地建立了一個浮動的上限：沒有區塊能夠包含比BLK_LIMIT_FACTOR 倍長期指數移動平均值更多的操作數。具體地：
  
`blk.oplimit = floor((blk.parent.oplimit * (EMAFACTOR - 1) + floor(parent.opcount * BLK_LIMIT_FACTOR)) /EMA_FACTOR)`  
  
BLK_LIMIT_FACTOR 和 EMA_FACTOR 是暫且被設為 65536 和 1.5 的常數，但可能會在更深入的分析後調整。
回覆

### 計算和圖靈完備

需要強調的是以太坊虛擬機器是圖靈完備的； 這意味著EVM程式碼可以實現任何可以想象的計算，包括無限迴圈。EVM程式碼有兩種方式實現迴圈。首先， JUMP 指令可以讓程式跳回至程式碼前面某處，還有允許如 `while x < 27: x = x * 2 ` 一樣的條件語句的JUMPI 指令實現條件跳轉。其次，合約可以呼叫其它合約，有通過遞迴實現迴圈的潛力。這很自然地導致了一個問題：惡意使用者能夠通過迫使礦工和全節點進入無限迴圈而不得不關機嗎？ 這問題出現是因為電腦科學中一個叫停機問題的問題：一般意義上沒有辦法知道，一個給定的程式是否能在有限的時間內結束執行。

正如在狀態轉換章節所述，我們的方案通過為每一個交易設定執行執行的最大計算步數來解決問題，如果超過則計算被恢復原狀但依然要支付費用。訊息以同樣的方式工作。為顯示這一方案背後的動機，請考慮下面的例子：

* 一個攻擊者建立了一個執行無限迴圈的合約，然後傳送了一個啟用迴圈的交易給礦工，礦工將處理交易，執行無限迴圈直到瓦斯耗盡。即使瓦斯耗盡交易半途停止，交易依然正確（回到原處）並且礦工依然從攻擊者哪裡掙到了每一步計算的費用。
* 一個攻擊者建立一個非常長的無限迴圈意圖迫使礦工長時間內一直計算致使在計算結束前若干區塊已經產生於是礦工無法收錄交易以賺取費 用。然而，攻擊者需要釋出一個 STARTGAS 值以限制可執行步數，因而礦工將提前知道計算將耗費過多的步數。
* 一個攻擊者看到一個包含諸如 send(A,self.storage); self.storage = 0格式的合約然後傳送帶有隻夠執行第一步的費用的而不夠執行第二步的交易（即提現但不減少賬戶餘額）。合約作者無需擔心防衛類似攻擊，因為如果執行中途停止則所有變更都被回覆。
* 一個金融合約靠提取九個專用資料釋出器的中值來工作以最小化風險，一個攻擊者接管了其中一個數據提供器，然後把這個按DAO章節所述的可變地址呼叫機制設計成可更改的資料提供器轉為執行一個無限迴圈，以求嘗試逼迫任何從此金融合約索要資金的嘗試都會因瓦斯耗盡而中止。然而，該金融合約可以在訊息裡設定瓦斯限制以防範此類問題。
圖靈完備的替代是圖靈不完備，這裡 JUMP 和 JUMPI 指令不存在並且在某個給定時間每個合約只允許有一個拷貝存在於呼叫堆棧內。在這樣的系統裡，上述的費用系統和圍繞我們的方案的效率的不確定性可能都是不需要的，因為執行一個合約的成本將被它的大小決定。此外，圖靈不完備甚至不是一個大的限制，在我們內部設想的所有合約例子中，至今只有一個需要迴圈，而且即使這迴圈也可以被26個單行程式碼段的重複所代替。考慮到圖靈完備帶來的嚴重的麻煩和有限的益處，為什麼不簡單地使用一種圖靈不完備語言呢？事實上圖靈不完備遠非一個簡潔的解決方案。為什麼？請考慮下面的合約：

```
python
C0: call(C1); call(C1);
C1: call(C2); call(C2);
C2: call(C3); call(C3);
...
C49: call(C50); call(C50);
C50: (作一個圖靈機的步計算和記錄結果在合約的長期儲存)
```

現在，傳送一個這樣的交易給A，這樣，在51個交易中，我們有了一個需要花費2^50 步計算的合約，礦工可能嘗試通過為每一個合約維護一個最高可執行步數並且對於遞迴呼叫其它合約的合約計算可能執行步數從而預先檢測這樣的邏輯炸彈，但是這會使礦工禁止建立其它合約的合約（因為上面26個合約的建立和執行可以很容易地放入一個單獨合約內）。另外一個問題點是一個訊息的地址欄位是一個變數，所以通常來講可能甚至無法預先知道一個合約將要呼叫的另外一個合約是哪一個。於是，最終我們有了一個驚人的結論：圖靈完備的管理驚人地容易，而在缺乏同樣的控制時圖靈不完備的管理驚人地困難- 那為什麼不讓協議圖靈完備呢？

### 貨幣和發行

以太坊網路包含自身的內建貨幣以太幣，以太幣扮演雙重角色，為各種數字資產交易提供主要的流動性，更重要的是提供了了支付交易費用的一種機制。為便利及避免將來的爭議期間（參見當前的mBTC/uBTC/聰的爭論），不同面值的名稱將被提前設定：

* 1: 偉
* 10^12: 薩博
* 10^15: 芬尼
* 10^18: 以太

這應該被當作是“元”和“分”或者“比特幣”和“聰”的概念的擴充套件版，在不遠的將來，我們期望“以太”被用作普通交易，“芬尼”用來進行微交易，“薩博”和“偉”用來進行關於費用和協議實施的討論。

發行模式如下：

* 通過發售活動，以太幣將以每BTC 1337-2000以太的價格發售，一個旨在為以太坊組織籌資並且為開發者支付報酬的機制已經在其它一些密碼學貨幣平臺上成功使用。早期購買者會享受較大的折扣，發售所得的BTC將完全用來支付開發者和研究者的工資和懸賞，以及投入密碼學貨幣生態系統的項目。
* 0.099x （x為發售總量）將被分配給BTC融資或其它的確定性融資成功之前參與開發的早期貢獻者，另外一個0.099x將分配給長期研究項目。
* 自上線時起每年都將有0.26x（x為發售總量）被礦工挖出。

### 發行分解
永久線性增長模型降低了在比特幣中出現的財富過於集中的風險，並且給予了活在當下和將來的人公平的機會去獲取貨幣，同時保持了對獲取和持有以太幣的激勵，因為長期來看“貨幣供應增長率”是趨於零的。我們還推斷，隨著時間流逝總會發生因為粗心和死亡等原因帶來的幣的遺失，假設幣的遺失是每年貨幣供應量的一個固定比例，則最終總的流通中的貨幣供應量會穩定在一個等於年貨幣發行量除以遺失率的值上（例如，當遺失率為1%時，當供應量達到30x時，每年有0.3x被挖出同時有0.3x丟失，達到一個均衡）。

![](http://bitcoin8btc.qiniudn.com/wp-content/uploads/2014/10/table.png)
除了線性的發行方式外，和比特幣一樣以太幣的的供應量增長率長期來看也趨於零。

![](http://bitcoin8btc.qiniudn.com/wp-content/uploads/2014/10/supply.png)

### 挖礦的中心化

比特幣挖礦演算法基本上是讓礦工千萬次地輕微改動區塊頭，直到最終某個節點的改動版本的雜湊小於目標值（目前是大約2190）。然而，這種挖礦演算法容易被兩種形式的中心化攻擊。第一種，挖礦生態系統被專門設計的因而在比特幣挖礦這一特殊任務上效率提高上千倍的ASICs（專用積體電路）和電腦晶片控制。這意味著比特幣挖礦不再是高度去中心化的和追求平等主義的，而是需要鉅額資本的有效參與。第二種，大部分比特幣礦工事實上不再在本地完成區塊驗證；而是依賴中心化的礦池提供區塊頭。這個問題可以說很嚴重：在本文寫作時，最大的兩個礦池間接地控制了大約全網50%的算力，雖然當一個礦池或聯合體嘗試51%攻擊時礦工可以轉換到其它礦池這一事實減輕了問題的嚴重性。

以太坊現在的目的是使用一個基於為每1000個隨機數隨機產生唯一雜湊的函數的挖礦演算法，用足夠寬的計算域，去除專用硬體的優勢。這樣的策略當然不會使中心化的收益減少為零，但是也不需要。注意每單個使用者使用他們的私人膝上型電腦或桌上型電腦就可以幾乎免費地完成一定量的挖礦活動，但當到了100%的CPU使用率之後更多地挖礦就會需要他們支付電力和硬體成本。ASIC挖礦公司需要從第一個雜湊開始就為電力和硬體支付成本。所以，如果中心化收益能夠保持在(E + H) /E 以下，那麼即使ASICs被製造出來普通礦工依然有生存空間。另外，我們計劃將挖礦演算法設計成挖礦需要訪問整個區塊鏈，迫使礦工儲存完成的區塊鏈或者至少能夠驗證每筆交易。這去除了對中心化礦池的需要；雖然礦池依然可以扮演平滑收益分配的隨機性的角色，但這功能可以被沒有中心化控制的P2P礦池完成地同樣好。這樣即使大部分普通使用者依然傾向選擇輕客戶端，通過增加網路中的全節點數量也有助於抵禦中心化。

### 擴充套件性

擴充套件性問題是以太坊常被關注的地方，與比特幣一樣，以太坊也遭受著每個交易都需要網路中的每個節點處理這一困境的折磨。比特幣的當前區塊鏈大小約為20GB，以每小時1MB的速度增長。如果比特幣網路處理Visa級的2000tps的交易，它將以每三秒1MB的速度增長（1GB每小時，8TB每年）。以太坊可能也會經歷相似的甚至更糟的增長模式，因為在以太坊區塊鏈之上還有很多應用，而不是像比特幣只是簡單的貨幣，但以太坊全節點只需儲存狀態而不是完整的區塊鏈歷史這一事實讓情況得到了改善。

大區塊鏈的問題是中心化風險。如果塊鏈大小增加至比如100TB，可能的場景將是隻有非常小數目的大商家會執行全節點，而常規使用者使用輕的SPV節點。這會增加對全節點合夥欺詐牟利（例如更改區塊獎勵，給他們自己BTC）的風險的擔憂。輕節點將沒有辦法立刻檢測到這種欺詐。當然，至少可能存在一個誠實的全節點，並且幾個小時之後有關詐騙的資訊會通過Reddit這樣的渠道洩露，但這時已經太晚：任憑普通使用者做出怎樣的努力去廢除已經產生的區塊，他們都會遇到與發動一次成功的51%攻擊同等規模的巨大的不可行的協調問題。在比特幣這裡，現在這是一個問題，但Peter Todd建議的一個改動可以緩解這個問題。

近期，以太坊會使用兩個附加的策略以應對此問題。首先，因為基於區塊鏈的挖礦演算法，至少每個礦工會被迫成為一個全節點，這保證了一定數量的全節點。其次，更重要的是，處理完每筆交易後，我們會把一箇中間狀態樹的根包含進區塊鏈。即使區塊驗證是中心化的，只要有一個誠實的驗證節點存在，中心化的問題就可以通過一個驗證協議避免。如果一個礦工釋出了一個不正確的區塊，這區塊要麼是格式錯，要麼狀態S[n]是錯的。因為S[0]是正確的，必然有第一個錯誤狀態S[i]但S[i-1]是正確的，驗證節點將提供索引i，一起提供的還有處理APPLY(S[i-1],TX[i]) -> S[i]所需的帕特里夏樹節點的子集。這些節點將受命進行這部分計算，看產生的S[i]與先前提供的值是否一致。

另外，更復雜的是惡意礦工釋出不完整區塊進行攻擊，造成沒有足夠的資訊去確定區塊是否正確。解決方案是質疑-迴應協議：驗證節點對目標交易索引發起質疑，接受到質疑資訊的輕節點會對相應的區塊取消信任，直到另外一個礦工或者驗證者提供一個帕特里夏節點子集作為正確的證據。

## 綜述：去中心化應用

 

上述合約機制使得任何一個人能夠在一個虛擬機器上建立通過全網共識來執行命令列應用（從根本上來說是），它能夠更改一個全網可訪問的狀態作為它的“硬碟”。然而，對於多數人來說，用作交易傳送機制的命令列介面缺乏足夠的使用者友好使得去中心化成為有吸引力的替代方案。最後，一個完整的“去中心化應用”應該包括底層的商業邏輯元件【無論是否在以太坊完整實施，使用以太坊和其它系統組合（如一個P2P訊息層，其中一個正在計劃放入以太坊客戶端）或者僅有其它系統的方式】和上層的圖形使用者介面元件。以太坊客戶端被設計成一個網路瀏覽器，但包括對“eth” Javascript API物件的支援，可被客戶端裡看到的特定的網頁用來與以太坊區塊鏈互動。從“傳統”網頁的角度看來，這些網頁是完全靜態的內容，因為區塊鏈和其它去中心化協議將完全代替伺服器來處理使用者發起的請求。最後，去中心化協議有希望自己利用某種方式使用以太坊來儲存網頁。

## 結論

 

以太坊協議最初是作為一個通過高度通用的語言提供如鏈上契約，提現限制和金融合約，賭博市場等高階功能的升級版密碼學貨幣來構思的。以太坊協議將不直接“支援”任何應用，但圖靈完備程式語言的存在意味著理論上任意的合約都可以為任何交易類型和應用創建出來。然而關於以太坊更有趣的是，以太坊協議比單純的貨幣走得更遠，圍繞去中心化儲存，去中心化計算和去中心化預測市場以及數十個類似概念建立的協議和去中心化應用，有潛力從根本上提升計算行業的效率，並通過首次新增經濟層為其它的P2P協議提供有力支撐，最終，同樣會有大批與金錢毫無關係的應用出現。

以太坊協議實現的任意狀態轉換概念提供了一個具有獨特潛力的平臺；與封閉式的，為諸如資料儲存，賭博或金融等單一目的設計的協議不同，以太坊從設計上是開放式的，並且我們相信它極其適合作為基礎層服務於在將來的年份裡出現的極其大量的金融和非金融協議。

## 註解與進階閱讀

### 註解

1.一個有經驗的讀者會注意到事實上比特幣地址是橢圓曲線公鑰的雜湊，而非公鑰本身，然而事實上從密碼學術語角度把公鑰雜湊稱為公鑰完全合理。這是因為比特幣密碼學可以被認為是一個定製的數字簽名演算法，公鑰由橢圓曲線公鑰的雜湊組成，簽名由橢圓曲線簽名連線的橢圓曲線公鑰組成，而驗證演算法包括用作為公鑰提供的橢圓曲線公鑰雜湊來檢查橢圓曲線公鑰，以及之後的用橢圓曲線公鑰來驗證橢圓曲線簽名。

2.技術上來說，前11個區塊的中值。

3.在內部，2和“CHARLIE”都是數字，後一個有巨大的base256編碼格式，數字可以從0到2^256-1。

### 進階閱讀

1. Intrinsic value: https://tinyurl.com/BitcoinMag-IntrinsicValue

2. Smart property: https://en.bitcoin.it/wiki/Smart_Property

3. Smart contracts: https://en.bitcoin.it/wiki/Contracts

4. B-money: http://www.weidai.com/bmoney.txt

5. Reusable proofs of work: http://www.finney.org/~hal/rpow/

6. Secure property titles with owner authority: http://szabo.best.vwh.net/securetitle.html

7. Bitcoin whitepaper: http://bitcoin.org/bitcoin.pdf

8. Namecoin: https://namecoin.org/

9. Zooko’s triangle: http://en.wikipedia.org/wiki/Zooko’s_triangle

10. Colored coins whitepaper: https://tinyurl.com/coloredcoin-whitepaper

11. Mastercoin whitepaper: https://github.com/mastercoin-MSC/spec

12. Decentralized autonomous corporations, Bitcoin Magazine: https://tinyurl.com/Bootstrapping-DACs

13. Simplified payment verification:https://en.bitcoin.it/wiki/Scalability#Simplifiedpaymentverification

14. Merkle trees: http://en.wikipedia.org/wiki/Merkle_tree

15. Patricia trees: http://en.wikipedia.org/wiki/Patricia_tree

16. GHOST: http://www.cs.huji.ac.il/~avivz/pubs/13/btc_scalability_full.pdf

17. StorJ and Autonomous Agents, Jeff Garzik: https://tinyurl.com/storj-agents

18. Mike Hearn on Smart Property at Turing Festival: http://www.youtube.com/watch?v=Pu4PAMFPo5Y

19. Ethereum RLP: https://github.com/ethereum/wiki/wiki/%5BEnglish%5D-RLP

20. Ethereum Merkle Patricia trees: https://github.com/ethereum/wiki/wiki/%5BEnglish%5D-Patricia-Tree

21. Peter Todd on Merkle sum trees:http://sourceforge.net/p/bitcoin/mailman/message/31709140/
22 logan
