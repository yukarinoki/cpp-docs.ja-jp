---
title: 演算子 = = (map) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::operator==
dev_langs:
- C++
helpviewer_keywords:
- operator== member [STL/CLR]
ms.assetid: 6f7672af-71f8-4086-ac42-173203e52951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: db005d1cb4be7af451ba9b0a0ec544aad86b87ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="operator-map-stlclr"></a>operator== (map) (STL/CLR)
比較を一覧表示します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator==(map<Key, Mapped>% left,  
        map<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子の関数が、シーケンスがによって制御される場合にのみ true を返します`left`と`right`同じ長さであると、各位置`i`、 `left[i] ==` `right[i]`です。 テストするために使用するかどうか`left`が同じ順序付け`right`要素によって比較対象の要素が 2 つのマップの場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_map_operator_eq.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymap c2;   
    c2.insert(Mymap::make_value(L'a', 1));   
    c2.insert(Mymap::make_value(L'b', 2));   
    c2.insert(Mymap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [d 4]  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [operator! = (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)   
 [演算子\<(map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)   
 [operator > = (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)   
 [operator > (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)   
 [operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)