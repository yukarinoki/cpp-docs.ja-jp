---
title: コンパイラ エラー C3896 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc60c09d6fd99e56f0261409099e56713604a76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3896"></a>コンパイラ エラー C3896
'member': 正しくない初期化子: このリテラル データ メンバーは 'nullptr' と共にのみ初期化できます  
  
 A[リテラル](../../windows/literal-cpp-component-extensions.md)データ メンバーが正しく初期化されていません。  参照してください[nullptr](../../windows/nullptr-cpp-component-extensions.md)詳細についてはします。  
  
 次の例では、C3896 が生成されます。  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```