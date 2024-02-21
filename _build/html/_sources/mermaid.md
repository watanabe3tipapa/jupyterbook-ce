# mermaid notation

このコンテンツはHTML変換のテスト用に作成しました

---




> 参考URL：https://note.com/_kikiyo_/n/n67ca638d8c5c


```mermaid

classDiagram
    direction TB
    class A["バス"]
    class B["乗客"]

    A"1" o-- "0..40"B

```
---

```mermaid

classDiagram
  direction LR

class A["動物"]{
    # 名前
    # 鳴く()
}
class B["犬"]{
    - 品種
    + 犬情報取得()
}
class C["バス"]{
    - バス会社名
    - 乗員数
    + バス情報取得()
}
class D["タイヤ"]{
    - 型番
    - 利用開始日
    + タイヤ情報取得()
}
class E["乗員"]{
    - 名前
    - 年齢
    + 乗員情報取得()
}
class F["社員"]{
    - 社員番号
    - ユーザー情報
    + 社員情報取得()
}
class G["ユーザー"]{
    - 名前
    - 住所
    + ユーザー情報取得()
}
class J["ホイール"]{
    - 型番
    - 利用開始日
    + ホイール情報取得()
}
class L["犬"]{
    + 鳴く()
}
class M["動物"]{
    + 鳴く()
}
<<interface>> M


A <|-- B :Inheritance(継承・汎化)
C"1" *-- "4"J : Composition(構成要素)
C"1" o-- "0..n"E : Aggregation(集計・集約)
F"1" <--> "1"G : Association(関連)
E -- G : Link (Solid)(特になし)
D"1" ..> "1"J : Dependency(依存)
L ..|> M : Realization(実現)
A .. G : Link(Dot)(特になし)


```

---


```mermaid

journey
    title 新作の服を買うまで
    section 認知・興味
        テレビ、雑誌 : 6 
        インフルエンサー :8 : 広報
    section 情報収集・比較対象
        商品名を検索 : 5 
        購入方法の確認 : 5 : EC
        最安値を探す : 4 : EC
    section 来店・試着
        電車を乗り継ぐ : 3 
        最寄り駅から徒歩で到着 : 3 
        試着する : 5 : 店舗スタッフ
    section 購入
        お得サービスの紹介 : 5 : 店舗スタッフ,総務
        購入 : 6 : 店舗スタッフ


```
---

> 参考URL：https://note.com/_kikiyo_/n/n67ca638d8c5c


### Chart

---

```mermaid

flowchart 

A
B[A]
C[[A]]
D[\A\]
E[/A/]
F[/A\]
G[\A/]
H(A)
I((A))
J(((A)))
L[(A)]
L{A}
M{{A}}
N>A]



```
---

```mermaid
flowchart 

A(開始)
B(終了)
処理1
C[処理2]
D{判断}
E[処理2-2]
F{{準備}}
G1[/外部データ<上にあると入力>/]
G2[/外部データ<下にあると出力>/]
H[[定義<マクロ>]]
I[(データベース)]
J1((結合子A))
J2((結合子A'))
K1[/ループ開始\]
K2[\ループ終了条件式/]

A --> F
F --> K1
K1 --> 処理1
処理1 --> D
D --> E & G1
E --> H
G1 --> C --> G2
G2 & H --> K2 --> B

H　-.- J1
J2 --> マクロ内容開始　--- I --- マクロ内容終了 --> J2



```


---
### excludes

```mermaid
    gantt
    title Git Book renewal
    excludes　sunday,wednesday
    リリース　:2024-03-1,30d

```

---


### Gitgraph Diagrams

```mermaid
---
title: Example Git diagram
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit



```



### Diagrams

```mermaid
C4Context
      title System Context diagram for Internet Banking System
      Enterprise_Boundary(b0, "BankBoundary0") {
        Person(customerA, "Banking Customer A", "A customer of the bank, with personal bank accounts.")
        Person(customerB, "Banking Customer B")
        Person_Ext(customerC, "Banking Customer C", "desc")

        Person(customerD, "Banking Customer D", "A customer of the bank, <br/> with personal bank accounts.")

        System(SystemAA, "Internet Banking System", "Allows customers to view information about their bank accounts, and make payments.")

        Enterprise_Boundary(b1, "BankBoundary") {

          SystemDb_Ext(SystemE, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

          System_Boundary(b2, "BankBoundary2") {
            System(SystemA, "Banking System A")
            System(SystemB, "Banking System B", "A system of the bank, with personal bank accounts. next line.")
          }

          System_Ext(SystemC, "E-mail system", "The internal Microsoft Exchange e-mail system.")
          SystemDb(SystemD, "Banking System D Database", "A system of the bank, with personal bank accounts.")

          Boundary(b3, "BankBoundary3", "boundary") {
            SystemQueue(SystemF, "Banking System F Queue", "A system of the bank.")
            SystemQueue_Ext(SystemG, "Banking System G Queue", "A system of the bank, with personal bank accounts.")
          }
        }
      }

      BiRel(customerA, SystemAA, "Uses")
      BiRel(SystemAA, SystemE, "Uses")
      Rel(SystemAA, SystemC, "Sends e-mails", "SMTP")
      Rel(SystemC, customerA, "Sends e-mails to")

      UpdateElementStyle(customerA, $fontColor="red", $bgColor="grey", $borderColor="red")
      UpdateRelStyle(customerA, SystemAA, $textColor="blue", $lineColor="blue", $offsetX="5")
      UpdateRelStyle(SystemAA, SystemE, $textColor="blue", $lineColor="blue", $offsetY="-10")
      UpdateRelStyle(SystemAA, SystemC, $textColor="blue", $lineColor="blue", $offsetY="-40", $offsetX="-50")
      UpdateRelStyle(SystemC, customerA, $textColor="red", $lineColor="red", $offsetX="-50", $offsetY="20")

      UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")




```

---

^C




