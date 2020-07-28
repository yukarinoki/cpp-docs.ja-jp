---
title: コンパイラ エラー C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 419aa8229e0fe60d391345556c5fbd8be17558d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214738"
---
# <a name="compiler-error-c2150"></a>コンパイラ エラー C2150

> '*identifier*': ビットフィールドの型は ' int '、' signed int '、または ' unsigned int ' である必要があります

ビットフィールドの基本型は、、、またはである必要があり **`int`** **`signed int`** **`unsigned int`** ます。

## <a name="example"></a>例

このサンプルでは、C2150 の発生方法とその修正方法を示します。

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```
