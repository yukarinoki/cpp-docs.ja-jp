---
title: プリプロセッサ演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da6ff2a87007892cb5a76e7fc003e1d172056fb0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-operators"></a>プリプロセッサ演算子
4 つのプリプロセッサ固有の演算子は、`#define` ディレクティブのコンテキストで使用されます (各演算子の概要については、次の一覧を参照)。 文字列化、文字定数化、およびトークン連結演算子については、次の 3 つのセクションで説明します。 詳細について、**定義**演算子を参照してください[#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)です。  
  
|演算子|アクション|  
|--------------|------------|  
|[文字列化演算子 (#)](../preprocessor/stringizing-operator-hash.md)|対応する実引数が二重引用符で囲まれます|  
|[文字定数化演算子 (#@)](../preprocessor/charizing-operator-hash-at.md)|対応する引数が単一引用符で囲まれ、文字として処理されます (Microsoft 固有の仕様)|  
|[トークン連結演算子 (##)](../preprocessor/token-pasting-operator-hash-hash.md)|実引数として使用されるトークンが、他のトークンを形成するために連結されることを許可します|  
|[defined 演算子](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|特定のマクロ ディレクティブで複合式の記述を簡略化します|  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)   
 [定義済みマクロ](../preprocessor/predefined-macros.md)   
 [C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)