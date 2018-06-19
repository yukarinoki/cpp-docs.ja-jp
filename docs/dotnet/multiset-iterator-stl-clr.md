---
title: multiset::iterator (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator member [STL/CLR]
ms.assetid: 0e8fff2a-f90e-4ba6-816a-5a2dc77c51e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59dd5a3df95e84a76828591a9c7861121d0b69a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134505"
---
# <a name="multisetiterator-stlclr"></a>multiset::iterator (STL/CLR)
被制御シーケンスの反復子の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型が指定されていない型のオブジェクトを表します`T1`被制御シーケンスの双方向反復子として使用されることができます。  
  
## <a name="example"></a>例  
  
```  
// cliext_multiset_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::const_iterator (STL/CLR)](../dotnet/multiset-const-iterator-stl-clr.md)