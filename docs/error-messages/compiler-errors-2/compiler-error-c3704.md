---
title: コンパイラ エラー C3704 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3b1f255852def5e04d75751b0a902fb7072545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264143"
---
# <a name="compiler-error-c3704"></a>コンパイラ エラー C3704
'function': vararg メソッドは、イベントを発生させることはできません  
  
 使用しようとしています。 [_ _event](../../cpp/event.md) vararg メソッドにします。 このエラーを解決するには、置換、`fireEvent(int i, ...)`を呼び出して、`fireEvent(int i)`次のコード サンプルで示すように呼び出します。  
  
 次の例では、C3704 が生成されます。  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```