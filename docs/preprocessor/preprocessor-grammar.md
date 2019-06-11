---
title: プリプロセッサの文法
ms.date: 09/04/2018
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: 6177cf5fddba549e410842ef3f270edcc13d4782
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179881"
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法

*コントロール行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *identifier* *token-string*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#define** <em>identifier</em> **(** *identifier*<sub>opt</sub> **,** ... **,** *identifier*<sub>opt</sub> **)** *token-string*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** *path-spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *digit-sequence*  **"** *filename* **"** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *token-string*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *token-string*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**defined(** *identifier* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**定義されている** *識別子*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;その他の任意の定数式

*条件付き*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if 部分* *elif パーツ*<sub>opt</sub> *else 部分*<sub>opt</sub> *endif 行*

*if 部分*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if 行* *テキスト*

*if 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *constant-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *identifier*

*elif パーツ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif 行* *テキスト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif パーツ* *elif 行* *テキスト*

*elif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *constant-expression*

*他の部分から成る*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*else-line* *text*

*他の行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*数字シーケンス*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*数字*: のいずれか<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*トークン文字列*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;トークンの文字列

*トークン*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*keyword*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*operator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

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