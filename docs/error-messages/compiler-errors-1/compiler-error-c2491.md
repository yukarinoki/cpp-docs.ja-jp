---
description: 詳細については、「コンパイラエラー C2491」を参照してください。
title: コンパイラ エラー C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 4fd12e30672d7045aa4a7506b35b845e8cd018c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283705"
---
# <a name="compiler-error-c2491"></a>コンパイラ エラー C2491

'識別子': dllimport 関数の定義は許可されていません。

データ、静的データ メンバー、および関数は `dllimport` として宣言できますが、`dllimport` として定義することはできません。

この問題を解決するには、関数の定義から `__declspec(dllimport)` 指定子を削除します。

次の例では警告 C2491 が生成されます。

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```
