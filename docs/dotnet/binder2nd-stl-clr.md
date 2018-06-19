---
title: binder2nd (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd function [STL/CLR]
ms.assetid: f4be8722-1778-4cb9-9ec7-ad1443f6899f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d203463213f970d70758ef69ab398f12a52c422f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107845"
---
# <a name="binder2nd-stlclr"></a>binder2nd (STL/CLR)
このテンプレート クラスは、引数が 1 つファンクタを記述、呼び出されると、指定された最初の引数とそのストアドの 2 番目の引数で呼び出されたストアドその 2 つの引数ファンクタを返します。 使用するそのストアド ファンクタの観点から、関数オブジェクトを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>パラメーター  
 楽しい  
 ストアド ファンクタの型。  
  
## <a name="member-functions"></a>メンバー関数  
  
|型定義|説明|  
|---------------------|-----------------|  
|delegate_type|汎用デリゲートの型。|  
|first_argument_type|ファンクタ最初の引数の型。|  
|result_type|ファンクタ結果の型。|  
|second_argument_type|ファンクタ 2 番目の引数の型。|  
|stored_function_type|ファンクタの型。|  
  
|メンバー|説明|  
|------------|-----------------|  
|binder2nd|ファンクタを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|演算子 ()|必要な関数を計算します。|  
|演算子 delegate_type^()|デリゲートにファンクタをキャストします。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスでは、2 つの引数ファンクターと 2 番目の引数を格納する引数が 1 つファンクタについて説明します。 このメンバー演算子を定義する`operator()`指定された最初の引数と 2 番目の引数がストアド ストアド ファンクターを呼び出すときの結果が返されるオブジェクトが関数として呼び出されたとき、ようにことです。  
  
 型が関数の引数として、オブジェクトを渡すことができますも`delegate_type^`適切に変換されます。  
  
## <a name="example"></a>例  
  
```  
// cliext_binder2nd.cpp   
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
 [bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)