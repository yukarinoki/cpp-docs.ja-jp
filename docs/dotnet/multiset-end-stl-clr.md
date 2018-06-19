---
title: multiset::end (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::end
dev_langs:
- C++
helpviewer_keywords:
- end member [STL/CLR]
ms.assetid: 225f8b74-f9b9-47ea-9603-43ac7c9a9734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 71ec368f62bef53b53f331cbe35bd1a455f84655
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131726"
---
# <a name="multisetend-stlclr"></a>multiset::end (STL/CLR)
被制御シーケンスの末尾を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの最後の位置を指し示す双方向反復子を返します。 被制御シーケンスの末尾を指定する反復子を取得するのにために使用します。その状態は、被制御シーケンスの長さが変更された場合は変更されません。  
  
## <a name="example"></a>例  
  
```  
// cliext_multiset_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md)