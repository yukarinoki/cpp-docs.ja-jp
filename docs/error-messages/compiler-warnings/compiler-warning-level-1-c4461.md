---
title: コンパイラの警告 (レベル 1) C4461 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884daeb7497f6664cecf864ec705891cac62f48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4461"></a>コンパイラの警告 (レベル 1) C4461
'型' : このクラスはファイナライザー 'ファイナライザー' を含んでいますが、デストラクター 'dtor' を含んでいません  
  
 既に型に含まれているファイナライザーは、削除するリソースを暗黙に指定します。 オブジェクトがスコープ外になると、ファイナライザーが型のデストラクターから明示的に呼び出されない限り、共通言語ランタイムがファイナライザーを実行するタイミングを決定します。  
  
 型にデストラクターを定義し、そのデストラクターからファイナライザーを明示的に呼び出す場合は、ファイナライザーを実行するタイミングを決定できます。  
  
 詳細については、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
## <a name="example"></a>例  
 次の例では、C4461 を生成します。  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```