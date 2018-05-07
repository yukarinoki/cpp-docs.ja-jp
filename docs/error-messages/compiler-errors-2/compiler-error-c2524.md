---
title: コンパイラ エラー C2524 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2524
dev_langs:
- C++
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b21a907de69291c6d7fbc23f3ea093271a1ad3b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2524"></a>コンパイラ エラー C2524
'デコンス トラクター': デストラクターまたはファイナライザーには、'void' パラメーター リストが必要です。  
  
 デストラクターまたはファイナライザーがパラメーター リストではない[void](../../cpp/void-cpp.md)です。 その他のパラメーターの型を指定することはできません。  
  
## <a name="example"></a>例  
 次のコードでは、C2524 を再現します。  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## <a name="example"></a>例  
 次のコードでは、C2524 を再現します。  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```