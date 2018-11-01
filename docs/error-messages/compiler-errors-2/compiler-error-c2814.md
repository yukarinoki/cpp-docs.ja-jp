---
title: コンパイラ エラー C2814
ms.date: 11/04/2016
f1_keywords:
- C2814
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
ms.openlocfilehash: 6562e8a0968f83a0e7e968b538b4d94dc1047fa5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474851"
---
# <a name="compiler-error-c2814"></a>コンパイラ エラー C2814

'member' : ネイティブ型をマネージド型または WinRT 型の 'type' の中に入れ子にすることはできません

## <a name="example"></a>例

ネイティブ型を CLR 型または WinRT 型の中に入れ子にすることはできません。 次の例では、C2814 を生成し、その修正方法を示しています。

```
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```
