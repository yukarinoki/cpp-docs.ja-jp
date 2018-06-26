---
title: 一覧 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
dev_langs:
- C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4e6ae13efabd34c6c685b07691789634ca0aed9c
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305918"
---
# <a name="list-stlclr"></a>list (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`list`1 つの要素を格納する各ノードの双方向リンク リストとして要素のシーケンスを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 [値]  
 被制御シーケンス内の要素の型。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext 

## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[list::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|  
|[list::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|  
|[list::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|  
|[list::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリック インターフェイスの型。|  
|[list::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[list::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[list::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[list::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|  
|[list::reference (STL/CLR)](#reference)|要素への参照の型です。|  
|[list::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|  
|[list::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::value_type (STL/CLR)](#value_type)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[list::assign (STL/CLR)](#assign)|すべての要素を置換します。|  
|[list::back (STL/CLR)](#back)|最後の要素にアクセスします。|  
|[list::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|  
|[list::clear (STL/CLR)](#clear)|すべての要素を削除します。|  
|[list::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|  
|[list::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|  
|[list::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|  
|[list::front (STL/CLR)](#front)|最初の要素にアクセスします。|  
|[list::insert (STL/CLR)](#insert)|指定した位置にある要素を追加します。|  
|[list::list (STL/CLR)](#list)|コンテナー オブジェクトを構築します。|  
|[list::merge (STL/CLR)](#merge)|2 つの被制御シーケンスの順序をマージします。|  
|[list::pop_back (STL/CLR)](#pop_back)|最後の要素を削除します。|  
|[list::pop_front (STL/CLR)](#pop_front)|最初の要素を削除します。|  
|[list::push_back (STL/CLR)](#push_back)|新しい最後の要素を追加します。|  
|[list::push_front (STL/CLR)](#push_front)|新しい最初の要素を追加します。|  
|[list::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|  
|[list::remove (STL/CLR)](#remove)|指定した値を持つ要素を削除します。|  
|[list::remove_if (STL/CLR)](#remove_if)|指定されたテストに合格した要素を削除します。|  
|[list::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|  
|[list::resize (STL/CLR)](#resize)|要素の数を変更します。|  
|[list::reverse (STL/CLR)](#reverse)|被制御シーケンスを反転させます。|  
|[list::size (STL/CLR)](#size)|要素の数をカウントします。|  
|[list::sort (STL/CLR)](#sort)|被制御シーケンスを並べ替えます。|  
|[list::splice (STL/CLR)](#splice)|ノード間のリンクを再接合します。|  
|[list::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|  
|[list::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|  
|[list::unique (STL/CLR)](#unique)|指定されたテストに合格した隣接する要素を削除します。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[list::back_item (STL/CLR)](#back_item)|最後の要素にアクセスします。|  
|[list::front_item (STL/CLR)](#front_item)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[list::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|  
|[operator!= (list) (STL/CLR)](#op_neq)|かどうかを`list`オブジェクトが他と等しくない`list`オブジェクト。|  
|[operator< (list) (STL/CLR)](#op_lt)|かどうかを`list`オブジェクトが他よりも小さい`list`オブジェクト。|  
|[operator<= (list) (STL/CLR)](#op_lteq)|かどうかを`list`オブジェクトが別に小さい`list`オブジェクト。|  
|[operator== (list) (STL/CLR)](#op_eq)|かどうかを`list`オブジェクトが他と等しい`list`オブジェクト。|  
|[operator> (list) (STL/CLR)](#op_gt)|かどうかを`list`オブジェクトが他よりも大きい`list`オブジェクト。|  
|[operator>= (list) (STL/CLR)](#op_gteq)|かどうかを`list`オブジェクトがより大きいか等しい間`list`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|IList\<値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>Remarks  
 オブジェクトは、割り当てし、双方向リンク リスト内の個々 のノードとして、制御するシーケンスの記憶域を解放します。 別の 1 つのノードの内容のコピーからではなく、ノード間のリンクを変更して要素を並べ替えます。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。 したがって、一覧には、基になるコンテナー テンプレート クラスには適して[キュー (STL/CLR)](../dotnet/queue-stl-clr.md)またはテンプレート クラス[スタック (STL/CLR)](../dotnet/stack-stl-clr.md)です。  
  
 A`list`オブジェクトがサポートする双方向反復子は、被制御シーケンス内の要素を指定する反復子を指定する、隣接する要素をステップ実行できます。 特殊なヘッド ノードによって返される反復子に対応[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達するリストの反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定されたリストの要素を参照することはできないことに注意してください。 一覧は`not`テンプレート クラスの基になるコンテナーとして使用可能な[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)です。  
  
 リストの反復子は、それに関連付けられているコンテナーへのハンドルを格納する関連付けられたリスト ノードへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 リストの反復子は、関連付けられているリスト ノードのいくつかのリストに関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="assign"></a> list::assign (STL/CLR)
すべての要素を置換します。  
  
### <a name="syntax"></a>構文  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数では、被制御シーケンスを置き換えますの繰り返しで`count`値の要素`val`です。 使用する要素をコンテナーを格納するのに、同じ値を持ちます。  
  
 場合`InIt`整数型の場合は、2 番目のメンバー関数の動作と同じ`assign((size_type)first, (value_type)last)`です。 それ以外の場合、シーケンスを被制御シーケンスを置き換えます [`first`、 `last`)。 使用すると被制御シーケンスのコピーを別のシーケンス。  
  
 3 番目のメンバー関数は、列挙子によって指定されたシーケンスに、被制御シーケンスを置き換えます`right`です。 これを使用するには、被制御シーケンスの列挙子によって説明されているシーケンスのコピーを作成します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
 
## <a name="back"></a> list::back (STL/CLR)
最後の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
reference back();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、空でない必要があります、被制御シーケンスの最後の要素への参照を返します。 存在することがわかっている場合に、最後の要素をアクセスに使用するとします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_back.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  

## <a name="back_item"></a> list::back_item (STL/CLR)
最後の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Remarks  
 プロパティでは、空でない必要があります、被制御シーケンスの最後の要素にアクセスします。 これを使用するには存在することがわかっている場合に、最後の要素を読み書きします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_back_item.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  

## <a name="begin"></a> list::begin (STL/CLR)
被制御シーケンスの先頭を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、または空のシーケンスの最後を越えたところ、被制御シーケンスの最初の要素を指定するランダム アクセス反復子を返します。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さが変更された場合は、被制御シーケンスが、そのステータスの先頭を変更できます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_begin.cpp   
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
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  

## <a name="clear"></a> list::clear (STL/CLR)
すべての要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数が効果的に呼び出し[list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md) `(` [list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md) `(),` [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `())`. これを使用するには、被制御シーケンスが空であることを確認します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  

## <a name="const_iterator"></a> list::const_iterator (STL/CLR)
被制御シーケンスの定数反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T2`被制御シーケンスの定数ランダム アクセス反復子として使用されることができます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_const_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> list::const_reference (STL/CLR)
要素への定数参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、要素への定数参照を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_const_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::list<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> list::const_reverse_iterator (STL/CLR)
被制御シーケンスの定数反転反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T4`被制御シーケンスの定数反転反復子として使用されることができます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="difference_type"></a> list::difference_type (STL/CLR)
2 つの要素間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、符号付き要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_list_difference_type.cpp   
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
  
// compute positive difference   
    cliext::list<wchar_t>::difference_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> list::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
### <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md)`() == 0`です。 これを使用して、リストが空かどうかをテストします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_empty.cpp   
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
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  

## <a name="end"></a> list::end (STL/CLR)
被制御シーケンスの末尾を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの最後の位置を指し示すランダム アクセス反復子を返します。 被制御シーケンスの末尾を指定する反復子を取得するのにために使用します。その状態は、被制御シーケンスの長さが変更された場合は変更されません。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_end.cpp   
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
  
// inspect last two items   
    cliext::list<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  

## <a name="erase"></a> list::erase (STL/CLR)
指定した位置にある要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 消去する範囲の開始しています。  
  
 last  
 消去する範囲の終了。  
  
 where  
 消去する要素。  
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`where`です。 それを使用するには 1 つの要素を削除します。  
  
 2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 これを使用するには 0 個以上の連続する要素を削除します。  
  
 両方のメンバー関数が、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()`このような要素が存在しない場合。  
  
 要素を消去するには、ときに要素のコピーの数は消去の終了と、シーケンスの最も近い最後の要素の数に比例します。 (シーケンスの先頭または末尾にある 1 つまたは複数の要素を消去するには、ときに要素のコピーは発生しません。)  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  

## <a name="front"></a> list::front (STL/CLR)
最初の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
reference front();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、空でない必要があります、被制御シーケンスの最初の要素への参照を返します。 これを使用するには存在することがわかっている場合に、最初の要素を読み書きします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_front.cpp   
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
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  

## <a name="front_item"></a> list::front_item (STL/CLR)
最初の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Remarks  
 プロパティでは、空でない必要があります、被制御シーケンスの最初の要素にアクセスします。 これを使用するには存在することがわかっている場合に、最初の要素を読み書きします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_front_item.cpp   
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
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  

## <a name="generic_container"></a> list::generic_container (STL/CLR)
コンテナーのジェネリック インターフェイスの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IList<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスを表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_generic_container.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(gc1->end(), L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push_back(L'e');   
  
    System::Collections::IEnumerator^ enum1 =   
        gc1->GetEnumerator();   
    while (enum1->MoveNext())   
        System::Console::Write(" {0}", enum1->Current);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  

## <a name="generic_iterator"></a> list::generic_iterator (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するため、反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスで使用できる汎用の反復子を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="generic_reverse_iterator"></a> list::generic_reverse_iterator (STL/CLR)
コンテナーのジェネリック インターフェイスを使用する反転反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスで使用できる汎用反転反復子を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c c  
```  

## <a name="generic_value"></a> list::generic_value (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するための要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、型のオブジェクトを表します。`GValue`ストアド要素の値をこのテンプレートのコンテナー クラスのジェネリック インターフェイスを使用することについて説明します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="insert"></a> list::insert (STL/CLR)
指定した位置にある要素を追加します。  
  
### <a name="syntax"></a>構文  
  
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
  
### <a name="remarks"></a>Remarks  
 メンバーの各関数が指す要素の前に、挿入`where`被制御シーケンスのシーケンスは、残りのオペランドで指定します。  
  
 最初のメンバー関数は、値を持つ要素を挿入します。`val`し、新しく挿入される要素を指定する反復子を返します。 使用する反復子によって指定された場所の前に 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値 `count` の要素を `val` 個挿入します。 使用する同じ値のすべてのコピーである 0 個以上の連続する要素を挿入します。  
  
 `InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合、これは、シーケンスを挿入 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の連続する要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 1 つの要素を挿入するときに要素のコピーの数はカーソルと、シーケンスの最も近い最後の要素の数に比例します。 (1 つまたは複数の要素を挿入する、シーケンスの先頭または末尾にある、ときに要素のコピーは発生しません。)場合`InIt`は入力反復子は、3 番目のメンバー関数は、シーケンス内の各要素の 1 つの挿入を効果的に実行します。 それ以外の場合、挿入するときに`N`要素、要素のコピーの数が線形に`N`+ カーソルと、シーケンスの最も近い最後の要素の数。  
  
### <a name="example"></a>例  
  
```cpp  
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

## <a name="iterator"></a> list::iterator (STL/CLR)
被制御シーケンスの反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T1`被制御シーケンスのランダム アクセス反復子として使用されることができます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x b c  
```  

## <a name="list"></a> list::list (STL/CLR)
コンテナー オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
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
  
### <a name="remarks"></a>Remarks  
  
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
  
### <a name="example"></a>例  
  
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

## <a name="merge"></a> list::merge (STL/CLR)
2 つの被制御シーケンスの順序をマージします。  
  
### <a name="syntax"></a>構文  
  
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
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数によって制御されるシーケンスからのすべての要素を削除する`right`被制御シーケンスに挿入します。 両方のシーケンスで以前注文`operator<`--いずれかのシーケンスの進行中の値で要素を縮小しません必要があります。 によって、結果のシーケンスが順序付けも`operator<`します。 このメンバー関数を使用するには値でも増加するシーケンスに値で増加する 2 つのシーケンスにマージします。  
  
 2 番目のメンバー関数と同様、最初は、順序に並べする点を除いて`pred`  --  `pred(X, Y)`任意の要素に対して false である必要があります`X`要素に依存している`Y`順序で。 使用順を指定するデリゲートの述語関数で 2 つのシーケンスにマージします。  
  
 両方関数は安定したマージの実行 - 結果として得られる被制御シーケンス内の元の被制御シーケンスのいずれかの要素のペアを逆にありません。 また場合の要素のペア`X`と`Y`結果の被制御シーケンスが大小-- `!(X < Y) && !(X < Y)` --によって制御されるシーケンスから要素の前に、の元の被制御シーケンス内の要素が表示されます`right`.  
  
### <a name="example"></a>例  
  
```cpp  
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

## <a name="op_as"></a> list::operator = (STL/CLR)
被制御シーケンスを置き換えます。  
  
### <a name="syntax"></a>構文  
  
```  
list<Value>% operator=(list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするコンテナー。  
  
### <a name="remarks"></a>Remarks  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーと置き換えます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_as.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="pop_back"></a> list::pop_back (STL/CLR)
最後の要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、空でない必要があります、被制御シーケンスの最後の要素を削除します。 使用するを背面にある 1 つの要素で、一覧を短きます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_pop_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  

## <a name="pop_front"></a> list::pop_front (STL/CLR)
最初の要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void pop_front();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、空でない必要があります、被制御シーケンスの最初の要素を削除します。 使用する前に 1 つの要素によって、リストを短縮します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_pop_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  

## <a name="push_back"></a> list::push_back (STL/CLR)
新しい最後の要素を追加します。  
  
### <a name="syntax"></a>構文  
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、値を持つ要素を挿入します。`val`被制御シーケンスの最後にします。 これを使用して、一覧に別の要素を追加します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_push_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="push_front"></a> list::push_front (STL/CLR)
新しい最初の要素を追加します。  
  
### <a name="syntax"></a>構文  
  
```  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、値を持つ要素を挿入します。`val`被制御シーケンスの先頭にします。 使用する前に、一覧に別の要素を付加します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="rbegin"></a> list::rbegin (STL/CLR)
反転被制御シーケンスの先頭を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、最後の要素または空のシーケンスの先頭を越えた、被制御シーケンスの指定、逆順反復子を返します。 したがって、これを指定、`beginning`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合、逆の順序で表示される、被制御シーケンスですがその状態の先頭は変更できます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  

## <a name="reference"></a> list::reference (STL/CLR)
要素への参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、要素への参照を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
A B C  
```  

## <a name="remove"></a> list::remove (STL/CLR)
指定した値を持つ要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void remove(value_type val);  
```  
  
#### <a name="parameters"></a>パラメーター  
 val  
 削除する要素の値です。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数は、被制御シーケンス内の要素を削除する`((System::Object^)val)->Equals((System::Object^)x)`(該当する場合) は true です。 これを使用して、指定の値を持つ任意の要素を消去します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_remove.cpp   
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
  
// fail to remove and redisplay   
    c1.remove(L'A');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();  
  
// remove and redisplay   
    c1.remove(L'b');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c  
```  

## <a name="remove_if"></a> list::remove_if (STL/CLR)
指定されたテストに合格した要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 削除する要素をテストします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンス (消去) から削除のすべての要素`X`を`pred(X)`は true です。 これを使用するには関数またはデリゲートとして指定することが条件を満たすすべての要素を削除します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
``` 

## <a name="rend"></a> list::rend (STL/CLR)
反転被制御シーケンスの末尾を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの先頭位置を指し示す反転反復子を返します。 したがって、これを指定、`end`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合は逆の順序で表示される、被制御シーケンスですがその状態の終了を変更できます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_rend.cpp   
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
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  

## <a name="resize"></a> list::resize (STL/CLR)
要素の数を変更します。  
  
### <a name="syntax"></a>構文  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>パラメーター  
 new_size  
 被制御シーケンスの新しいサイズ。  
  
 val  
 埋め込み要素の値です。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数の両方では、ことを確認[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md) `()`記す返します`new_size`です。 被制御シーケンスを長くする必要がある場合、最初のメンバー関数では値 `value_type()` で要素を追加し、2 番目のメンバー関数では値 `val` で要素を追加します。 被制御シーケンスを短くするために、メンバー関数はどちら効果的に消去の最後の要素[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() -` `new_size`回です。 被制御シーケンスがサイズであることを確認するために使用`new_size`トリミングまたは現在の被制御シーケンスの余白で、します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  

## <a name="reverse"></a> list::reverse (STL/CLR)
被制御シーケンスを反転させます。  
  
### <a name="syntax"></a>構文  
  
```  
void reverse();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンス内のすべての要素の順序を反転させます。 要素の一覧を反映するために使用するとします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_reverse.cpp   
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
  
// reverse and redisplay   
    c1.reverse();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
```  

## <a name="reverse_iterator"></a> list::reverse_iterator (STL/CLR)
被制御シーケンスの反転反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T3`被制御シーケンスの反転反復子として使用されることができます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
x b a  
```  
  
## <a name="size"></a> list::size (STL/CLR)
要素の数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの長さを返します。 これを使用するには、被制御シーケンス内の現在の要素の数を決定します。 シーケンスが参照してください、0 以外のサイズを持つかどうかは、関心のあるすべて場合[list::empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)`()`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_size.cpp   
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
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  

## <a name="size_type"></a> list::size_type (STL/CLR)
2 つの要素の間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、負でない要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_size_type.cpp   
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
  
// compute positive difference   
    cliext::list<wchar_t>::size_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```

## <a name="sort"></a> list::sort (STL/CLR)
被制御シーケンスを並べ替えます。  
  
### <a name="syntax"></a>構文  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 要素のペアの比較子。  
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数は、によって順序がされるように、被制御シーケンス内の要素を再配置`operator<`--進行中は、シーケンス値で要素を縮小しません。 昇順に並べ替え順序を並べ替えるには、このメンバー関数を使用します。  
  
 2 番目のメンバー関数の動作、最初と同じで、シーケンスが順序付けする点を除いて`pred`  --  `pred(X, Y)`は任意の要素に対して false`X`要素に依存している`Y`結果のシーケンスにします。 述語の関数またはデリゲートで指定した順序でシーケンスの並べ替えに使用します。  
  
 両方関数は、安定した並べ替えを実行します。--結果として得られる被制御シーケンス内の元の被制御シーケンス内の要素のペアを逆にありません。  
  
### <a name="example"></a>例  
  
```cpp  
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

## <a name="splice"></a> list::splice (STL/CLR)
ノード間のリンクを restitch です。  
  
### <a name="syntax"></a>構文  
  
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
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数は、挿入によって制御されるシーケンス`right`によって示される、被制御シーケンスの要素の前に`where`です。 これはまた、`right` からすべての要素を削除します (`%right`でなければなりません`this`)。使用するすべての 1 つのリストを別にスプライスします。  
  
 2 番目のメンバー関数によって指し示される要素を削除する`first`によって制御されるシーケンスで`right`被制御シーケンス内の要素を指すの前に挿入し、`where`です。 (場合`where` `==` `first` `||` `where` `== ++first`変更は発生しません)。使用する 1 つのリストの 1 つの要素を別にスプライスします。  
  
 3 番目のメンバー関数によって指定されたサブ範囲を挿入します。 [`first`、 `last`) によって制御されるシーケンスから`right`によって示される、被制御シーケンスの要素の前に`where`です。 これはまた、`right` で制御されるシーケンスから元のサブ範囲を削除します (If `right` `==` `this`、範囲 [`first`、 `last`) によって指し示される要素を含める必要がありますいない`where`)。Splice 0 個以上の要素の 1 つのリストから別のサブシーケンスを使用するとします。  
  
### <a name="example"></a>例  
  
```cpp
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

## <a name="swap"></a> list::swap (STL/CLR)
2 つのコンテナーのコンテンツを交換します。  
  
### <a name="syntax"></a>構文  
  
```  
void swap(list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテンツを交換するコンテナー。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、`*this` と `right` の間で被制御シーケンスを交換します。 定数時間では、例外をスローしません。 2 つのコンテナーの内容を交換する簡単な方法として使用するとします。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_list_swap.cpp   
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
  
// construct another container with repetition of values   
    cliext::list<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```   

## <a name="to_array"></a> list::to_array (STL/CLR)
被制御シーケンスを新しい配列にコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、被制御シーケンスを格納する配列を返します。 使用する配列形式の被制御シーケンスのコピーを入手します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="unique"></a> list::unique (STL/CLR)
指定されたテストに合格した隣接する要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pred  
 要素のペアの比較子。  
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数は、被制御シーケンス (消去) から削除を比較するすべての要素に一致する直前の要素--場合要素`X`要素の前に`Y`と`X == Y`、メンバー関数は削除`Y`です。 使用する、隣接する要素のすべてのサブシーケンスのすべてが 1 つのコピーを削除するのにその比較結果が同じです。 されている場合、被制御シーケンスが順序付けなどの呼び出しによって[list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`、メンバー関数は、一意の値を持つ要素のみのままにします。 (ターミナル メソッドという名前なのはそのためです)。  
  
 2 番目のメンバー関数と同様、最初の各要素を削除する点を除いて`Y`次の要素`X`を`pred(X, Y)`です。 述語関数または指定したデリゲートを満たす隣接する要素のすべてのサブシーケンスのすべてが 1 つのコピーを削除するのに使用するとします。 されている場合、被制御シーケンスが順序付けなどの呼び出しによって`sort(pred)`、メンバー関数と同じ順序付け、他の要素がない要素のみのままにします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  

## <a name="value_type"></a> list::value_type (STL/CLR)
要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーター `Value` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_value_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::list<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
``` 

## <a name="op_neq"></a> operator! = (リスト) (STL/CLR)
等しくない比較を一覧表示します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator!=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子関数を返します`!(left == right)`です。 テストするために使用するかどうか`left`順序付けされていないと同じ`right`と 2 つのリストは、要素で要素を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_ne.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  

## <a name="op_lt"></a> 演算子&lt;(リスト) (STL/CLR)
リストが比較未満です。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator<(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子関数を返す場合は true、最下位の位置の`i`を`!(right[i] < left[i])`も真であることをお勧め`left[i] < right[i]`です。 返しますそれ以外の場合、`left->size() < right->size()`をテストするために使用するかどうか`left`前に順序付け`right`とき要素によって比較対象の要素は、2 つのリスト。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_lt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  

## <a name="op_lteq"></a> 演算子&lt;= (リスト) (STL/CLR)
以下の一覧の比較できます。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator<=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子関数を返します`!(right < left)`です。 テストするために使用するかどうか`left`後に順序付けされていない`right`と 2 つのリストは、要素で要素を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_le.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  

## <a name="op_eq"></a> 演算子 = = (リスト) (STL/CLR)
比較を一覧表示します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator==(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子の関数が、シーケンスがによって制御される場合にのみ true を返します`left`と`right`同じ長さであると、各位置`i`、 `left[i] ==` `right[i]`です。 テストするために使用するかどうか`left`が同じ順序付け`right`と 2 つのリストは、要素で要素を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_eq.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  

## <a name="op_gt"></a> 演算子&gt;(リスト) (STL/CLR)
比較よりも大きい値を一覧表示します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator>(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子関数を返します`right` `<` `left`です。 テストするために使用するかどうか`left`が後に順序付け`right`と 2 つのリストは、要素で要素を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_gt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  

## <a name="op_gteq"></a> 演算子&gt;= (リスト) (STL/CLR)
リストよりも大きいまたは等しい比較します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator>=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
### <a name="remarks"></a>Remarks  
 演算子関数を返します`!(left` `<` `right)`です。 テストするために使用するかどうか`left`する前に順序付けされていない`right`と 2 つのリストは、要素で要素を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_list_operator_ge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
