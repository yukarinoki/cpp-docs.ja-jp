---
title: コンパイラ エラー C2081 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 165217b3ea4d50dc965927419786a01a6cc92af3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166862"
---
# <a name="compiler-error-c2081"></a>コンパイラ エラー C2081
'identifier': 仮パラメーター リストが不正です名前。  
  
 識別子には、構文エラーが発生しました。  
  
 このエラーは、仮パラメーター リストの古いスタイルを使用して、発生することができます。 仮パラメーター リストでは、仮パラメーターの種類を指定する必要があります。  
  
 次の例では、C2081 が生成されます。  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 考えられる解決方法:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```