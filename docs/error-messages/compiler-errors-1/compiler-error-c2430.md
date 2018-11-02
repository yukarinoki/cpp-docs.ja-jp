---
title: コンパイラ エラー C2430
ms.date: 11/04/2016
f1_keywords:
- C2430
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
ms.openlocfilehash: 754758e652539e4f2d9b12e568b8ef5ccf41d8db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676474"
---
# <a name="compiler-error-c2430"></a>コンパイラ エラー C2430

1 つ以上のインデックスが 'identifier' の登録します。

1 つ以上の登録でスケーリングします。 コンパイラは、インデックスのスケーリングをサポートしていますが、レジスタは 1 つまでしかスケールすることができます。

## <a name="example"></a>例

次の例では、C2430 が生成されます。

```
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```