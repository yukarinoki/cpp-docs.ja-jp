---
title: コンパイラの警告 (レベル 4) C4214 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4214
dev_langs:
- C++
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0efe0666ded5428dcc40a1900f263cfc522a1502
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292923"
---
# <a name="compiler-warning-level-4-c4214"></a>コンパイラの警告 (レベル 4) C4214
使用される標準の拡張機能: int 型以外のフィールド型のビット  
  
 既定 Microsoft 拡張機能 (/Ze)、任意の整数型のビット フィールドの構造体のメンバーができます。  
  
## <a name="example"></a>例  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 このようなビット フィールドは ANSI 互換では無効 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。