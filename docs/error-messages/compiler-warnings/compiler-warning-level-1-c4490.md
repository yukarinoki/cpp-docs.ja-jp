---
title: コンパイラの警告 (レベル 1) C4490 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4490
dev_langs:
- C++
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baf6c10d50b9b6dd7a41df195dd0b1e39683c98c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4490"></a>コンパイラの警告 (レベル 1) C4490
'override': オーバーライド指定子の不適切な使用'function' が、基本 ref クラスのメソッドと一致しません  
  
 オーバーライド指定子が正しく使用されていません。 たとえば、インターフェイスの関数をオーバーライドしていない、これを実装します。  
  
 詳細については、次を参照してください。[オーバーライド指定子を](../../windows/override-specifiers-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4490 を生成します。  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```