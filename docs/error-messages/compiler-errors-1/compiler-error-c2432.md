---
description: 詳細については、「コンパイラエラー C2432」を参照してください。
title: コンパイラ エラー C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: 392108e0fd16952bc8bcf43682dc163c664171ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190017"
---
# <a name="compiler-error-c2432"></a>コンパイラ エラー C2432

' identifier ' の16ビットデータへの無効な参照です

16ビットレジスタは、インデックスまたはベースレジスタとして使用されます。 コンパイラは、16ビットデータの参照をサポートしていません。 32ビットコードをコンパイルするときに、16ビットレジスタをインデックスまたは基本レジスタとして使用することはできません。

次の例では、C2432 が生成されます。

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
