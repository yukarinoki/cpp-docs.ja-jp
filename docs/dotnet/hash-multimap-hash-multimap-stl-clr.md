---
title: hash_multimap::hash_multimap (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::hash_multimap
dev_langs:
- C++
helpviewer_keywords:
- hash_multimap member [STL/CLR]
ms.assetid: a1d576a7-5dc7-4ad9-abef-ee7a13caaec3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 295b9f07911b672f0192d5f3db23ec4570e88982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaphashmultimap-stlclr"></a>hash_multimap::hash_multimap (STL/CLR)
コンテナー オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
hash_multimap();  
explicit hash_multimap(key_compare^ pred);  
hash_multimap(key_compare^ pred, hasher^ hashfn);  
hash_multimap(hash_multimap<Key, Mapped>% right);  
hash_multimap(hash_multimap<Key, Mapped>^ right);  
template<typename InIter>  
    hash_multimaphash_multimap(InIter first, InIter last);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 挿入する範囲の開始しています。  
  
 hashfn  
 ハッシュ バケットにマッピング キーの関数。  
  
 last  
 挿入する範囲の終了。  
  
 pred  
 被制御シーケンスの述語を順序付けです。  
  
 右  
 挿入するオブジェクトまたは範囲。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `hash_multimap();`  
  
 既定の順序の述語を使用して要素を持たない、被制御シーケンスを初期化`key_compare()`既定のハッシュ関数を使用しています。 これを使用するには、既定の述語とハッシュ関数の順序を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `explicit hash_multimap(key_compare^ pred);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`既定のハッシュ関数を使用しています。 これを使用するには、空の初期被制御シーケンスを指定された順序の指定の述語と既定のハッシュ関数を指定します。  
  
 : コンス トラクター  
  
 `hash_multimap(key_compare^ pred, hasher^ hashfn);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用して、指定の順序の指定の述語とハッシュ関数で、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `hash_multimap(hash_multimap<Key, Mapped>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right.begin()`、 `right.end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_multimap オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `hash_multimap(hash_multimap<Key, Mapped>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right->begin()`、 `right->end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_multimap オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)、既定の順序の述語、および既定のハッシュ関数です。 使用する既定の順序の述語とハッシュ関数で被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスの順序指定された述語と既定のハッシュ関数、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`既定の順序の述語、および既定のハッシュ関数です。 これを使用するには、被制御シーケンスの既定の順序の述語とハッシュ関数と、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスに指定された順序の指定の述語と既定ハッシュ関数、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
// construct an empty container   
    Myhash_multimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multimap c3(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multimap c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3);   
    for each (Myhash_multimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multimap c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multimap c7(c4);   
    for each (Myhash_multimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_multimap c8(%c3);   
    for each (Myhash_multimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)   
 [hash_multimap::operator= (STL/CLR)](../dotnet/hash-multimap-operator-assign-stl-clr.md)