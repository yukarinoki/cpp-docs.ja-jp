---
title: map::rbegin (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: bd7165a3-561f-48d4-9791-7aaafc2cf3a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 65ae106d9d0e2593f5c06612a04494d2372ec82d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="maprbegin-stlclr"></a>map::rbegin (STL/CLR)
反転被制御シーケンスの先頭を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、最後の要素または空のシーケンスの先頭を越えた、被制御シーケンスの指定、逆順反復子を返します。 したがって、これを指定、`beginning`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合、逆の順序で表示される、被制御シーケンスですがその状態の先頭は変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_map_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    Mymap::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*rbegin() = [c 3]  
*++rbegin() = [b 2]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)   
 [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)   
 [map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)