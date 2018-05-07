---
title: コンパイラ エラー C2432 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfbadf2c7d53cce799efbd5f10286b31bb3cd3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2432"></a>コンパイラ エラー C2432
'identifier' での 16 ビット データへの参照が正しくありません。  
  
 16 ビット レジスタは、インデックスまたはベース レジスタとして使用されます。 コンパイラは、16 ビットのデータの参照をサポートしていません。 16 ビット レジスタは、32 ビット コードのコンパイルするときに、インデックスまたはベース レジスタとして使用できません。  
  
 次の例では、C2432 が生成されます。  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```