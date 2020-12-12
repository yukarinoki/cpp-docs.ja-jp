---
description: 詳細については、「コンパイラエラー C2894」を参照してください。
title: コンパイラ エラー C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: dcb5f04cd7cd1ad9d2e6f0d645cabd512ed91c42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270921"
---
# <a name="compiler-error-c2894"></a>コンパイラ エラー C2894

テンプレートを ' C ' リンケージを持つように宣言することはできません

このエラーは、ブロック内で定義されたテンプレートが原因で発生する場合があり `extern "C"` ます。

次の例では、C2894 が生成されます。

```cpp
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

次の例では、C2894 が生成されます。

```cpp
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```
