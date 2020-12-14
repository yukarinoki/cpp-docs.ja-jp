---
description: 詳細については、「コンパイラエラー C2150」を参照してください。
title: コンパイラ エラー C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 5a609edba74e2aee8e0d2a6275fa1ca40fafe5c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223517"
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
