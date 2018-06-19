---
title: hash_multimap::find (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: ce839c5e-b8c5-434e-9cc0-e4c6ee6a6bb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82766ef6a7ef739173decd7c9b194a6bf13028ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109483"
---
# <a name="hashmultimapfind-stlclr"></a>hash_multimap::find (STL/CLR)
指定したキーに一致する要素を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 被制御シーケンス内の少なくとも 1 つの要素と同じ順序付け`key`、メンバー関数は、それらの要素のいずれかを指定する反復子を返しますそれ以外の場合を返します[hash_multimap::end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`。 指定したキーに一致する制御シーケンス内の要素を検索に使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multimap_find.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Myhash_multimap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
find A = False  
find b = [b 2]  
find C = False  
```  
  
## <a name="description"></a>説明  
 なお`find`をいくつかの要素が見つかったは保証されません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::equal_range (STL/CLR)](../dotnet/hash-multimap-equal-range-stl-clr.md)   
 [hash_multimap::lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md)   
 [hash_multimap::upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)