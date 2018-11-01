---
title: コンパイラ エラー C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: a9c6465ef87c12135ad4e6709741f0027d8ea3c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638192"
---
# <a name="compiler-error-c2150"></a>コンパイラ エラー C2150

> '*識別子*': ビット フィールドは型 'int'、'signed int' または 'unsigned int' が必要

ビット フィールドの基本型が必要な`int`、 `signed int`、または`unsigned int`します。

## <a name="example"></a>例

このサンプルでは、C2150、発生する方法と解決方法を示します。

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```