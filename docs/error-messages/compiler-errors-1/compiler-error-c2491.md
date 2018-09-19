---
title: コンパイラ エラー C2491 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40e6adfc369cd79f4c08c9099f5bc7db2b2281d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110992"
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