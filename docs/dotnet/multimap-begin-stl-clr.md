---
title: multimap::begin (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::begin
dev_langs:
- C++
helpviewer_keywords:
- begin member [STL/CLR]
ms.assetid: 2e1e48f5-31e5-4ead-abae-bb5220925226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3680f338b1e4ff301b4e459b984277050a9b2050
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="multimapbegin-stlclr"></a>multimap::begin (STL/CLR)
被制御シーケンスの先頭を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、または空のシーケンスの最後を越えたところ、被制御シーケンスの最初の要素を指定する双方向反復子を返します。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さが変更された場合は、被制御シーケンスが、そのステータスの先頭を変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_multimap_begin.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultimap::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*++begin() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*begin() = [a 1]  
*++begin() = [b 2]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)