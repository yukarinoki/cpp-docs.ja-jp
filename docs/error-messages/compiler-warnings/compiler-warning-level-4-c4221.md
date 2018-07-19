---
title: コンパイラの警告 (レベル 4) C4221 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4221
dev_langs:
- C++
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e602eb662533207a1f2957d3b11a0823e4b83af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293196"
---
# <a name="compiler-warning-level-4-c4221"></a>コンパイラの警告 (レベル 4) C4221
使用される標準の拡張機能: 'identifier': 自動変数のアドレスを使用して初期化することはできません  
  
 既定 Microsoft 拡張機能 (/Ze)、集計の型を初期化することができます (**配列**、 `struct`、または**共用体**) ローカル (自動) 変数のアドレスを使用します。  
  
## <a name="example"></a>例  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 このような初期化は ANSI 互換では有効ではありません ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。