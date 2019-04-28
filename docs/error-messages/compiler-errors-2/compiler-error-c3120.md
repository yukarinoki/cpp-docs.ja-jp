---
title: コンパイラ エラー C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: 99d6280420111fde1a2e2187e3cbaeb529652d01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281600"
---
# <a name="compiler-error-c3120"></a>コンパイラ エラー C3120

'メソッド名が': インターフェイス メソッドが可変個引数リストを取得できません。

インターフェイス メソッドは、可変個引数リストを取得できません。 たとえば、次のインターフェイス定義には、C3120 が生成されます。

```
// C3120.cpp
__interface A {
int X(int i, ...);    // C3120
};

int main(void) { return(0); }
```