---
description: '詳細情報: コンパイラの警告 (レベル 1) C4928'
title: コンパイラの警告 (レベル 1) C4928
ms.date: 11/04/2016
f1_keywords:
- C4928
helpviewer_keywords:
- C4928
ms.assetid: 77235d7f-9360-45cb-8348-d148c605c4a3
ms.openlocfilehash: 15cf688a01ef62b6c76b8be5a61d43d436cfe790
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203615"
---
# <a name="compiler-warning-level-1-c4928"></a>コンパイラの警告 (レベル 1) C4928

コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。

複数のユーザー定義変換ルーチンが見つかりました。 コンパイラは、このようなすべてのルーチンでコードを実行しました。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4928 が生成されます。

```cpp
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
