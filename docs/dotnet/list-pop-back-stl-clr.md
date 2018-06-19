---
title: list::pop_back (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::pop_back
dev_langs:
- C++
helpviewer_keywords:
- pop_back member [STL/CLR]
ms.assetid: 03fe8e0e-461b-41c4-8e20-97d0d4ed0feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: acbd8718aa16fadf21ce7091b33d454eeda33b4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135093"
---
# <a name="listpopback-stlclr"></a>list::pop_back (STL/CLR)
最後の要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
void pop_back();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、空でない必要があります、被制御シーケンスの最後の要素を削除します。 使用するを背面にある 1 つの要素で、一覧を短きます。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_pop_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)   
 [list::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)   
 [list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)