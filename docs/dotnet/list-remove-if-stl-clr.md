---
title: list::remove_if (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::remove_if
dev_langs:
- C++
helpviewer_keywords:
- remove_if member [STL/CLR]
ms.assetid: cbc66192-751b-41c5-b557-d5d7bbc2a840
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 53a6c12509e34e40d3a6a439fb03dc1f6779aba3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132324"
---
# <a name="listremoveif-stlclr"></a>list::remove_if (STL/CLR)
指定されたテストに合格した要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 削除する要素をテストします。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンス (消去) から削除のすべての要素`X`を`pred(X)`は true です。 これを使用するには関数またはデリゲートとして指定することが条件を満たすすべての要素を削除します。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)   
 [list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)   
 [list::remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)