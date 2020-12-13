---
description: 詳細については、「コンパイラエラー C2761」を参照してください。
title: コンパイラエラー C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 624a375aedc78b6d63f3a6c5a1185edfade28c7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336152"
---
# <a name="compiler-error-c2761"></a>コンパイラエラー C2761

' function ': メンバー関数の再宣言は許可されていません

メンバー関数を再宣言することはできません。 これは定義できますが、再宣言することはできません。

## <a name="examples"></a>例

次の例では、C2761 が生成されます。

```cpp
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

クラスまたは構造体の非静的メンバーを定義することはできません。  次の例では、C2761 が生成されます。

```cpp
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```
