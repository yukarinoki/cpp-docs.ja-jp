---
title: hash_set::insert (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 0a9bc9aa-012e-4101-9e8c-f1f4b6b76af7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9bab7d42d981cd54cd72c318f978f482a84a465b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130004"
---
# <a name="hashsetinsert-stlclr"></a>hash_set::insert (STL/CLR)
要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 val  
 挿入するキー値。  
  
 where  
 (ヒントのみ) を挿入するためのコンテナー内の場所。  
  
## <a name="remarks"></a>コメント  
 各メンバー関数は、残りのオペランドで指定されたシーケンスを挿入します。  
  
 最初のメンバー関数が値を持つ要素を挿入するよう努めて`val`、値のペアを返しますと`X`です。 場合`X.second`が true の場合、`X.first`新しく挿入される要素を指定以外の場合`X.first`それと同等の要素を指定既に順序付けが存在し、新しい要素が挿入されません。 使用する 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値を持つ要素を挿入します。`val`を使用して、 `where` (パフォーマンスを向上させる) をヒントとしてし、新しく挿入される要素を指定する反復子を返します。 使用することがわかって要素に隣接する可能性のある 1 つの要素を挿入します。  
  
 3 番目のメンバー関数は、シーケンスを挿入します。 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 各要素の挿入では、被制御シーケンス内の要素の数の対数に比例して時間がかかります。 挿入は、カーソル位置に隣接する要素を指定するヒントの指定、償却定数時間でただし、実行できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_bool Pairib;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_set c2;   
    Myhash_set::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_set c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = [x True]  
insert(L'b') = [b False]  
 a b c x  
insert(begin(), L'y') = y  
 a b c x y  
 a b c x  
 a b c x y  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)