---
description: '詳細情報: コンパイラの警告 (レベル 1) C4003'
title: コンパイラの警告 (レベル 1) C4003
ms.date: 11/04/2016
f1_keywords:
- C4003
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
ms.openlocfilehash: d8a581e9cf6152a3e0e92832b36e5f61a94277f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335987"
---
# <a name="compiler-warning-level-1-c4003"></a>コンパイラの警告 (レベル 1) C4003

マクロ 'identifier' に指定された実引数の数が少なすぎます

マクロ定義の仮引数の数が、マクロ内の実際のパラメーターの数を超えています。 マクロの展開では、不足しているパラメーターに対して空のテキストが置き換えられます。

次の例では、C4003 が生成されます。

```cpp
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```
