---
description: '詳細情報: コンパイラの警告 (レベル 1) C4555'
title: コンパイラの警告 (レベル 1) C4555
ms.date: 11/04/2016
f1_keywords:
- C4555
helpviewer_keywords:
- C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
ms.openlocfilehash: e6ef8f5698364e0186dbf6cbf623af96ef2bf7d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265845"
---
# <a name="compiler-warning-level-1-c4555"></a>コンパイラの警告 (レベル 1) C4555

式の影響はありません; 式の副作用が必要です。

この警告は、式が効果を持たない場合に通知します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次に例を示します。

```cpp
// C4555.cpp
// compile with: /W1
#pragma warning(default:4555)

void func1()
{
   1;   // C4555
}

void func2()
{
   int x;
   x;   // C4555
}

int main()
{
}
```
