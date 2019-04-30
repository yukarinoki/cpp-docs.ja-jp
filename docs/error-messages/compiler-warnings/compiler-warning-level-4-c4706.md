---
title: コンパイラの警告 (レベル 4) C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: e57470fcd8e7b014084b094c9ca5e39f0a86d85e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395223"
---
# <a name="compiler-warning-level-4-c4706"></a>コンパイラの警告 (レベル 4) C4706

条件付きの式内の割り当て

条件式のテスト値を代入式の結果をしました。

割り当てには、規則上問題なくテスト式など、別の式で使用できる値 (割り当ての左側にある値) があります。

次の例では、C4706 が生成されます。

```
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

警告は、テスト条件を囲むかっこは 2 倍にする場合でも発生します。

```
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

リレーションシップをテストし、使用して、割り当てしないようにする場合は、`==`演算子。 たとえば、テストの行以下かどうか、b が等しくなります。

```
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

値を代入式の結果、テストを作成する場合は、割り当てが 0 以外、または not null であることを確認するテストします。 たとえば、次のコードでは、この警告が生成されませんされます。

```
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```