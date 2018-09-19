---
title: コンパイラの警告 (レベル 1) C4731 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4731
dev_langs:
- C++
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75117b34e63694cfa6aeec97abf178ff8e61a7da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086487"
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