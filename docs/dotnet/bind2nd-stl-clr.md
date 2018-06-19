---
title: bind2nd (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::bind2nd
dev_langs:
- C++
helpviewer_keywords:
- bind2nd function [STL/CLR]
ms.assetid: 457cebea-38e4-4466-a468-fe9eb138e80c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 13d8ffe476c73c04aff2e0c5de84558a7d9dbeae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106149"
---
# <a name="bind2nd-stlclr"></a>bind2nd (STL/CLR)
生成、`binder2nd`引数およびファンクタ。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Fun,  
    typename Arg>  
    binder2nd<Fun> bind2nd(Fun% functor,  
        Arg right);  
```  
  
## <a name="template-parameters"></a>テンプレート パラメーター  
 arg  
 引数の型。  
  
 楽しい  
 ファンクタの型。  
  
## <a name="function-parameters"></a>関数パラメーター  
 ファンクター  
 ラップするファンクタ。  
  
 右  
 ラップする 2 番目の引数。  
  
## <a name="remarks"></a>コメント  
 テンプレート関数を返します[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`です。 最初の引数を持つ呼び出し元引数が 1 つファンクタで 2 つの引数ファンクターと 2 番目の引数をラップする便利な手段として使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_bind2nd.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)