---
title: プリプロセッサの文法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: d14a3e00e18a2d3ac69dd472ac4056a379ada224
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法
**#define**  *identifier* *token-string*opt  
  
 *#* **define**  *identifier*[**(** *identifier*opt **,** *...* **,** *identifier*opt **)**] *token-string*opt  
  
 **defined(**  *identifier* **)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path-spec***"**  
  
 `#include` **\<***path-spec***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"** opt  
  
 *#* **undef**  *identifier*  
  
 **#error**  *token-string*  
  
 **#pragma**  *token-string*  
  
 *条件付き*:  
 *if 部分 elif パーツ*opt*else 部分*opt*endif 行*  
  
 *if 部分*:  
 *if-linetext*  
  
 *if 行*:  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif パーツ*:  
 *elif 行のテキスト*  
  
 *elif パーツ elif 行テキスト*  
  
 *elif 行*:  
 **#elif**  *constant-expression*  
  
 *他の部分から成る*:  
 *else-linetext*  
  
 *else 行*:  
 `#else`  
  
 *endif 行*:  
 `#endif`  
  
 *桁シーケンス*:  
 *digit*  
  
 *digit-sequence digit*  
  
 *桁*: のいずれか  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *トークン文字列*:  
 トークンの文字列  
  
 *トークン*:  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 有効なオペレーティング システム ファイル名  
  
 *パス spec* :  
 有効なファイル パス  
  
 *テキスト*:  
 テキストの任意のシーケンス  
  
> [!NOTE]
>  次の非終端はでは展開、[構文規則](../cpp/lexical-conventions.md)のセクションで、 *C++ 言語リファレンス*: `constant`、 `constant` -*式*、*識別子*、*キーワード*、 `operator`、および`punctuator`です。  
  
## <a name="see-also"></a>関連項目  
 [文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)