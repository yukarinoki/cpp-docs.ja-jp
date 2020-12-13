---
description: 詳細については、「コンパイラエラー C3747」を参照してください。
title: コンパイラ エラー C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 9e40b887d5a107eed5e93a7f3827ba4e8c1590e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340204"
---
# <a name="compiler-error-c3747"></a>コンパイラ エラー C3747

既定の型パラメーターがありません: パラメーター param

既定値を持つジェネリックパラメーターまたはテンプレートパラメーターは、既定値を持たないパラメーターによってパラメーターリスト内に配置することはできません。

次の例では、C3747 が生成されます。

```cpp
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

考えられる解決策:

```cpp
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```
