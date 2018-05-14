---
title: hash_multiset::find (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: fbedeb37-242e-4c2a-b1f8-234bcfd9cd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b133889df92205366cf2005315e6761c7eb6617b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetfind-stlclr"></a>hash_multiset::find (STL/CLR)
指定したキーに一致する要素を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 被制御シーケンス内の少なくとも 1 つの要素と同じ順序付け`key`、メンバー関数は、それらの要素のいずれかを指定する反復子を返しますそれ以外の場合を返します[hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md) `()`。 指定したキーに一致する制御シーケンス内の要素を検索に使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multiset_find.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>説明  
 なお`find`をいくつかの要素が見つかったは保証されません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)   
 [hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)