---
title: コンパイラ エラー C2504 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bac0f8f28955af172590535568289182c3489d6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2504"></a>コンパイラ エラー C2504
'class': 基底クラスが定義されていません  
  
 基本クラスが宣言されていますが、定義されていることはありません。  以下の原因が考えられます。  
  
1.  インクルード ファイルがありません。  
  
2.  外部の基本クラスの宣言[extern](../../cpp/using-extern-to-specify-linkage.md)です。  
  
 次の例では、C2504 が生成されます。  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 わかりました  
  
```  
class C{};  
class D : public C {};  
```