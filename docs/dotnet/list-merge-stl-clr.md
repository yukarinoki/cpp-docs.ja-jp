---
title: list::merge (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::merge
dev_langs:
- C++
helpviewer_keywords:
- merge member [STL/CLR]
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff5ba18dea3b33d1cf3a50dedfc5e90055e69c3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="listmerge-stlclr"></a>list::merge (STL/CLR)
2 つの被制御シーケンスの順序をマージします。  
  
## <a name="syntax"></a>構文  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 要素のペアの比較子。  
  
 右  
 コンテナーにマージします。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数によって制御されるシーケンスからのすべての要素を削除する`right`被制御シーケンスに挿入します。 両方のシーケンスで以前注文`operator<`--いずれかのシーケンスの進行中の値で要素を縮小しません必要があります。 によって、結果のシーケンスが順序付けも`operator<`します。 このメンバー関数を使用するには値でも増加するシーケンスに値で増加する 2 つのシーケンスにマージします。  
  
 2 番目のメンバー関数と同様、最初は、順序に並べする点を除いて`pred`  --  `pred(X, Y)`任意の要素に対して false である必要があります`X`要素に依存している`Y`順序で。 使用順を指定するデリゲートの述語関数で 2 つのシーケンスにマージします。  
  
 両方関数は安定したマージの実行 - 結果として得られる被制御シーケンス内の元の被制御シーケンスのいずれかの要素のペアを逆にありません。 また場合の要素のペア`X`と`Y`結果の被制御シーケンスが大小-- `!(X < Y) && !(X < Y)` --によって制御されるシーケンスから要素の前に、の元の被制御シーケンス内の要素が表示されます`right`.  
  
## <a name="example"></a>例  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)   
 [list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)