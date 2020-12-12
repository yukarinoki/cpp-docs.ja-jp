---
description: '詳細情報: コンパイラの警告 (レベル 4) C4706'
title: コンパイラの警告 (レベル 4) C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: ca614d0ca55dcfa22ec31df78ebe2be904ffd9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208529"
---
# <a name="compiler-warning-level-4-c4706"></a>コンパイラの警告 (レベル 4) C4706

条件式内の代入

条件式のテスト値は、代入の結果でした。

代入には、テスト式など、別の式で合法的に使用できる値 (代入の左側の値) が含まれます。

次の例では、C4706 が生成されます。

```cpp
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

この警告は、テスト条件をかっこで囲んでいる場合でも発生します。

```cpp
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

関係をテストする必要があり、割り当てを行わない場合は、演算子を使用し `==` ます。 たとえば、次の行は、a と b が等しいかどうかをテストします。

```cpp
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

テスト値を割り当ての結果として使用する場合は、代入が0でも null でもないことをテストします。 たとえば、次のコードでは、この警告は生成されません。

```cpp
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
