---
title: equal_to (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function [STL/CLR]
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 492398ab8d82b7b97a4116766d7b1e98be525aae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="equalto-stlclr"></a>equal_to (STL/CLR)
このテンプレート クラスは、ファンクタを記述、呼び出されると、true を返します、最初の引数が 2 番目に等しい場合のみです。 使用する、引数の型の観点から、関数オブジェクトを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>パラメーター  
 arg  
 引数の型。  
  
## <a name="member-functions"></a>メンバー関数  
  
|型定義|説明|  
|---------------------|-----------------|  
|delegate_type|汎用デリゲートの型。|  
|first_argument_type|ファンクタ最初の引数の型。|  
|result_type|ファンクタ結果の型。|  
|second_argument_type|ファンクタ 2 番目の引数の型。|  
  
|メンバー|説明|  
|------------|-----------------|  
|equal_to|ファンクタを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|演算子 ()|必要な関数を計算します。|  
|演算子 delegate_type^()|デリゲートにファンクタをキャストします。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、2 つの引数ファンクタをについて説明します。 このメンバー演算子を定義する`operator()`これにより、オブジェクトが関数として呼び出される場合、true を返しますだけ最初の引数は、2 番目に等しいかどうかは。  
  
 型が関数の引数として、オブジェクトを渡すことができますも`delegate_type^`適切に変換されます。  
  
## <a name="example"></a>例  
  
```  
// cliext_equal_to.cpp   
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
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)