---
title: コンパイラ エラー C2431
ms.date: 11/04/2016
f1_keywords:
- C2431
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
ms.openlocfilehash: 6298748b341d58c5d931566f714530a4858e46ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608105"
---
# <a name="compiler-error-c2431"></a>コンパイラ エラー C2431

'identifier' に無効なインデックス レジスタ

ESP レジスタがスケールまたはインデックスとベース レジスタの両方として使用します。 X86 プロセッサで許可するかしないのエンコーディングの兄弟です。

次の例では、C2431 が生成されます。

```
// C2431.cpp
// processor: x86
int main() {
   _asm mov ax, [ESI + 2*ESP]   // C2431
   _asm mov ax, [esp + esp]   // C2431
}
```