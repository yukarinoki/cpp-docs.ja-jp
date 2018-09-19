---
title: コンパイラ エラー C2422 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17421f2d4a7823c0e2fbb34a54a7c562223c798c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047032"
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