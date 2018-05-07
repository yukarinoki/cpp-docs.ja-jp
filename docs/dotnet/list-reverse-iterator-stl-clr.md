---
title: list::reverse_iterator (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator member [STL/CLR]
ms.assetid: 56853ed8-cb12-41d7-98b2-c511cd77945d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3f071165e6b52ea7220487f2182849c1fc87359
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="listreverseiterator-stlclr"></a>list::reverse_iterator (STL/CLR)
被制御シーケンスの反転反復子の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef T3 reverse_iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型が指定されていない型のオブジェクトを表します`T3`被制御シーケンスの反転反復子として使用されることができます。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
x b a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::const_iterator (STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)   
 [list::const_reverse_iterator (STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)   
 [list::iterator (STL/CLR)](../dotnet/list-iterator-stl-clr.md)