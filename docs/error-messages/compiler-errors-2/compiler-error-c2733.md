---
title: コンパイラ エラー C2733 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc1857cd800dd2d395754b9ae95094d9f57aad27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234190"
---
# <a name="compiler-error-c2733"></a>コンパイラ エラー C2733
C リンケージの 2 番目のオーバー ロードされた関数 'function' が許可されていません  
  
 1 つ以上のオーバー ロードされた関数は C リンケージで宣言します。 C リンケージを使用する場合、指定された関数の 1 つしかは外部できます。 装飾されていない名前が同じであるオーバー ロードされた関数からは、C プログラムで使用できません。  
  
 次の例では、C2733 が生成されます。  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```