---
description: '詳細情報: コンパイラの警告 (レベル 1) C4731'
title: コンパイラの警告 (レベル 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: d2041936d7d3c4b7189f57d57ffb1c9f226ea933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228652"
---
# <a name="compiler-warning-level-1-c4731"></a>コンパイラの警告 (レベル 1) C4731

' pointer ': インラインアセンブリコードによって変更されたフレームポインターレジスタ ' register '

フレームポインターレジスタが変更されました。 インラインアセンブリブロックまたはフレーム変数 (変更されたレジスタに応じてローカルまたはパラメーター) に登録を保存して復元する必要があります。または、コードが正しく機能しない可能性があります。

次の例では、C4731 が生成されます。

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP はフレームポインターです (FPO は許可されていません)。変更されています。 `p`が後で参照されると、に対して相対的に参照され `EBP` ます。 しかし、 `EBP` コードによって上書きされているので、プログラムが正常に動作せず、エラーが発生することもあります。
