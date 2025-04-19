# 📚Java-了解Java的起源與發展、特性、優勢

Java 是由 Sun Microsystems 於 1995 年發表的高階程式語言。(由James Gosling 及 其團隊於1991年開始開發)（現已被Oracle收購）

開發目標：一種簡單、可靠、安全且跨平台的程式語言 → 原本的開發目的是為了數位家電（例如智慧電視）打造一套可攜式的程式語言。

Java 的最大特色是「Write Once, Run Anywhere（一次編寫，到處運行）」，因為它運行在 JVM（Java Virtual Machine）之上，與平台無關。


# Java的標誌 : 名字本身就是來自咖啡。Java 是印尼爪哇島（Java Island）的名字，那裡盛產咖啡豆。
當初開發團隊在為這個語言取名字時，就一邊喝咖啡☕一邊討論，所以咖啡杯圖案就成了 Java 的象徵。😃

# 🕰️ Java 版本演進整理 : (GPT彙整)
| 版本            | 發布年份| 主要特性與里程碑                                            |
|-----------------|--------|-----------------------------------------------------------|
| **JDK 1.0**     | 1996   | Java 誕生，支援 applet、小型網頁程式                        |
| **JDK 1.1**     | 1997   | 增加內部類別（Inner Class）、JavaBeans                      |
| **J2SE 1.2**    | 1998   | 被稱為 Java 2，加入 Swing GUI、Collections Framework       |
| **J2SE 1.3**    | 2000   | 改善效能、導入 HotSpot JVM                                 |
| **J2SE 1.4**    | 2002   | 正規表示式（Regex）、NIO                                    |
| **Java SE 5.0** | 2004   | 泛型（Generics）、enum、foreach、註解（Annotation           |
| **Java SE 6**   | 2006   | 增強 Web Services、腳本引擎支援（如 JavaScript）           |
| **Java SE 7**   | 2011   | try-with-resources、數字語法改善                          |
| **Java SE 8**   | 2014   | 🔥 Lambda 表達式、Stream API、新的時間 API（java.time）   |
| **Java SE 9**   | 2017   | 模組系統（Jigsaw）                                       |
| **Java SE 10**  | 2018   | `var` 型別推斷                                           |
| **Java SE 11**  | 2018   | 📌 LTS（長期支援版）、正式加入 HTTP Client API            |
| **Java SE 17**  | 2021   | 📌 LTS 版本，Sealed Classes、Pattern Matching           |
| **Java SE 21**  | 2023   | 📌 最新 LTS，虛擬執行緒（Virtual Threads）、效能優化等     |
# Oracle改為每六個月發布一個新版本，每三年一個LTS版本
### 💡 小筆記：
- Java 每 6 個月更新一次版本。
- 長期支援版（LTS）目前推薦使用：**Java 17 或 Java 21**。
- Java 被廣泛用於：後端開發、Android App、企業應用系統等。
- ❗ ❗ 題外話 : 面試時可詢問企業目前採用何種Java版本?「請問貴公司目前 Java 的開發環境是採用哪個版本？有規劃往新版（例如 Java 17、21）升級嗎？❗ ❗ 

  要對 Java 有版本差異的認知

  如果我知道不同版本有不同語法特性、效能差異、甚至安全性更新。
  例如 Java 8 的 Lambda 跟 Stream、Java 11 是 LTS、Java 17 支援 Sealed Classes 等。

  注意到實務開發環境的細節，代表自己不光只會寫程式，而是要有意識到實務中的部署、升級、維護等情況。

  若公司還停留在舊版（例如 Java 8），那可能面臨升級需求，這會影響自己的技術學習曲線。

  重視開發文化與更新節奏，間接了解公司是否有跟上技術潮流？是否願意持續更新技術堆疊？

  如果公司還在用非常舊的版本（如Java 6、7），可能代表技術債多或資源緊繃。😟😟😟

# ☕ Java 的特性與優勢
| 特性 | 說明 |
|------|------|
| 📌1. 平台獨立性 | Java 程式可在任何支援 JVM 的作業系統執行。口號是「Write Once, Run Anywhere」。😝 |
| 📌2. 物件導向（OOP） | 所有程式皆以類別（class）為單位設計，有封裝、繼承、多型等特性。 |
| 📌3. 自動垃圾回收（Garbage Collection） | JVM 負責記憶體管理，釋放不再使用的記憶體空間，減少記憶體洩漏問題。😮 |
| 📌4. 多執行緒支援（Multithreading） | 可同時處理多個任務，提高執行效率。 |
| 📌5. 安全性高（Security） | JVM 提供沙箱機制、防止惡意程式存取系統資源；也支援加密與數位簽章。 |
| 📌6. 穩定且可擴充 | Java 在企業級系統廣泛使用，架構清晰，適合建構大型應用程式。 |
| 📌7. 擁有龐大的生態系 | 有完整的標準函式庫（API）、開發框架（Spring、Hibernate 等）和大量開源資源。 |


