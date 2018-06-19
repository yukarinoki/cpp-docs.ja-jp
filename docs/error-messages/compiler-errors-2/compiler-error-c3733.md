---
title: コンパイラ エラー C3733 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3733
dev_langs:
- C++
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7d5531bf9eb7352f1866bc0800734a78261b585
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266631"
---
# <a name="compiler-error-c3733"></a>コンパイラ エラー C3733
'event': COM イベントを指定するための構文が正しくありません'_ _interface' を忘れましたか。  
  
 COM イベントの間違った構文が使用されました。 このエラーを解決するには、イベントの種類を変更または COM イベントの規則に準拠する構文を修正します。  
  
 次の例では、C3733 が生成されます。  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```