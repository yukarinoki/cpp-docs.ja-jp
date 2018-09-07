---
title: C.2 規則 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb83b35a03608e272e9af67159b61e5dbf4e1ec6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755022"
---
# <a name="c2-rules"></a>C.2 規則
表記法は、C 規格の 6.1 で説明します。 この文章の付録では、OpenMP C および C++ のディレクティブの基本言語の文法を拡張機能を示します。

**/\* C++ (ISO/IEC 14882:1998) \*/**

*ステートメント seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント seq ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント seq openmp ディレクティブ*

**/\* C90 で (ISO/IEC 9899:1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント list ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメントの一覧の openmp ディレクティブ*

**/\* C99 (ISO/IEC 9899:1999) \*/**

*ブロック アイテム*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*宣言*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*

**/\* 標準的なステートメント \*/**

*statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp コンストラクト*

*openmp コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列のコンス トラクター*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクションのコンス トラクター*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*1 つのコンス トラクター*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列-for のコンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列のセクションでは、コンス トラクター*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*critical コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*順序付けのコンス トラクター*

*openmp ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*barrier ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*flush ディレクティブ*

*構造化ブロック*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント*

*並列構造*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列ディレクティブ構造化ブロック*

*並列ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp parallel** *並列句*<sub>optseq</sub> *新しい行*

*並列句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*一意な並列句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*

*並列句では一意*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**場合 (** *式* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**num_threads (** *式* **)**

*コンス トラクターの*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*イテレーション ステートメントの for ディレクティブ*

*ディレクティブの*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp** *for 句*<sub>optseq</sub> *新しい行*

*for 句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for 句一意*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*for 句一意*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**順序付け**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**スケジュール (** *スケジュールの種類* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**スケジュール (** *スケジュールの種類* **、** *式* **)**

*スケジュールの種類*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**静的**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**動的**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ガイド付き**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ランタイム**

*セクションのコンス トラクター*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション ディレクティブのセクションのスコープ*

*セクション ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp セクション***セクション句*<sub>optseq</sub> *新しい行*

*セクション句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*セクション スコープ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{0} セクション シーケンス}*

*セクション シーケンス*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション ディレクティブ*<sub>opt</sub> *構造化ブロック*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション シーケンス構造セクション ディレクティブのブロック*

*セクション ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp セクション***新しい行*

*1 つのコンス トラクター*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*単一ディレクティブ構造化ブロック*

*単一ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 つの # プラグマ omp** *単一句*<sub>optseq</sub> *新しい行*

*単一句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*並列のコンストラクトの*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ディレクティブの並列の繰り返しステートメント*

*並列-ディレクティブの*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp の並列***並列-句の*<sub>optseq</sub> *新しい行*

*並列-句の*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*一意な並列句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for 句一意*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*

*並列のセクションでは、コンス トラクター*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列のセクションでは、ディレクティブのセクション スコープ*

*ディレクティブのセクションでは並列*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp parallel セクション***句のセクションでは並列*<sub>optseq</sub> *新しい行*

*句のセクションでは並列*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*一意な並列句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*データ句*

*マスター コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master ディレクティブ構造化ブロック*

*master ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp マスター** *新しい行*

*critical コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*critical ディレクティブ構造化ブロック*

*critical ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp の重要な***リージョン語句*<sub>opt</sub> *新しい行*

*リージョン語句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(識別子)*

*barrier ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp バリア***新しい行*

*atomic コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic ディレクティブの式ステートメント*

*atomic ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp atomic** *新しい行*

*flush ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp フラッシュ***フラッシュ var*<sub>opt</sub> *新しい行*

*フラッシュ var*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(変数リスト)*

*順序付けられたコンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ordered ディレクティブ構造化ブロック*

*ordered ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp 注文***新しい行*

**/\* 標準の宣言 \*/**

*宣言*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate ディレクティブ*

*threadprivate ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# プラグマ omp threadprivate (** *変数一覧***)** *新しい行* 

*データ句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**プライベート (** *変数一覧* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyprivate (***変数一覧***)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**firstprivate (***変数一覧***)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**lastprivate (** *変数一覧***)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**共有 (** *変数一覧* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**既定の (共有)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**既定 (なし)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**削減 (***減少演算子***:***変数一覧***)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyin (***変数一覧***)** 

*減少演算子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;いずれか:  **+  \* -(& a) ^ &#124; (& a) (& a)&#124;&#124;**

**/\* C で \*/**

*変数リスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*変数リスト* **、** *識別子*

**/\* C++ では \*/**

*変数リスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id 式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*変数リスト* **、** *id 式*