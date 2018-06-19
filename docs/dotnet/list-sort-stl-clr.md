---
title: list::sort (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::sort
dev_langs:
- C++
helpviewer_keywords:
- sort member [STL/CLR]
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 670b18e5901ef264474256a1a1e57cde7a28ef01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138345"
---
# <a name="listsort-stlclr"></a>list::sort (STL/CLR)
被制御シーケンスを並べ替えます。  
  
## <a name="syntax"></a>構文  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 要素のペアの比較子。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数は、によって順序がされるように、被制御シーケンス内の要素を再配置`operator<`--進行中は、シーケンス値で要素を縮小しません。 昇順に並べ替え順序を並べ替えるには、このメンバー関数を使用します。  
  
 2 番目のメンバー関数の動作、最初と同じで、シーケンスが順序付けする点を除いて`pred`  --  `pred(X, Y)`は任意の要素に対して false`X`要素に依存している`Y`結果のシーケンスにします。 述語の関数またはデリゲートで指定した順序でシーケンスの並べ替えに使用します。  
  
 両方関数は、安定した並べ替えを実行します。--結果として得られる被制御シーケンス内の元の被制御シーケンス内の要素のペアを逆にありません。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_sort.cpp   
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
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)   
 [list::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)   
 [list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)