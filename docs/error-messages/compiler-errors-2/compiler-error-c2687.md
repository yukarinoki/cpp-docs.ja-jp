---
description: 詳細については、「コンパイラエラー C2687」を参照してください。
title: コンパイラエラー C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: 38996f2f31998ef96dd848915686adb1bf46c987
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220761"
---
# <a name="compiler-error-c2687"></a>コンパイラエラー C2687

' type ': 例外宣言を ' void ' にしたり、不完全な型、ポインター、または不完全な型への参照を意味したりすることはできません

型を例外宣言の一部として使用するには、型が void ではなく定義されている必要があります。

次の例では、C2687 が生成されます。

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

考えられる解決策:

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
