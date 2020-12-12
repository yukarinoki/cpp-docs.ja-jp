---
description: 詳細については、「コンパイラエラー C2537」を参照してください。
title: コンパイラ エラー C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 46603ded270b4702d4b7d4de97352547c5f503f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302037"
---
# <a name="compiler-error-c2537"></a>コンパイラ エラー C2537

' 指定子 ': リンケージ指定が正しくありません。

次の原因が考えられます。

1. リンケージ指定子はサポートされていません。 "C" リンケージ指定子のみがサポートされています。

1. オーバーロードされた関数のセット内の複数の関数に対して、"C" リンケージが指定されています。 これは認められていません。

次の例では、C2537 が生成されます。

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
