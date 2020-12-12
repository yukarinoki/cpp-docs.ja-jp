---
description: 詳細については、「コンパイラエラー C2628」を参照してください。
title: コンパイラエラー C2628
ms.date: 11/04/2016
f1_keywords:
- C2628
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
ms.openlocfilehash: 876e96bfb406262c150807e4e95f14dd5b7177d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123566"
---
# <a name="compiler-error-c2628"></a>コンパイラエラー C2628

' type1 ' の後に続く ' type1 ' は無効です ('; ' を忘れたことがあります)。

セミコロンが欠落している可能性があります。

次の例では、C2628 が生成されます。

```cpp
// C2628.cpp
class CMyClass {}
int main(){}   // C2628 error
```

考えられる解決策:

```cpp
// C2628b.cpp
class CMyClass {};
int main(){}
```
