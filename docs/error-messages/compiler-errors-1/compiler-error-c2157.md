---
description: 詳細については、「コンパイラエラー C2157」を参照してください。
title: コンパイラ エラー C2157
ms.date: 11/04/2016
f1_keywords:
- C2157
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
ms.openlocfilehash: 4d8619d3d27bd9a1cb0c5323d9fdbf462b043ecf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181319"
---
# <a name="compiler-error-c2157"></a>コンパイラ エラー C2157

'function' : プラグマ リスト内で参照される前に宣言されていなければなりません

[alloc_text](../../preprocessor/alloc-text.md) プラグマの関数の一覧で参照される前に関数名が宣言されていません。

次の例では C2157 が生成されます。

```cpp
// C2157.cpp
// compile with: /c
#pragma alloc_text( "func", func)   // C2157

// OK
extern "C" void func();
#pragma alloc_text( "func", func)
```
