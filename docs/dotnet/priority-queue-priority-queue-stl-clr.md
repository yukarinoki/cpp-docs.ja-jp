---
title: priority_queue::priority_queue (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue member [STL/CLR]
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cb50eed9dbfcbe9480a6588ff10f966f1888205
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163394"
---
# <a name="priorityqueuepriorityqueue-stlclr"></a>priority_queue::priority_queue (STL/CLR)
コンテナー アダプター オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>パラメーター  
 続き  
 コピーするコンテナー。  
  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 pred  
 被制御シーケンスの述語を順序付けです。  
  
 右  
 挿入するオブジェクトまたは範囲。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `priority_queue();`  
  
 既定の順序の述語を空のラップされたコンテナーを作成します。 これを使用するには、既定の順序の述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 ラップされたコンテナーのコピーを作成する`right.get_container()`、順序の指定の述語と`right.value_comp()`です。 キュー オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`、同じ順序の指定の述語に置き換えます。  
  
 : コンス トラクター  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 ラップされたコンテナーのコピーを作成する`right->get_container()`、順序の指定の述語と`right->value_comp()`です。 キュー オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`*right`、同じ順序の指定の述語に置き換えます。  
  
 : コンス トラクター  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`です。 これを使用して、順序指定された述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`のすべての要素をプッシュ`cont`順序指定された述語で、既存のコンテナーからの初期被制御シーケンスを指定するために使用します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 既定の順序付け述語で、空のラップされたコンテナーを作成し、シーケンスをプッシュ [`first`、 `last`)。 これを使用して、順序指定された述語を持つ、指定した eqeuence からの初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`、シーケンスにプッシュし、[`first`、 `last`)。 これを使用して、順序指定された述語を持つ、指定した seqeuence からの初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`のすべての要素をプッシュ`cont`さらに、シーケンス [`first`、 `last`)。 これを使用して、順序指定された述語を持つ既存のコンテナーと、指定した seqeuence からの初期被制御シーケンスを指定します。  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)