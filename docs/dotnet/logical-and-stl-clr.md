---
title: logical_and (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::logical_and
dev_langs:
- C++
helpviewer_keywords:
- logical_and function [STL/CLR]
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 72f14aca5c4c2649475482cb8417e23ca2eae35c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="logicaland-stlclr"></a>logical_and (STL/CLR)
このテンプレート クラスは、ファンクタを記述、呼び出されると、true を返します、最初の引数と 2 番目のテストとしての両方が true の場合のみです。 使用する、引数の型の観点から、関数オブジェクトを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
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
|logical_and|ファンクタを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|演算子 ()|必要な関数を計算します。|  
|演算子 delegate_type ^|デリゲートにファンクタをキャストします。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、2 つの引数ファンクタをについて説明します。 このメンバー演算子を定義する`operator()`これにより、オブジェクトが関数として呼び出される場合、true を返しますのみ 1 番目の引数と 2 番目のテストとしての両方の true です。  
  
 型が関数の引数として、オブジェクトを渡すことができますも`delegate_type^`適切に変換されます。  
  
## <a name="example"></a>例  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
2 0  
3 0  
1 0  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [logical_or (STL/CLR)](../dotnet/logical-or-stl-clr.md)