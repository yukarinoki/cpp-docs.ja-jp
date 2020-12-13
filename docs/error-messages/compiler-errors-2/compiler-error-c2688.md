---
description: 詳細については、「コンパイラエラー C2688」を参照してください。
title: コンパイラエラー C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: 17219fe6f4358b73ace0435e60d8fc2b7a9b6df8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330689"
---
# <a name="compiler-error-c2688"></a>コンパイラエラー C2688

' C2:: fgrv ': 複数のまたは仮想継承を伴う共変の戻り値が varargs 関数でサポートされていません

関数に可変個の引数が含まれている場合 Visual C++ では、共変の戻り値の型はサポートされません。

このエラーを解決するには、関数を定義して、変数の引数を使用しないようにするか、またはすべての仮想関数で戻り値を同じにします。

次の例では、C2688 が生成されます。

```cpp
// C2688.cpp
struct G1 {};
struct G2 {};
struct G3 : G1, G2 {};
struct G4 {};
struct G5 {};
struct G6 : G4, G5 {};
struct G7 : G3, G6 {};

struct C1 {
   virtual G4& fgrv(int,...);
};

struct C2 : C1 {
   virtual G7& fgrv(int,...);   // C2688, does not return G4&
};
```
