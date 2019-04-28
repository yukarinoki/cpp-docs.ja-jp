---
title: コンパイラ エラー C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 6492dfffbb5a2f80ea543d4248c0f77759c0a521
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303607"
---
# <a name="compiler-error-c2021"></a>コンパイラ エラー C2021

'character' でなく指数の値が必要です

浮動小数点定数の指数として使用される文字は、有効な数値ではありません。 指数が範囲内を使用してください。

## <a name="example"></a>例

次の例では、C2021 が生成されます。

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>例

考えられる解決方法:

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```