---
title: hash_set::generic_iterator (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::generic_iterator
dev_langs:
- C++
helpviewer_keywords:
- generic_iterator member [STL/CLR]
ms.assetid: 9d6ac06d-d70c-4343-b959-553885a9cb53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c139776518a0a1d368845fb210541062c94866c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128593"
---
# <a name="hashsetgenericiterator-stlclr"></a>hash_set::generic_iterator (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するため、反復子の型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスで使用できる汎用の反復子を表します。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_set::generic_iterator gcit = gc1->begin();   
    Myhash_set::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::generic_container (STL/CLR)](../dotnet/hash-set-generic-container-stl-clr.md)