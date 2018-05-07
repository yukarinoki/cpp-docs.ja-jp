---
title: コンパイラの警告 (レベル 2) C4099 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afecb3fb2420d27bedf16c81894f224a1119a67b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099
'identifier': 'objecttype1' 使われて '%objecttype2' を使用して 1 つ目の種類名  
  
 クラスと構造体として宣言されたオブジェクトが定義されているまたは構造体としてをクラスとして宣言されたオブジェクトを定義します。 コンパイラは、定義で指定された型を使用します。  
  
## <a name="example"></a>例  
 次の例では、C4099 を生成します。  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```