來學習一下GC概念，🔍 程式碼解析如下
| 範例程式碼：Java 垃圾回收 |
|---------------------------|
public class GCDemo {
    public static void main(String[] args) {
        Object obj1 = new Object(); // 建立一個 Object 物件，obj1 指向它
        Object obj2 = new Object(); // 建立另一個 Object 物件，obj2 指向它
        obj1 = null;                // obj1 不再指向原本的物件（變成垃圾）
        obj2 = obj1;                // obj2 現在也變成 null，原本的第二個物件也變成垃圾
    }
}
✅ 結果：兩個物件都變成了「無人參考的垃圾」，等待 JVM 的 GC 回收！|

# ☕ Java 的跨平台特性解析
Java 程式只需要撰寫一次，不用針對每一種作業系統分別開發，就能在多種作業系統上執行，例如：

Windows、macOS、Linux、Unix、Android

→ 關鍵在於 JVM（Java Virtual Machine）Java 虛擬機器。

Java 程式會先被編譯成 .class 檔（bytecode，位元碼）

.class 檔不是針對某一種作業系統，而是針對 JVM

JVM 負責「解譯並執行」bytecode，在不同平台上裝 JVM，就能跑 Java 程式

Java Code (.java)

   ⬇ 編譯

Bytecode (.class)

   ⬇JVM 解譯

Run on: Windows / macOS / Linux ...

📌 換句話說：

Java 程式 ➜ 編譯成 bytecode ➜ JVM 幫你跑 ➜ 不受平台限制！👍

🧠 小補充：那為什麼其他語言（像 C/C++）無法跨平台？

C/C++ 是直接編譯成對應平台的機器碼（native code），要在不同平台上執行，需要針對每個作業系統重新編譯。

而 Java 編譯成中間碼（bytecode），交由 JVM 處理平台相容的細節，所以程式本身不需要改動。

所以說Java的優勢(總結)

📌程式可重複使用 : 不需要針對不同平台重新編譯

📌開發成本降低 : 降低了維護成本與學習成本

📌強化系統穩定性 : 龐大的向後兼容性考量

📌廣泛應用於企業級系統 : 舊版本編寫的程式幾乎都能在新版本上運行

📌安全性 : 不支持直接的指針操作，避免記憶體意外訪問

📌自動垃圾回收（GC）減少記憶體泄漏風險


動動腦🧠

1️⃣ 下列哪項不是 Java 的主要特性？

a) 跨平台

b) 物件導向

c) 指針操作

d) 自動垃圾回收


📌 解析：

✅答案是C，Java 不支援直接的指針操作（不像 C/C++），這是為了提升安全性與簡化記憶體管理。

雖然底層仍有記憶體操作，但在語言層級中，Java 是不允許開發者使用指針的。

2️⃣ Java 的跨平台特性主要依靠：

a) 編譯器

b) JVM

c) JDK

d) 操作系統

📌 解析：

✅答案是b，Java 程式會編譯成 bytecode（位元碼），由 JVM（Java Virtual Machine） 在各平台執行，實現「一次編寫，到處執行（Write Once, Run Anywhere）」的特性。

3️⃣ Java 程式編譯後產生的檔案格式是：

a) .exe

b) .jar

c) .class

d) .java

📌 解析：

✅答案是C

.java 是原始碼檔案，經 javac 編譯後，會產生 .class 檔 → 裡面是 JVM 可以識別的 bytecode。

.jar 則是用來打包 .class 檔與相關資源的壓縮格式（Java Archive）。

🧠 我的理解與反思：

Java的設計邏輯讓我覺得有條不紊，能夠在不同作業系統上執行相同程式碼，對於企業開發來說很重要!

雖然現在有GPT、AI、各種程式語言出現，但Java穩定性、廣泛應用及強大的社群資源，仍是值得作為必修的程式語言。

對於我這個零基礎的小白來說，必須得花很多時間好好了解，打下扎實的基礎，以利於後續深度的學習與應用，最重要的就是做中學。


