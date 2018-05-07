---
title: list::begin (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::begin
dev_langs:
- C++
helpviewer_keywords:
- begin member [STL/CLR]
ms.assetid: 3431467b-951a-498a-af8d-50f631da1646
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eba4004f7f3bf1dfe4b0fdb3dd3c2b48450c0feb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="listbegin-stlclr"></a>list::begin (STL/CLR)
被制御シーケンスの先頭を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、または空のシーケンスの最後を越えたところ、被制御シーケンスの最初の要素を指定するランダム アクセス反復子を返します。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さが変更された場合は、被制御シーケンスが、そのステータスの先頭を変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_begin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::front (STL/CLR)](../dotnet/list-front-stl-clr.md)   
 [list::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)