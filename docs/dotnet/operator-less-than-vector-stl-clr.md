---
title: 演算子&lt;(ベクトル) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 41fbd028-e937-4337-9429-57e79a993eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 075517b08043d01436708b01423934deb3e12ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-vector-stlclr"></a>演算子&lt;(ベクトル) (STL/CLR)
ベクター比較よりも小さいです。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator<(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返す場合は true、最下位の位置の`i`を`!(right[i] < left[i])`も真であることをお勧め`left[i] < right[i]`です。 返しますそれ以外の場合、`left->size() < right->size()`をテストするために使用するかどうか`left`前に順序付け`right`要素によって比較対象の要素が 2 つのベクトルの場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_operator_lt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [演算子 = = (ベクトル) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)   
 [operator! = (ベクトル) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)   
 [operator > = (ベクトル) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)   
 [operator > (ベクトル) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)   
 [operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)