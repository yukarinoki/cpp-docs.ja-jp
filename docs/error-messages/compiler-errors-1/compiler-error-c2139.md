---
title: コンパイラ エラー C2139 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2139
dev_langs:
- C++
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd56ee920d3f53b22d9979b45c39fa78b9054662
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169805"
---
# <a name="compiler-error-c2139"></a>コンパイラ エラー C2139
'type': 未定義のクラスがコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません  
  
 無効な引数は、型の特徴に渡されました。  
  
 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2139 を生成します。  
  
```  
// C2139.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class C;  
class D {};  
  
class E {  
public:  
   virtual void Test() {}  
};  
  
int main() {  
   cout << is_polymorphic<C>::value << endl;   // C2139  
   cout << is_polymorphic<D>::value << endl;   // OK  
   cout << is_polymorphic<E>::value << endl;   // OK  
}  
```