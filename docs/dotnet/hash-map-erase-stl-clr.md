---
title: hash_map::erase (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 1d2a79aa-62f7-461c-8f7c-7b660eb189be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 827791bc90ddea7026582c18ea14eadeb96e7512
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110378"
---
# <a name="hashmaperase-stlclr"></a>hash_map::erase (STL/CLR)
指定した位置にある要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 消去する範囲の開始しています。  
  
 key  
 消去するキー値。  
  
 last  
 消去する範囲の終了。  
  
 where  
 消去する要素。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`where`、し、削除、要素の後に残る最初の要素を指定する反復子を返しますまたは[hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`このような要素が存在しない場合。 それを使用するには 1 つの要素を削除します。  
  
 2 番目のメンバー関数、被制御シーケンスの要素の範囲内の削除 [`first`、 `last`)、し、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは`end()`場合、このような要素がないです。存在する. これを使用するには 0 個以上の連続する要素を削除します。  
  
 3 番目のメンバー関数と同じ順序キーを持つは、被制御シーケンスのいずれかの要素を削除する`key`、削除された要素の数のカウントを返します。 これを使用して、削除し、指定したキーと一致するすべての要素をカウントします。  
  
 各要素の消去では、被制御シーケンス内の要素の数の対数に比例して時間がかかります。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_map_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    cliext::hash_map<wchar_t, int> c1;   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_map<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
erase(begin()) = [b 2]  
 [b 2] [c 3] [d 4] [e 5]  
erase(begin(), end()-1) = [e 5]  
size() = 1  
erase(L'x') = 0  
erase(L'e') = 1  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::clear (STL/CLR)](../dotnet/hash-map-clear-stl-clr.md)