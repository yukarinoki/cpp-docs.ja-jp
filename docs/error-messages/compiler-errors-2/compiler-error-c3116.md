---
title: コンパイラ エラー C3116 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3116
dev_langs:
- C++
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fde589df31e6e3b75f9a0153d7383ab1e85ed180
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3116"></a>コンパイラ エラー C3116
'ストレージの指定子': インターフェイス メソッドに対する無効なストレージ クラス  
  
 使用する`typedef`、 `register`、または`static`インターフェイス メソッドのストレージ クラスとして。 これらのストレージ クラスは、インターフェイスのメンバーには使用できません。  
  
 次の例では、C3116 が生成されます。  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```