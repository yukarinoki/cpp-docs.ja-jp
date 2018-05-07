---
title: hash_set::hash_set (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::hash_set
dev_langs:
- C++
helpviewer_keywords:
- hash_set member [STL/CLR]
ms.assetid: 006414ed-db5a-4c08-ac81-4a8ae57d0aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1e0f8ce11d66b02c63d2eee6cf2022c16c214fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashsethashset-stlclr"></a>hash_set::hash_set (STL/CLR)
コンテナー オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
hash_set();  
explicit hash_set(key_compare^ pred);  
hash_set(key_compare^ pred, hasher^ hashfn);  
hash_set(hash_set<Key>% right);  
hash_set(hash_set<Key>^ right);  
template<typename InIter>  
    hash_sethash_set(InIter first, InIter last);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `hash_set();`  
  
 既定の順序の述語を使用して要素を持たない、被制御シーケンスを初期化`key_compare()`既定のハッシュ関数を使用しています。 これを使用するには、既定の述語とハッシュ関数の順序を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `explicit hash_set(key_compare^ pred);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`既定のハッシュ関数を使用しています。 これを使用するには、空の初期被制御シーケンスを指定された順序の指定の述語と既定のハッシュ関数を指定します。  
  
 : コンス トラクター  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用して、指定の順序の指定の述語とハッシュ関数で、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `hash_set(hash_set<Key>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right.begin()`、 `right.end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_set オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `hash_set(hash_set<Key>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right->begin()`、 `right->end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_set オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)、既定の順序の述語、および既定のハッシュ関数です。 使用する既定の順序の述語とハッシュ関数で被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスの順序指定された述語と既定のハッシュ関数、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`既定の順序の述語、および既定のハッシュ関数です。 これを使用するには、被制御シーケンスの既定の順序の述語とハッシュ関数と、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスに指定された順序の指定の述語と既定ハッシュ関数、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
// construct an empty container   
    Myhash_set c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 a b c  
size() = 0  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::generic_container (STL/CLR)](../dotnet/hash-set-generic-container-stl-clr.md)   
 [hash_set::operator= (STL/CLR)](../dotnet/hash-set-operator-assign-stl-clr.md)