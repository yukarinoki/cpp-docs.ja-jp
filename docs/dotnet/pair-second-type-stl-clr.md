---
title: pair::second_type (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::second_type
dev_langs:
- C++
helpviewer_keywords:
- second_type member [STL/CLR]
ms.assetid: 555f0216-186b-4dac-babc-1499f69e5c1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d17a456d8e57a7cde61773da310a766374294d3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159510"
---
# <a name="pairsecondtype-stlclr"></a>pair::second_type (STL/CLR)
2 番目のラップされた値の型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef Value2 second_type;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Value2` のシノニムです。  
  
## <a name="example"></a>例  
  
```  
// cliext_pair_second_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ペア (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)   
 [pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)   
 [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)