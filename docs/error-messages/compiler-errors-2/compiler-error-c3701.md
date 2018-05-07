---
title: コンパイラ エラー C3701 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3701
dev_langs:
- C++
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efcf451729ef9ffd869d9fecdc122615e4b40e54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3701"></a>コンパイラ エラー C3701
'function': イベント ソースにイベントがありません  
  
 使用しようとしています。 [event_source](../../windows/event-source.md)をイベント メソッドを持たないクラスにします。 このエラーを解決するには、1 つまたは複数のイベントをクラスに追加します。  
  
 次の例では、C3701 が生成されます。  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```