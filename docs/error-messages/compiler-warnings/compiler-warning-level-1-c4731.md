---
title: コンパイラの警告 (レベル 1) C4731 |Microsoft ドキュメント
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
ms.openlocfilehash: 31bdf972ef3791760469251dc4d0bf19627bded2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283882"
---
# <a name="compiler-warning-level-1-c4731"></a>コンパイラの警告 (レベル 1) C4731
'pointer': フレーム ポインター レジスタ 'register' インライン アセンブラー コードによって変更されました。  
  
 フレーム ポインター レジスタが変更されました。 保存して、インライン アセンブリ ブロックまたはフレーム変数 (ローカルまたはによって変更されたレジスタのパラメーター) に登録を復元する必要がありますか、コードが正しく動作しない可能性があります。  
  
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
  
 EBP が (FPO は許可されていません) フレーム ポインターであり変更しています。 ときに`p`後は、参照、に対する相対参照されている`EBP`です。 しかし、`EBP`が、コードで上書きされているため、プログラムが正しく動作しないもエラーの可能性があります。