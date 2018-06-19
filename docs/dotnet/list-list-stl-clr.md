---
title: list::list (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::list
dev_langs:
- C++
helpviewer_keywords:
- list member [STL/CLR]
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cacfa4bb1d852a62d81d4496f19371072f2615f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137778"
---
# <a name="listlist-stlclr"></a>list::list (STL/CLR)
コンテナー オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `count`  
 挿入する要素の数。  
  
 `first`  
 挿入する範囲の開始しています。  
  
 `last`  
 挿入する範囲の終了。  
  
 `right`  
 挿入するオブジェクトまたは範囲。  
  
 `val`  
 挿入する要素の値です。  
  
## <a name="remarks"></a>コメント  
  
 : コンス トラクター  
  
 `list();`  
  
 要素を持たない被制御シーケンスを初期化します。 空の初期被制御シーケンスの指定に使用するとします。  
  
 : コンス トラクター  
  
 `list(list<Value>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right.begin()`、 `right.end()`)。 使用すると、リスト オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスの指定を`right`です。  
  
 : コンス トラクター  
  
 `list(list<Value>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right->begin()`、 `right->end()`)。 ハンドルが一覧のオブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`です。  
  
 : コンス トラクター  
  
 `explicit list(size_type count);`  
  
 被制御シーケンスを初期化します`count`値を持つ要素各`value_type()`です。 使用する要素をコンテナーを格納するのに既定値を持ちます。  
  
 : コンス トラクター  
  
 `list(size_type count, value_type val);`  
  
 被制御シーケンスを初期化します`count`値を持つ要素各`val`です。 使用する要素をコンテナーを格納するのに、同じ値を持ちます。  
  
 : コンス トラクター  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)。 これを使用するには、被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`です。 これを使用するには、被制御シーケンスの列挙子によって記述された別のシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [list::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)