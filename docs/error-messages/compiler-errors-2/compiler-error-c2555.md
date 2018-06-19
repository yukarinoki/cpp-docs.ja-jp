---
title: コンパイラ エラー C2555 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2d1a710177e2c8c72b0afeff662dddf1c22ef5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230587"
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555
'class1::function1': 仮想関数をオーバーライドする型の戻り値は異なる 'class2::function2' の covariant ではありません  
  
 仮想関数と派生のオーバーライドする関数は、戻り値の型が同一のパラメーター リストにあります。 派生クラスでオーバーライドする関数は、その戻り値の型によってのみ、基底クラスの仮想関数を異なることはできません。  
  
 このエラーを解決するには、仮想関数が呼び出された後に、戻り値をキャストします。  
  
 /Clr でコンパイルする場合にも、このエラーを表示可能性があります。   たとえば、Visual c 次の c# の宣言と同じ。  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 C2555 の詳細については、サポート技術情報記事 Q240862 を参照してください。  
  
 次の例では、C2555 が生成されます。  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```