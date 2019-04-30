---
title: コンパイラの警告 (レベル 1) C4928
ms.date: 11/04/2016
f1_keywords:
- C4928
helpviewer_keywords:
- C4928
ms.assetid: 77235d7f-9360-45cb-8348-d148c605c4a3
ms.openlocfilehash: 9357e5775e6cfc9a44c43104c4ffd3fd34084e51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393442"
---
# <a name="compiler-warning-level-1-c4928"></a>コンパイラの警告 (レベル 1) C4928

コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。

1 つ以上のユーザー定義の変換ルーチンが見つかりました。 コンパイラでは、このようなすべてのルーチンで、コードが実行されます。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4928 が生成されます。

```
// C4928.cpp
// compile with: /W1
#pragma warning(default: 4928)

struct I
{
};

struct I1 : I
{
};

struct I2 : I
{
};

template <class T>
struct Ptr
{
   operator T*()
   {
      return 0;
   }

   Ptr()
   {
   }

   Ptr(I*)
   {
   }
};

int main()
{
   Ptr<I1> p1;
   Ptr<I2> p2 = p1;   // C4928
   // try one of the following two lines to resolve this error
   // Ptr<I2> p2(p1);
   // Ptr<I2> p2 = (I1*) p1;
}
```