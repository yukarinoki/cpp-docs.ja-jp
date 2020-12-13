---
description: '詳細情報: .C C と C++ の文法'
title: C. OpenMP C と C++ の文法
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 9543d721afbff1069b5497ba8dc7092089a1b706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342505"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C と C++ の文法

[C.1 表記](#c1-notation)<br/>
[C.2 規則](#c2-rules)

## <a name="c1-notation"></a>C.1 表記

文法規則は、非ターミナルの名前と、その後にコロンを付けたもので構成され、その後に別の行で代替候補が続きます。

構文式の<sub>選択</sub> 候補は、置換で用語が省略可能であることを示します。

構文式 *用語*<sub>の optseq</sub> は、次の追加の規則を使用した *用語シーケンス*<sub>選択</sub> に相当します。

*用語のシーケンス*:  
&nbsp;&nbsp;&nbsp;&nbsp;*句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*用語-seq* *語*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*用語-シーケンス* `,`*用語*   

## <a name="c2-rules"></a>C.2 規則

この表記は、C 標準のセクション6.1 で説明されています。 この文法付録では、OpenMP C および C++ ディレクティブの基本言語文法の拡張について説明します。

**/\* C++ (ISO/IEC 14882:1998) \*/**

*ステートメント-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント-seq ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメント-seq openmp ディレクティブ*

**/\* C90 (ISO/IEC 9899:1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメントリストステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ステートメントリスト openmp ディレクティブ*

**/\* C99 (ISO/IEC 9899:1999) \*/**

*ブロック項目*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp ディレクティブ*

**/\* 標準ステートメント \*/**

*statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp コンストラクト*

*openmp コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*単一コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列セクション-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*マスター-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*重大-コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic コンストラクト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ordered-コンストラクト*

*openmp ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*バリア-ディレクティブ*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*flush ディレクティブ*

*構造化ブロック*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*並列コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列ディレクティブの構造化ブロック*

*並列ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel`*並列句の*<sub>optseq</sub> *改行*

*parallel 句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*

*unique-parallel 句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (`*式*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (`*式*   `)`

*-コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ディレクティブの反復ステートメント*

*ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for`*for 句*<sub>optseq</sub> *改行*

*for 句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*unique-句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*スケジュール-種類*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*スケジュール-種類* `,`*式*      `)`

*スケジュール-種類*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*セクション-コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション-ディレクティブセクション-スコープ*

*セクション-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections`*セクション-句*<sub>optseq</sub> *改行*

*セクション-句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*セクション-スコープ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{section-sequence}*

*セクション-シーケンス*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション-ディレクティブ*<sub>opt</sub> *構造化ブロック*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*セクション-シーケンスセクション-ディレクティブの構造化ブロック*

*セクション-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section`*改行*

*単一コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*単一ディレクティブの構造化ブロック*

*シングルディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single`*単一句の*<sub>optseq</sub> *改行*

*単一句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*parallel-コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列ディレクティブの反復ステートメント*

*並列ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for`*並列句の*<sub>optseq</sub> *の改行*

*parallel-句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*

*並列セクション-コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*並列セクション-ディレクティブセクション-スコープ*

*並列セクション-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections`*並列セクション-句*<sub>optseq</sub> *改行*

*並列セクション-句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel 句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 句*

*マスター-コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*マスターディレクティブの構造化ブロック*

*マスターディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master`*改行*

*重大な構成*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*重大なディレクティブの構造化ブロック*

*重大なディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical`*リージョンフレーズの*<sub></sub> *改行*

*地域-語句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*識別子*

*バリア-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier`*改行*

*atomic コンストラクト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic ディレクティブ式-ステートメント*

*atomic ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic`*改行*

*flush ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush`*フラッシュ-変数* を <sub>選択</sub> します。

*フラッシュ変数*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(変数リスト)*

*順序付け* された構造:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*順序付きディレクティブの構造化ブロック*

*ordered-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered`*改行*

**/\* 標準の宣言 \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate-ディレクティブ*

*threadprivate-ディレクティブ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (`*変数リスト* `)`*改行*    

*data 句*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (`*変数リスト*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *変数リスト*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *変数リスト*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (`*変数リスト*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (`*変数リスト*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *リダクション演算子* `:`*変数リスト*          `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *変数リスト*    `)`

*リダクション演算子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;次のいずれか:   `+ \* - & ^ | && ||`

**/\* C の場合 \*/**

*変数リスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*変数リスト* `,`*識別子*   

**/\* C++ の \*/**

*変数リスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id-式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*変数リスト* `,`*id-式*   
