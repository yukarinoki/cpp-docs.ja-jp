---
title: コンパイラ エラー C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638257"
---
# <a name="compiler-error-c2534"></a>コンパイラ エラー C2534

'identifier': コンス トラクターは、値を返すことはできません

コンス トラクターの戻り値または戻り値の型があることはできません (であっても、`void`型を返す)。

このエラーは、削除することによって解決される可能性があります、`return`コンス トラクターの定義からのステートメント。

次の例では、C2534 が生成されます。

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```