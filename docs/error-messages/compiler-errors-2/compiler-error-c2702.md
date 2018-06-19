---
title: コンパイラ エラー C2702 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2702
dev_langs:
- C++
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 813833b5c3aeb7da0651fecb879ac12ca0713d13
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234646"
---
# <a name="compiler-error-c2702"></a>コンパイラ エラー C2702
_ _except は終了ブロックには表示されない場合があります。  
  
 例外ハンドラー (`__try`/`__except`) 内にネストすることはできません、`__finally`ブロックします。  
  
 次の例では、C2702 が生成されます。  
  
```  
// C2702.cpp  
// processor: x86 IPF  
int Counter;  
int main() {  
   __try {}  
   __finally {  
      __try {}   // C2702  
      __except( Counter ) {}   // C2702  
   }  
}  
```