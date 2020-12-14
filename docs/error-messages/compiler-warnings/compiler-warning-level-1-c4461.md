---
description: '詳細情報: コンパイラの警告 (レベル 1) C4461'
title: コンパイラの警告 (レベル 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 2efb92ca26f9e6cf76f7777c8a50ac657f73554d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311007"
---
# <a name="compiler-warning-level-1-c4461"></a>コンパイラの警告 (レベル 1) C4461

'型' : このクラスはファイナライザー 'ファイナライザー' を含んでいますが、デストラクター 'dtor' を含んでいません

既に型に含まれているファイナライザーは、削除するリソースを暗黙に指定します。 オブジェクトがスコープ外になると、ファイナライザーが型のデストラクターから明示的に呼び出されない限り、共通言語ランタイムがファイナライザーを実行するタイミングを決定します。

型にデストラクターを定義し、そのデストラクターからファイナライザーを明示的に呼び出す場合は、ファイナライザーを実行するタイミングを決定できます。

詳細については、「 [デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

## <a name="example"></a>例

次の例では、C4461 が生成されます。

```cpp
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
