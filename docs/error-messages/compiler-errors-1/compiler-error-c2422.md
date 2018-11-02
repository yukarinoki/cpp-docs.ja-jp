---
title: コンパイラ エラー C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 524eeadb6cf066d3eba3a7e88c45a9e2b993c0ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509136"
---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422

'オペランド' で誤ったセグメント オーバーライド

インライン アセンブラー コードで使用するオペランドに対してセグメント オーバーライド演算子 (コロン)  以下の原因が考えられます。

- 演算子の直前のレジスタは、セグメントの登録ではありません。

- 演算子の直前のレジスタは、オペランド内の唯一のセグメント レジスタではありません。

- 間接演算子 (角かっこ) 内でセグメント オーバーライド演算子が表示されます。

- 次のセグメントのオーバーライド演算子式は、即時のオペランドまたはメモリ オペランドではありません。

次の例では、C2422 が生成されます。

```
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```