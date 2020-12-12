---
description: 詳細については、「コンパイラエラー C2422」を参照してください。
title: コンパイラ エラー C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 4fb35b7613e523c750d6c3f15a8071117edba46a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120244"
---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422

' オペランド ' に無効なセグメントオーバーライドがあります。

インラインアセンブラーコードで、オペランドに対してセグメントオーバーライド演算子 (コロン) が誤って使用されています。  考えられる原因は次のとおりです。

- 演算子の前のレジスタがセグメントレジスタではありません。

- 演算子の前のレジスタは、オペランドの唯一のセグメントレジスタではありません。

- セグメントのオーバーライド演算子は、間接演算子 (角かっこ) 内に出現します。

- セグメントオーバーライド演算子の後の式は、イミディエイトオペランドまたはメモリオペランドではありません。

次の例では、C2422 が生成されます。

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```
