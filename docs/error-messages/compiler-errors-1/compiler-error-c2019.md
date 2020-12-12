---
description: 詳細については、「コンパイラエラー C2019」を参照してください。
title: コンパイラエラー C2019
ms.date: 11/04/2016
f1_keywords:
- C2019
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
ms.openlocfilehash: 5b30bdb8eace513572152d0f33da5f591e21bd6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283928"
---
# <a name="compiler-error-c2019"></a>コンパイラエラー C2019

プリプロセッサ ディレクティブが必要です。'character' が見つかりました

文字は符号の後に続きますが、 `#` プリプロセッサディレクティブの最初の文字ではありません。

次の例では、C2019 が生成されます。

```cpp
// C2019.cpp
#!define TRUE 1   // C2019
```

考えられる解決策:

```cpp
// C2019b.cpp
// compile with: /c
#define TRUE 1
```
