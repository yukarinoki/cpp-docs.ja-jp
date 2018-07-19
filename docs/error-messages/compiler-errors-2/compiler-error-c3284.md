---
title: コンパイラ エラー C3284 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f75cc4e3d6d7eb30f125a016c43b72609d467c57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252557"
---
# <a name="compiler-error-c3284"></a>コンパイラ エラー C3284
ジェネリック パラメーター 'parameter' (関数 ’function’) に対する制約は、ジェネリック パラメーター 'parameter' (関数 'function') に対する制約と一致しなければなりません。  
  
 仮想ジェネリック関数は、基底クラス内にある、名前と引数のセットが同一の仮想関数と同じ制約を使用しなければなりません。  
  
 次の例では C3284 が生成されます。  
  
```  
// C3284.cpp  
// compile with: /clr /c  
// C3284 expected  
public interface class IGettable {  
   int Get();  
};  
  
public interface class B {  
   generic<typename T>  
   where T : IGettable  
   virtual int mf(T t);  
};  
  
public ref class D : public B {  
public:  
   generic<typename T>  
   // Uncomment the following line to resolve.  
   // where T : IGettable  
   virtual int mf(T t) {  
      return 4;  
   }  
};  
```