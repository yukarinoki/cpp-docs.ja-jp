---
title: 式エバリュエーター エラー CXX0064 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7964eac628fa89695d1757cff8b7b329fd7fe713
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0064"></a>式エバリュエーター エラー CXX0064
バインドされた仮想メンバー関数にブレークポイントを設定することはできません。  
  
 ブレークポイントがなどのオブジェクトへのポインターを介して仮想メンバー関数に設定されました。  
  
```  
pClass->vfunc( int );  
```  
  
 など、クラスを入力して、仮想関数のブレークポイントを設定できます。  
  
```  
Class::vfunc( int );  
```  
  
 このエラーは、can0064 と同じものと同じです。