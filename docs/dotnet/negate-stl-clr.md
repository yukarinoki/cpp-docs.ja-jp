---
title: negate (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::negate
dev_langs:
- C++
helpviewer_keywords:
- negate function [STL/CLR]
ms.assetid: 58e4c339-0dee-4db8-b2cc-de8920977039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5971bab0439f42c5abda71daae3671125b2e0b8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135438"
---
# <a name="negate-stlclr"></a>negate (STL/CLR)
このテンプレート クラスは、ファンクタを記述、呼び出されると、その引数を否定を返します。 使用する、引数の型の観点から、関数オブジェクトを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Arg>  
    ref class negate  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    negate();  
    negate(negate<Arg>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>パラメーター  
 arg  
 引数の型。  
  
## <a name="member-functions"></a>メンバー関数  
  
|型定義|説明|  
|---------------------|-----------------|  
|argument_type|ファンクタ引数の型。|  
|delegate_type|汎用デリゲートの型。|  
|result_type|ファンクタ結果の型。|  
  
|メンバー|説明|  
|------------|-----------------|  
|negate|ファンクタを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|演算子 ()|必要な関数を計算します。|  
|演算子 delegate_type ^|デリゲートにファンクタをキャストします。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、引数が 1 つファンクタをについて説明します。 このメンバー演算子を定義する`operator()`否定の引数が返されるオブジェクトが関数として呼び出されたとき、ようにことです。  
  
 型が関数の引数として、オブジェクトを渡すことができますも`delegate_type^`適切に変換されます。  
  
## <a name="example"></a>例  
  
```  
// cliext_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(-3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 -3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::negate<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 -3  
-4 3  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [logical_not (STL/CLR)](../dotnet/logical-not-stl-clr.md)