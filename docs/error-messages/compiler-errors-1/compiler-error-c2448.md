---
description: 詳細については、「コンパイラエラー C2448」を参照してください。
title: コンパイラ エラー C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 8dc6f794a71c89b4b14d0a3f33d5617e296b3dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189614"
---
# <a name="compiler-error-c2448"></a>コンパイラ エラー C2448

' identifier ': 関数スタイル初期化子が関数定義である可能性があります

関数の定義が正しくありません。

このエラーは、旧形式の C 言語の正式リストが原因で発生する場合があります。

次の例では、C2448 が生成されます。

```cpp
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```
