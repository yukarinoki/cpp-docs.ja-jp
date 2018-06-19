---
title: コンパイラ エラー C2893 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db3b71a05ece6b79672d47699dc68e0eb5bb1f60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246699"
---
# <a name="compiler-error-c2893"></a>コンパイラ エラー C2893
関数テンプレート 'テンプレート名' の特定に失敗しました  
  
 コンパイラは関数テンプレートを特殊化に失敗しました。 このエラーの多くの原因があります。  
  
 一般に、C2893 エラーを解決する方法を関数のシグネチャを確認し、すべての型のインスタンスを作成できるかどうかを確認します。  
  
## <a name="example"></a>例  
 C2893 が原因で発生`f`のテンプレート パラメーター`T`があると推測`std::map<int,int>`が`std::map<int,int>`メンバーを持たない`data_type`(`T::data_type`でインスタンス化することができない`T = std::map<int,int>`。)。 次の例では、C2893 を生成します。  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```