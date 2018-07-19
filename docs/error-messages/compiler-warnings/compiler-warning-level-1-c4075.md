---
title: コンパイラの警告 (レベル 1) C4075 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4075
dev_langs:
- C++
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9a0d9fb3808af9ed05454b5b07d471303abc654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282884"
---
# <a name="compiler-warning-level-1-c4075"></a>コンパイラの警告 (レベル 1) C4075
初期化子が不明な初期化領域にあります。  
  
 [#pragma init_seg](../../preprocessor/init-seg.md) が認識できないセクション名を使用しています。 コンパイラはこの **pragma** コマンドを無視します。  
  
 次の例では C4075 が生成されます。  
  
```  
// C4075.cpp  
// compile with: /W1  
#pragma init_seg("mysegg")   // C4075  
  
// try..  
// #pragma init_seg(user)  
  
int main() {  
}  
```