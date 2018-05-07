---
title: map::operator(STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::operator[]
dev_langs:
- C++
helpviewer_keywords:
- operatormember [] [STL/CLR]
ms.assetid: 50e494c5-62d4-4469-8da3-7432ee4dff97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2eeedf3c6d4dda7ac8a90ac430f8d48f871750bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mapoperatorstlclr"></a>map::operator(STL/CLR)
関連するマップされた値をキーにマップします。  
  
## <a name="syntax"></a>構文  
  
```  
mapped_type operator[](key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 メンバー関数と同等の順序を持つ要素を検索する試み`key`です。 1 つが見つかると、値を返します、関連付けられているマップです。それ以外の場合、これは挿入`value_type(key, mapped_type())`し、関連付けられているを返します (既定値) には、値がマップされています。 これを使用してに関連付けられたキーの指定、マップされた値を確認するか、何も見つからない場合は、キーのエントリが存在することを確認します。  
  
## <a name="example"></a>例  
  
```  
// cliext_map_operator_sub.cpp   
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
  
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'A', c1[L'A']);   
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'b', c1[L'b']);   
  
// redisplay altered contents   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// alter mapped values and redisplay   
    c1[L'A'] = 10;   
    c1[L'c'] = 13;   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
c1[A] = 0  
c1[b] = 2  
 [A 0] [a 1] [b 2] [c 3]  
 [A 10] [a 1] [b 2] [c 13]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::find (STL/CLR)](../dotnet/map-find-stl-clr.md)   
 [map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)