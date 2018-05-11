---
title: 条件付きコンパイルを指定する A.2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d54245a2df2f38bed2674a3bb3923f8212d35459
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="a2---specifying-conditional-compilation"></a>A.2 条件付きコンパイルの指定
次の例では、OpenMP マクロを使用して条件付きコンパイルの例を示します`_OPENMP`([Section 2.2](../../parallel/openmp/2-2-conditional-compilation.md) 8 ページの)。 OpenMP のコンパイルと、`_OPENMP`マクロが定義になります。  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 定義済みプリプロセッサ演算子は、1 つのディレクティブでテストする 1 つ以上のマクロを使用します。  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```