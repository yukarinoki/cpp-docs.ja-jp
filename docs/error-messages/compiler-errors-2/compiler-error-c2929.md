---
description: 詳細については、「コンパイラエラー C2929」を参照してください。
title: コンパイラ エラー C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: b110615a05a416b6bba7256c7f59f734179677a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320388"
---
# <a name="compiler-error-c2929"></a>コンパイラ エラー C2929

'identifier': 明示的なインスタンス生成。明示的にテンプレート クラス メンバーのインスタンス生成を行ったり抑制したりできません

識別子がインスタンス化できないようになっている間は、識別子を明示的にインスタンス化することはできません。

次の例では C2929 が生成されます。

```cpp
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```
