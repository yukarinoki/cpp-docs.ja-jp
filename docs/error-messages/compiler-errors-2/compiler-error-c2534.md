---
title: コンパイラ エラー C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386968"
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