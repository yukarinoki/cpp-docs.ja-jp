---
title: コンパイラ エラー C2589 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15589358979f554a9c17114f7d78b05dd83c472
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230754"
---
# <a name="compiler-error-c2589"></a>コンパイラ エラー C2589
'identifier': の右側に無効なトークン ':: '  
  
 クラス、構造体、または共用体の名前が、スコープ解決演算子 (ダブル コロンを含む) の左側に表示された場合、右側のトークンは、クラス、構造体、または共用体のメンバーにする必要があります。 それ以外の場合、任意のグローバル識別子は、右側に表示できます。  
  
 スコープ解決演算子をオーバー ロードできません。  
  
 次の例では、C2589 が生成されます。  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```