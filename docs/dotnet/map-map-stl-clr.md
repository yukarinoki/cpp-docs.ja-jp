---
title: map::map (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::map
dev_langs:
- C++
helpviewer_keywords:
- map member [STL/CLR]
ms.assetid: c91f699a-4742-4859-b2b3-c2a01a750bea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cd39f72c776065eadac713012440b9fe4701329a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137615"
---
# <a name="mapmap-stlclr"></a>map::map (STL/CLR)
コンテナー オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
map();  
explicit map(key_compare^ pred);  
map(map<Key, Mapped>% right);  
map(map<Key, Mapped>^ right);  
template<typename InIter>  
    mapmap(InIter first, InIter last);  
template<typename InIter>  
    map(InIter first, InIter last,  
        key_compare^ pred);  
map(System::Collections::Generic::IEnumerable<GValue>^ right);  
map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
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
  
 `map();`  
  
 既定の順序の述語を使用して要素を持たない、被制御シーケンスを初期化`key_compare()`です。 これを使用するには、既定の順序の述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `explicit map(key_compare^ pred);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`です。 これを使用して、順序指定された述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `map(map<Key, Mapped>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します [`right.begin()`、 `right.end()`)、既定の順序の述語とします。 マップ オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の述語とします。  
  
 : コンス トラクター  
  
 `map(map<Key, Mapped>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します [`right->begin()`、 `right->end()`)、既定の順序の述語とします。 マップ オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の述語とします。  
  
 : コンス トラクター  
  
 `template<typename InIter> map(InIter first, InIter last);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、既定の順序の述語とします。 使用する既定の順序の述語で被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> map(InIter first, InIter last, key_compare^ pred);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)、順序の指定の述語に置き換えます`pred`です。 これを使用するには、被制御シーケンスの順序指定された述語を持つ、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`既定の順序の述語とします。 これを使用するには、被制御シーケンスの既定の順序の述語と、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語と`pred`です。 これを使用するには、被制御シーケンスの順序指定された述語を持つ、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_map_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
// construct an empty container   
    Mymap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymap c3(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3);   
    for each (Mymap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymap c7(c4);   
    for each (Mymap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymap c8(%c3);   
    for each (Mymap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)   
 [map::operator= (STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)