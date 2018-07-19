---
title: コンパイラの警告 (レベル 1) C4683 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418bf25d565c616d5bc4aaf58361c4f28df298ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285344"
---
# <a name="compiler-warning-level-1-c4683"></a>コンパイラの警告 (レベル 1) C4683
**'**   
 ***関数*': イベント ソースが 'out' のパラメーター以外の複数のイベント ハンドラーをフックするときに注意**  
  
 1 つ以上のイベント シンクが COM イベント ソースをリッスンしている場合は、out パラメーターの値が無視可能性があります。  
  
 次のような状況で、メモリ リークが発生する注意してください。  
  
1.  メソッドに内部的に割り当てられると、たとえば BSTR を out パラメーターがあるかどうか * です。  
  
2.  イベントに複数のハンドラーがある場合 (はマルチキャスト イベント)  
  
 メモリ リークの原因は、out パラメーターが複数のハンドラーで設定が最後のハンドラーによってのみ、呼び出しサイトに返されることです。  
  
 次の例では、C4683 が生成されます。  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```