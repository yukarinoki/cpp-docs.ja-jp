---
title: コンパイラの警告 (レベル 1) C4293
description: MSVC compiler warning C4293 の原因について説明し、その修正方法を示します。
ms.date: 07/15/2020
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 3b5a05d4a744b084f1cc34210a5374962064e85d
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446477"
---
# <a name="compiler-warning-level-1-c4293"></a>コンパイラの警告 (レベル 1) C4293

> '*operator*': シフト数が負であるか、大きすぎます。未定義の動作です

シフト数が負の値または大きすぎる場合、結果のイメージの動作は未定義になります。

## <a name="remarks"></a>解説

この問題を解決するには、最初のオペランドのキャストを使用して、結果の型のサイズに拡張します。

## <a name="example"></a>例

次の例では、C4293 を生成し、その修正方法を示しています。

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi)
{
   return (hi << 32) | lo;   // C4293

   // In C, try the following line instead:
   // return ( (unsigned __int64)hi << 32) | lo;
   // In C++, try this line instead:
   // return (static_cast<unsigned __int64>(hi) << 32) | lo;
}
```
