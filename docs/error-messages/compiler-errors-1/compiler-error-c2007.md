---
description: 詳細については、「コンパイラエラー C2007」を参照してください。
title: コンパイラエラー C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: fa2ad780269079ef081f22d2c222e106443200e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298488"
---
# <a name="compiler-error-c2007"></a>コンパイラエラー C2007

\#構文の定義

の後に識別子は表示されません `#define` 。 このエラーを解決するには、識別子を使用します。

次の例では、C2007 が生成されます。

```cpp
// C2007.cpp
#define   // C2007
```

考えられる解決策:

```cpp
// C2007b.cpp
// compile with: /c
#define true 1
```
