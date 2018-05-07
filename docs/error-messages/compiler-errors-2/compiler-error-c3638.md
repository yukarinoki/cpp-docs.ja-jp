---
title: コンパイラ エラー C3638 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb1a05323187b4a5dfcc2356da4a1ff8b874de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3638"></a>コンパイラ エラー C3638
'operator': 標準ボックス化とボックス化解除変換演算子を再定義することはできません  
  
 コンパイラでは、暗黙的なボックス化をサポートするために各マネージ クラスの変換演算子を定義します。 この演算子は再定義することはできません。  
  
 詳細については、次を参照してください。[暗黙的なボックス化](../../windows/boxing-cpp-component-extensions.md)です。  
  
 次の例では、C3638 が生成されます。  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```