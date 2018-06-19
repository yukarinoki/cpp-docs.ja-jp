---
title: deque::at (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::at
dev_langs:
- C++
helpviewer_keywords:
- at member [STL/CLR]
ms.assetid: 9af83d8a-c519-4b2a-a25f-d3dc8bbb87fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8388f6428d31cce2993e7c90db66f430564d347e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107052"
---
# <a name="dequeat-stlclr"></a>deque::at (STL/CLR)
指定した位置にある要素にアクセスします。  
  
## <a name="syntax"></a>構文  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>パラメーター  
 発注書  
 アクセスする要素の位置。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、位置にある被制御シーケンスの要素への参照を返します`pos`です。 読み取ったり書き込んだりする要素の位置に使用することがわかっています。  
  
## <a name="example"></a>例  
  
```  
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)