---
title: list::splice (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::splice
dev_langs:
- C++
helpviewer_keywords:
- splice member [STL/CLR]
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e0c92faf6a4ec84e6ed65c58d02337038398d37e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135951"
---
# <a name="listsplice-stlclr"></a>list::splice (STL/CLR)
ノード間のリンクを restitch です。  
  
## <a name="syntax"></a>構文  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 スプライスする範囲の先頭。  
  
 last  
 スプライスする範囲の末尾。  
  
 右  
 スプライスするコンテナーです。  
  
 where  
 前にスプライスするためのコンテナー内の場所。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数は、挿入によって制御されるシーケンス`right`によって示される、被制御シーケンスの要素の前に`where`です。 これはまた、`right` からすべての要素を削除します (`%right`でなければなりません`this`)。使用するすべての 1 つのリストを別にスプライスします。  
  
 2 番目のメンバー関数によって指し示される要素を削除する`first`によって制御されるシーケンスで`right`被制御シーケンス内の要素を指すの前に挿入し、`where`です。 (場合`where` `==` `first` `||` `where` `== ++first`変更は発生しません)。使用する 1 つのリストの 1 つの要素を別にスプライスします。  
  
 3 番目のメンバー関数によって指定されたサブ範囲を挿入します。 [`first`、 `last`) によって制御されるシーケンスから`right`によって示される、被制御シーケンスの要素の前に`where`です。 これはまた、`right` で制御されるシーケンスから元のサブ範囲を削除します (If `right` `==` `this`、範囲 [`first`、 `last`) によって指し示される要素を含める必要がありますいない`where`)。Splice 0 個以上の要素の 1 つのリストから別のサブシーケンスを使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_splice.cpp   
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
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [list::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)   
 [list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)