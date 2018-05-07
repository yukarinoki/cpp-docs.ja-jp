---
title: コンパイラ エラー C3227 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3227
dev_langs:
- C++
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4d156e70a1ac2c0b05e212ace81b8ccc32d8f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3227"></a>コンパイラ エラー C3227
'parameter': 'キーワード' を使用して、ジェネリック型を割り当てることはできません  
  
 型をインスタンス化するのには、適切なコンス トラクターが必要です。 ただし、コンパイラは、適切なコンス トラクターを使用できるようにすることはできません。  
  
 ジェネリックではなくテンプレートを使用するには、このエラーを解決するのにまたはいくつかの方法のいずれかを使用して、型のインスタンスを作成することができます。  
  
## <a name="example"></a>例  
 次の例では、C3227 を生成します。  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```