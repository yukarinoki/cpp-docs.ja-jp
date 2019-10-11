---
title: プリプロセッサの文法
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: f0916e3cc9bbdb398db693286dacc4517df03557
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222262"
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法

*制御線*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *識別子* *トークン-文字列*<sub>選択</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *識別子* **(** &#x2800;識別子&#x200B;<sub></sub> **の**選択... **,** *識別子*&#x200B; <sub></sub>opt&#x2800; **)** *トークン文字列の*<sub>選択</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _パス-仕様_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include**_パス-仕様_ **\<** **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *数字-シーケンス* **"** _ファイル名_ **"** &#x200B;<sub>選択</sub>  \
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *識別子*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *トークン-文字列*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *token-string*

*定数式*: \
&nbsp;&nbsp;&nbsp;&nbsp;**定義済み (** &#x2800;*識別子*&#x2800; **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**定義済み***識別子*\
&nbsp;&nbsp;&nbsp;&nbsp;その他の定数式

*条件*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if-部分* *elif-部分*<sub>選択</sub>*else-パート*<sub>選択</sub>*endif-行*

*if-part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if 行* *テキスト*

*改行*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *定数式*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *識別子*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *identifier*

*elif-parts*: \
&nbsp;&nbsp;&nbsp;&nbsp;*elif 行* *テキスト*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif パーツ* *elif 行* *テキスト*

*elif 行*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *constant-expression*

*else-パート*: \
&nbsp;&nbsp;&nbsp;&nbsp;*他の行* *テキスト*

*他の行*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-行*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*数字-シーケンス*: \
&nbsp;&nbsp;&nbsp;&nbsp;*数値*\
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*digit*: 次のいずれか \
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*トークン文字列*: \
&nbsp;&nbsp;&nbsp;&nbsp;トークンの文字列

*トークン*: \
&nbsp;&nbsp;&nbsp;&nbsp;*キーワード*\
&nbsp;&nbsp;&nbsp;&nbsp;*識別子*\
&nbsp;&nbsp;&nbsp;&nbsp;*定率*\
&nbsp;&nbsp;&nbsp;&nbsp;*operator*\
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*ファイル名*: \
&nbsp;&nbsp;&nbsp;&nbsp;有効なオペレーティングシステムファイル名

*パスの仕様*: \
&nbsp;&nbsp;&nbsp;&nbsp;有効なファイル パス

*テキスト*: \
&nbsp;&nbsp;&nbsp;&nbsp;任意のテキストのシーケンス

> [!NOTE]
> 次の非終端要素は、  *C++言語リファレンス*の[構文規則](../cpp/lexical-conventions.md)(*定数*、*定数式*、*識別子*、*キーワード*、*演算子*、および *) で拡張されています。など*。

## <a name="see-also"></a>関連項目

[文法の概要 (CC++/)](../preprocessor/grammar-summary-c-cpp.md)
