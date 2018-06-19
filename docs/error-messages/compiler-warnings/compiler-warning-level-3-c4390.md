---
title: コンパイラの警告 (レベル 3) C4390 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d052a1fa6124aa1518cddec00566e14668fe111d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290089"
---
# <a name="compiler-warning-level-3-c4390"></a>コンパイラの警告 (レベル 3) C4390
';': 空の被制御文が見つかりました。これを目的としたですか。  
  
 含まれていない命令コントロール ステートメントの後にセミコロンが見つかりました。  
  
 使用する必要がありますマクロにより C4390 を取得する場合、[警告](../../preprocessor/warning.md)プラグマ マクロを含むモジュールで C4390 を無効にします。  
  
 次の例では、C4390 が生成されます。  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```