---
description: 詳細については、「コンパイラエラー C2008」を参照してください。
title: コンパイラエラー C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 3fcde1885fd752a03a1285470a232f1daaa27df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298527"
---
# <a name="compiler-error-c2008"></a>コンパイラエラー C2008

'character' : マクロ定義内で指定された文字の使い方が間違っています。

マクロ名の直後に文字が表示されます。 このエラーを解決するには、マクロ名の後にスペースが必要です。

次の例では、C2008 が生成されます。

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

考えられる解決策:

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
