---
title: コンパイラ エラー C2891 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01741d1cc67f0045c46ab392212625b9e1a2d8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2891"></a>コンパイラ エラー C2891
'parameter': テンプレート パラメーターのアドレスを取得できません  
  
 左辺値である場合を除き、テンプレート パラメーターのアドレスを取得できません。 型パラメーターは、アドレスがないために、左辺値ではありません。 また、左辺値ではないテンプレート パラメーター リスト内の非型の値には、アドレスがありません。 これは、テンプレート パラメーターとして渡された値がコンパイラによって生成されたテンプレート引数のコピーであるために、コンパイラ エラー C2891 を原因となったコードの例です。  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 テンプレート パラメーターなど、参照型の左辺値であることができますが、アドレスを取得します。  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 このエラーを修正するにはなりませんテンプレート パラメーターのアドレスは左辺値である場合を除き。