---
title: map::to_array (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: e7089d11-c968-4110-927a-97f9b5b8f992
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c4e9d9c3e785f2d2b6b3c5250172d1a3f5761bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129776"
---
# <a name="maptoarray-stlclr"></a>map::to_array (STL/CLR)
被制御シーケンスを新しい配列にコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、被制御シーケンスを格納する配列を返します。 使用する配列形式の被制御シーケンスのコピーを入手します。  
  
## <a name="example"></a>例  
  
```  
// cliext_map_to_array.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Mymap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Mymap::make_value(L'd', 4));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Mymap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3] [d 4]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)