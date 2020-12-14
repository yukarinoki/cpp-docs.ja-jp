---
description: 詳細については、「コンパイラエラー C3413」を参照してください。
title: コンパイラ エラー C3413
ms.date: 11/04/2016
f1_keywords:
- C3413
helpviewer_keywords:
- C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
ms.openlocfilehash: 1b6f5ba895ce1db433fb8c8366e62ab3c0790f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316246"
---
# <a name="compiler-error-c3413"></a>コンパイラ エラー C3413

'name': 明示的インスタンス化が無効です

不正な形式の明示的なインスタンス化が検出されました。

次の例では C3413 が生成されます。

```cpp
// C3413.cpp
template
class MyClass {};   // C3413
```

考えられる解決策:

```cpp
// C3413b.cpp
// compile with: /c
template <class T>
class MyClass {};

template <>
class MyClass<int> {};
```
