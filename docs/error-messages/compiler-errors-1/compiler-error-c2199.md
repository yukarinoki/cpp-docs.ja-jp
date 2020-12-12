---
description: 詳細については、「コンパイラエラー C2199」を参照してください。
title: コンパイラ エラー C2199
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: e3c1daefb8a8b14c49b42e48c0d46d5a8e638953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278423"
---
# <a name="compiler-error-c2199"></a>コンパイラ エラー C2199

構文エラー: グローバルスコープで ' identifier (' が見つかりました (宣言が意図されていたかどうか)

指定されたコンテキストにより、構文エラーが発生しました。 宣言の構文が正しくありません。

次の例では、C2199 が生成されます。

```cpp
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```
