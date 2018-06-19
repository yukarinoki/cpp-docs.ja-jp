---
title: list::unique (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::unique
dev_langs:
- C++
helpviewer_keywords:
- unique member [STL/CLR]
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d5dbfab0fb53a4ca11128d01e7b32060c6428549
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137576"
---
# <a name="listunique-stlclr"></a>list::unique (STL/CLR)
指定されたテストに合格した隣接する要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 要素のペアの比較子。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数は、被制御シーケンス (消去) から削除を比較するすべての要素に一致する直前の要素--場合要素`X`要素の前に`Y`と`X == Y`、メンバー関数は削除`Y`です。 使用する、隣接する要素のすべてのサブシーケンスのすべてが 1 つのコピーを削除するのにその比較結果が同じです。 されている場合、被制御シーケンスが順序付けなどの呼び出しによって[list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`、メンバー関数は、一意の値を持つ要素のみのままにします。 (ターミナル メソッドという名前なのはそのためです)。  
  
 2 番目のメンバー関数と同様、最初の各要素を削除する点を除いて`Y`次の要素`X`を`pred(X, Y)`です。 述語関数または指定したデリゲートを満たす隣接する要素のすべてのサブシーケンスのすべてが 1 つのコピーを削除するのに使用するとします。 されている場合、被制御シーケンスが順序付けなどの呼び出しによって`sort(pred)`、メンバー関数と同じ順序付け、他の要素がない要素のみのままにします。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [list::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)