---
title: list::rend (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: b51030ad-1bca-42b0-b890-db47111d2921
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 19b3a1f7b6483bcf8fa839c8b20d1f261f096c2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131713"
---
# <a name="listrend-stlclr"></a>list::rend (STL/CLR)
反転被制御シーケンスの末尾を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの先頭位置を指し示す反転反復子を返します。 したがって、これを指定、`end`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合は逆の順序で表示される、被制御シーケンスですがその状態の終了を変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_rend.cpp   
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
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)   
 [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)