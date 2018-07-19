---
title: コンパイラ エラー C2032 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1db268222f3b9f7ca6f9ce297680866185e6661d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167217"
---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032
'identifier': 関数 'structorunion' の構造体/共用体のメンバーであることはできません  
  
 構造体または共用体が C ではありませんが、C++ では許可されているメンバー関数エラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。  
  
 次の例では、C2032 が生成されます。  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 考えられる解決方法:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```