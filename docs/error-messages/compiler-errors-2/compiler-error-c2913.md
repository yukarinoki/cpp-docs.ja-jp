---
description: 詳細については、「コンパイラエラー C2913」を参照してください。
title: コンパイラ エラー C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: eba6a782c8ec9abe5c13e643d077c81d25d4bf2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270486"
---
# <a name="compiler-error-c2913"></a>コンパイラ エラー C2913

明示的特殊化。' 宣言 ' はクラステンプレートの特殊化ではありません

非テンプレートクラスを特殊化することはできません。

次の例では、C2913 が生成されます。

```cpp
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```
