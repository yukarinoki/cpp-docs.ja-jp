---
title: コンパイラ エラー C2019 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2019
dev_langs:
- C++
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6f1ae1b22cca0d00e990f64ccaf469359563f8e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038699"
---
# <a name="compiler-error-c2019"></a>コンパイラ エラー C2019

プリプロセッサ ディレクティブが必要です。'character' が見つかりました

文字の後に、`#`記号はプリプロセッサ ディレクティブの最初の文字ではありません。

次の例では、C2019 が生成されます。

```
// C2019.cpp
#!define TRUE 1   // C2019
```

考えられる解決方法:

```
// C2019b.cpp
// compile with: /c
#define TRUE 1
```