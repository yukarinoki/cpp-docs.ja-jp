---
title: プリプロセッサの文法 |Microsoft Docs
ms.custom: ''
ms.date: 09/04/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56df4d0bfdaf87ace87a9f9dcbde85166929e642
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766117"
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法

*コントロール行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *識別子**トークン文字列*<sub>選択</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>識別子</em>**(** *識別子*<sub>opt</sub> **、** .**、** *識別子*<sub>opt</sub> **)** *トークン文字列*<sub>選択</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *パス仕様* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *パス仕様* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *数字シーケンス***"** *filename* **"**<sub>選択  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *トークン文字列*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *トークン文字列*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**定義 (** *識別子* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**定義されている***識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;その他の任意の定数式

*条件付き*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if 部分* *elif パーツ*<sub>opt</sub> *else 部分*<sub>opt</sub> *endif 行*

*if 部分*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if 行**テキスト*

*if 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *定数式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *識別子*

*elif パーツ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif 行**テキスト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif パーツ* *elif 行**テキスト*

*elif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *定数式*

*他の部分から成る*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*他の行**テキスト*

*他の行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*endif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*数字シーケンス*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*数字*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*数字シーケンス**桁*

*数字*: のいずれか<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*トークン文字列*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;トークンの文字列

*トークン*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*キーワード*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*定数*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*演算子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*などの区切り記号*

*ファイル名*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;有効なオペレーティング システムのファイル名

*パス仕様*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;有効なファイル パス

*テキスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;テキストの任意のシーケンス

> [!NOTE]
> 展開する次の非終端要素、[構文規則](../cpp/lexical-conventions.md)のセクション、 *C++ 言語リファレンス*:*定数*、*定数式*、*識別子*、*キーワード*、*演算子*、および*などの区切り記号*します。

## <a name="see-also"></a>関連項目

[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)