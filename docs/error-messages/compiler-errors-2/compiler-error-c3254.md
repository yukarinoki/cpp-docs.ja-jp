---
description: 詳細については、「コンパイラエラー C3254」を参照してください。
title: コンパイラ エラー C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7d0084f52060803cd99b973c9f6105fc8915c2aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194216"
---
# <a name="compiler-error-c3254"></a>コンパイラ エラー C3254

' 明示的なオーバーライド ': クラスに明示的なオーバーライド ' override ' が含まれていますが、関数宣言を含むインターフェイスから派生していません

[明示的](../../cpp/explicit-overrides-cpp.md)にメソッドをオーバーライドする場合、オーバーライドを含むクラスは、オーバーライドする関数を含む型から直接的または間接的に派生させる必要があります。

次の例では、C3254 が生成されます。

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```
