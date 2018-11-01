---
title: コンパイラ エラー C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 3b48bebde6d7baedea73ed181cd4ea33adc44a69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563125"
---
# <a name="compiler-error-c2491"></a>コンパイラ エラー C2491

'識別子': dllimport 関数の定義は許可されていません。

データ、静的データ メンバー、および関数は `dllimport` として宣言できますが、`dllimport` として定義することはできません。

この問題を解決するには、関数の定義から `__declspec(dllimport)` 指定子を削除します。

次の例では警告 C2491 が生成されます。

```
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```