---
title: コンパイラ エラー C3075 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3075
dev_langs:
- C++
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c582c9907987fe9f015f3e639e2f3f2e362e0c82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3075"></a>コンパイラ エラー C3075
'instance': 参照型 'type' のインスタンスを値型に埋め込むことはできません  
  
 値型に参照型のインスタンスを含めることはできません。  
  
 詳細については、次を参照してください。[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)です。  
  
## <a name="example"></a>例  
 次の例では C3075 が生成されます。  
  
```  
// C3075.cpp  
// compile with: /clr /c  
ref struct U {};  
value struct X {  
   U y;   // C3075  
};  
  
ref struct Y {  
   U y;   // OK  
};  
```