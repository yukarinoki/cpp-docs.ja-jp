---
title: map::const_iterator (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::const_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_iterator member [STL/CLR]
ms.assetid: bf7a3d55-032c-4233-bb48-d1530b10cb00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 031cc8369a389a55e52a4d1676b1b17a6c6411de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129763"
---
# <a name="mapconstiterator-stlclr"></a>map::const_iterator (STL/CLR)
被制御シーケンスの定数反復子の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型が指定されていない型のオブジェクトを表します`T2`被制御シーケンスの定数の双方向反復子として使用されることができます。  
  
## <a name="example"></a>例  
  
```  
// cliext_map_const_iterator.cpp   
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
    Mymap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" [{0} {1}]", cit->first, cit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)