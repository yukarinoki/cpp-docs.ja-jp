---
title: コンパイラ エラー C3697
ms.date: 11/04/2016
f1_keywords:
- C3697
helpviewer_keywords:
- C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
ms.openlocfilehash: 55eadd55af8d4e6f088a0d0eb732d820242cae66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363688"
---
# <a name="compiler-error-c3697"></a>コンパイラ エラー C3697

「修飾子」: この修飾子では使用できません ' ^'

追跡ハンドル (^) は、意図していない修飾子に適用されました。

次の例では、C3697 が生成されます。

```
// C3697.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^__restrict s;   // C3697
   String ^ s2;   // OK
}
```