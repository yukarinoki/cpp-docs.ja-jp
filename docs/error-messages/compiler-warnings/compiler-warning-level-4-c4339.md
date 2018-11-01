---
title: コンパイラの警告 (レベル 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: bc9d335b3a09f7953a12b388d5bb40cc4d433969
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567766"
---
# <a name="compiler-warning-level-4-c4339"></a>コンパイラの警告 (レベル 4) C4339

'type': 未定義の型の使用が WinRT または CLR meta-data で検出されました。この型を使用するとランタイム例外が起きる可能性があります。

Windows ランタイムまたは共通言語ランタイム用にコンパイルされたコードで、型が定義されていませんでした。 ランタイム例外の可能性を回避するために、型を定義します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では C4339 が生成され、その修正方法が示されています。

```
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```