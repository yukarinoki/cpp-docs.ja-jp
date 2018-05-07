---
title: 致命的なエラー C1311 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53b3759a5fec4b072f9a9b300670d61cb0d101c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1311"></a>致命的なエラー C1311
COFF 形式は、'var' をアドレスの数バイトと共に静的に初期化できません。  
  
 型に 4 バイト未満の記憶域を持つ変数に、コンパイル時に値を持つことはできません、アドレスを静的に割り当てられたことはできません。  
  
 このエラーは、それ以外の場合は、コードで発生する可能性が有効な C++ です。  
  
 次の例では、C1311 を引き起こす可能性のある 1 つの条件を示します。  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```