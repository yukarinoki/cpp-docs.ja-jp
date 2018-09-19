---
title: コンパイラの警告 (レベル 1) C4461 |Microsoft Docs
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
ms.openlocfilehash: 86c12208c6992b97f30bc36ea821ba26148ff751
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081400"
---
# <a name="compiler-warning-level-1-c4461"></a>コンパイラの警告 (レベル 1) C4461

'型' : このクラスはファイナライザー 'ファイナライザー' を含んでいますが、デストラクター 'dtor' を含んでいません

既に型に含まれているファイナライザーは、削除するリソースを暗黙に指定します。 オブジェクトがスコープ外になると、ファイナライザーが型のデストラクターから明示的に呼び出されない限り、共通言語ランタイムがファイナライザーを実行するタイミングを決定します。

型にデストラクターを定義し、そのデストラクターからファイナライザーを明示的に呼び出す場合は、ファイナライザーを実行するタイミングを決定できます。

詳細については、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

## <a name="example"></a>例

次の例では、C4461 が生成されます。

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