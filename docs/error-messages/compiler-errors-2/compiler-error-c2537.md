---
title: コンパイラ エラー C2537 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65db4fa66d147cc46c1a6013d07048892dfa0800
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136024"
---
# <a name="compiler-error-c2537"></a>コンパイラ エラー C2537

'specifier': リンケージの仕様

以下の原因が考えられます。

1. リンケージ指定子がサポートされていません。 "C"リンケージ指定子のみがサポートされています。

1. "C"リンケージは、一連のオーバー ロードされた関数の 1 つ以上の関数に対して指定されます。 これは認められていません。

次の例では、C2537 が生成されます。

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```