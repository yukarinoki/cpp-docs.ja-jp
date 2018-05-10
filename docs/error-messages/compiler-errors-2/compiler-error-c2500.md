---
title: コンパイラ エラー C2500 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c05ffd59e415375dd3c7f94ae9bc377c0fc2b9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2500"></a>コンパイラ エラー C2500
'identifier1': 'identifier2' である直接基底クラス  
  
 クラスまたは構造体の基底クラスの一覧に 2 回以上表示されます。  
  
 直接の基本クラスは基底のリストに記載されています。 間接基本は、基底のリスト内のクラスのいずれかの基本クラスです。  
  
 クラスは、直接基底クラスとして複数回指定できません。 クラスは、間接基底クラスとして複数回使用できます。  
  
 次の例では、C2500 が生成されます。  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```