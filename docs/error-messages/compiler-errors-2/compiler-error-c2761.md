---
title: コンパイラ エラー C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 1236cfaf70781b6ca80db1a317a0c1b01b0f2740
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228233"
---
# <a name="compiler-error-c2761"></a>コンパイラ エラー C2761

'function': メンバー関数の再宣言できません

メンバー関数を再宣言することはできません。 それを定義できますが、再宣言はできません。

## <a name="example"></a>例

次の例では、C2761 が生成されます。

```
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

## <a name="example"></a>例

クラスまたは構造体の非静的メンバーを定義することはできません。  次の例では、C2761 が生成されます。

```
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```