---
title: list::insert (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0e1ce686cbf905a0e49f94e4d8cebf180fbc0224
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134298"
---
# <a name="listinsert-stlclr"></a>list::insert (STL/CLR)
指定した位置にある要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 count  
 挿入する要素の数。  
  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 val  
 挿入する要素の値です。  
  
 where  
 前に挿入するためのコンテナー内の場所。  
  
## <a name="remarks"></a>コメント  
 メンバーの各関数が指す要素の前に、挿入`where`被制御シーケンスのシーケンスは、残りのオペランドで指定します。  
  
 最初のメンバー関数は、値を持つ要素を挿入します。`val`し、新しく挿入される要素を指定する反復子を返します。 使用する反復子によって指定された場所の前に 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値 `count` の要素を `val` 個挿入します。 使用する同じ値のすべてのコピーである 0 個以上の連続する要素を挿入します。  
  
 `InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合、これは、シーケンスを挿入 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の連続する要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 1 つの要素を挿入するときに要素のコピーの数はカーソルと、シーケンスの最も近い最後の要素の数に比例します。 (1 つまたは複数の要素を挿入する、シーケンスの先頭または末尾にある、ときに要素のコピーは発生しません。)場合`InIt`は入力反復子は、3 番目のメンバー関数は、シーケンス内の各要素の 1 つの挿入を効果的に実行します。 それ以外の場合、挿入するときに`N`要素、要素のコピーの数が線形に`N`+ カーソルと、シーケンスの最も近い最後の要素の数。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_insert.cpp   
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
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)