---
title: コンパイラの警告 (レベル 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: af091d1d35fff955afcc5af3da48b80416e79f36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385434"
---
# <a name="compiler-warning-level-1-c4731"></a>コンパイラの警告 (レベル 1) C4731

'pointer': フレーム ポインター レジスタが 'の ' 登録インライン アセンブラー コードによって変更されました。

フレーム ポインター レジスタが変更されました。 保存して、インライン アセンブリ ブロックまたはフレーム変数 (ローカルまたは登録の変更に応じて、パラメーター) に登録を復元する必要があります。 またはコードが正しく動作しない可能性があります。

次の例では、C4731 が生成されます。

```
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

EBP フレーム ポインターを (FPO は許可されていません) は、変更されている. ときに`p`は後で参照されている、に対して相対的に参照されている`EBP`します。 `EBP`が、コードで上書きされているため、プログラムが正しく機能しませんし、エラーも可能性があります。