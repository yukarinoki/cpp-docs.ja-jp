---
title: operator! = (リスト) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::operator!=
dev_langs:
- C++
helpviewer_keywords:
- operator!= member [STL/CLR]
ms.assetid: aa4e1461-8137-43df-a99c-fbec8dd3269f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 10a6c92127042b8ad9805c53d7a10f5abc8134f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134306"
---
# <a name="operator-list-stlclr"></a>operator!= (list) (STL/CLR)
等しくない比較を一覧表示します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator!=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(left == right)`です。 テストするために使用するかどうか`left`順序付けされていないと同じ`right`と 2 つのリストは、要素で要素を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_operator_ne.cpp   
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
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [演算子 = = (リスト) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)   
 [演算子\<(リスト) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)   
 [operator > = (リスト) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)   
 [operator > (リスト) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)   
 [operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)