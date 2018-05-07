---
title: multiset::value_comp (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::value_comp
dev_langs:
- C++
helpviewer_keywords:
- value_comp member [STL/CLR]
ms.assetid: 6b418e7a-9e82-4d35-a25d-f07b79a875a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9045c9dba510d83c79a75525c57351c71ddca1a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="multisetvaluecomp-stlclr"></a>multiset::value_comp (STL/CLR)
2 つの要素値の順序付けのデリゲートをコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
value_compare^ value_comp();  
```  
  
## <a name="remarks"></a>コメント  
 メンバー関数では、被制御シーケンスの並べ替えに使用される順序付けのデリゲートを返します。 使用する 2 つの要素値を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_multiset_value_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::value_compare (STL/CLR)](../dotnet/multiset-value-compare-stl-clr.md)   
 [multiset::value_type (STL/CLR)](../dotnet/multiset-value-type-stl-clr.md)