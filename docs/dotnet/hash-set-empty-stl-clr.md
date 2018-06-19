---
title: hash_set::empty (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::empty
dev_langs:
- C++
helpviewer_keywords:
- empty member [STL/CLR]
ms.assetid: 7843eb9a-067b-4339-8637-5401b637c6d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c94ce396ffaadb2374c34cb224ecbe6d0692a735
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127280"
---
# <a name="hashsetempty-stlclr"></a>hash_set::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[hash_set::size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md)`() == 0`です。 これを使用するには、hash_set が空かどうかをテストします。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_empty.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md)