---
title: コンパイラ エラー C3113 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3113
dev_langs:
- C++
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 220f400bd1ce80be039dcd8d572d20fad5da09f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3113"></a>コンパイラ エラー C3113
'structure' をテンプレートまたはジェネリックにすることはできません。  
  
 ジェネリック インターフェイスまたは列挙型から、クラス テンプレートまたはクラスを作成しようとしました。  
  
 次の例では、c3113 エラーが生成されます。  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```