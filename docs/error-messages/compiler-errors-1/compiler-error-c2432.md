---
title: コンパイラ エラー C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: e2983d966a6290ce19713c63feb502c8ffc74bf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631243"
---
# <a name="compiler-error-c2432"></a>コンパイラ エラー C2432

'identifier' の 16 ビットのデータへの参照が正しくありません。

16 ビット レジスタは、インデックスまたはベース レジスタとして使用されます。 コンパイラでは、16 ビットのデータを参照することはできません。 16 ビット レジスタは、32 ビット コードをコンパイルするときに、インデックスまたはベース レジスタとして使用できません。

次の例では、C2432 が生成されます。

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```