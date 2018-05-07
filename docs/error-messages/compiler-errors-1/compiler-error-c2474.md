---
title: コンパイラ エラー C2474 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b42e93630bdfba0400c30aafa1b6436f5b9e868
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2474"></a>コンパイラ エラー C2474
'keyword' : 隣接するセミコロンがありません。キーワードまたは識別子のどちらかである可能性があります。  
  
 コンパイラでセミコロンが検出される必要があったため、ユーザーの意図は認識されませんでした。 このエラーを解決するには、セミコロンを追加します。  
  
## <a name="example"></a>例  
 次の例では C2474 が生成されます。  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```