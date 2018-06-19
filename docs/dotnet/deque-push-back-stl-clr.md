---
title: deque::push_back (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::push_back
dev_langs:
- C++
helpviewer_keywords:
- push_back member [STL/CLR]
ms.assetid: dafd5a4d-1fc7-434c-b129-a523099f8701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eaa2cf2889790a93b90ccf0dc4358a8415feb3fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110675"
---
# <a name="dequepushback-stlclr"></a>deque::push_back (STL/CLR)
新しい最後の要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
void push_back(value_type val);  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、値を持つ要素を挿入します。`val`被制御シーケンスの最後にします。 これを使用するには、deque に別の要素を追加します。  
  
## <a name="example"></a>例  
  
```  
// cliext_deque_push_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)   
 [deque::pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)   
 [deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)