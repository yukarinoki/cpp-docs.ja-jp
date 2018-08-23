---
title: プリプロセッサの文法 |Microsoft Docs
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
ms.openlocfilehash: 1871d1b8281f4dd74733133ede70ed80430246b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538444"
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
*elif の構成要素の if 部分*opt*else 部分*opt*endif 行*  
  
*if 部分*:  
*if-linetext*  
  
*if 行*:  
**#if**  *constant-expression*  
  
**#ifdef**  *identifier*  
  
**#ifndef**  *identifier*  
  
*elif パーツ*:  
*elif 行のテキスト*  
  
*elif パーツ elif 行のテキスト*  
  
*elif 行*:  
**#elif**  *constant-expression*  
  
*他の部分から成る*:  
*else-linetext*  
  
*他の行*:  
`#else`  
  
*endif 行*:  
`#endif`  
  
*数字シーケンス*:  
*digit*  
  
*digit-sequence digit*  
  
*数字*: のいずれか  
**0 1 2 3 4 5 6 7 8 9**  
  
*トークン文字列*:  
トークンの文字列  
  
*トークン*:  
*keyword*  
  
*identifier*  
  
*constant*  
  
*operator*  
  
`punctuator`  
  
*ファイル名*:  
有効なオペレーティング システム ファイル名  
  
*パス仕様*:  
有効なファイル パス  
  
*テキスト*:  
テキストの任意のシーケンス  
  
> [!NOTE]
> 展開する次の非終端要素、[構文規則](../cpp/lexical-conventions.md)のセクション、 *C++ 言語リファレンス*: `constant`、 `constant` -*式*、*識別子*、*キーワード*、 `operator`、および`punctuator`します。  
  
## <a name="see-also"></a>関連項目  
 
[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)