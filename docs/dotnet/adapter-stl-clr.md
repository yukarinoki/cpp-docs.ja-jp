---
title: アダプター (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/15/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a472284df67993a65de98df7db698ea533451ea3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079437"
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)
STL/CLR ヘッダー `<cliext/adapter>` 2 つのテンプレート クラスを指定します (`collection_adapter`と`range_adapter`)、およびテンプレート関数は、`make_collection`です。  
  
## <a name="syntax"></a>構文  
  
```  
#include <cliext/adapter>  
```  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext 
  
## <a name="declarations"></a>宣言  
  
|クラス|説明|  
|-----------|-----------------|  
|[collection_adapter (STL/CLR)](#collection_adapter)|範囲として基本クラス ライブラリ (BCL) コレクションをラップします。|  
|[range_adapter (STL/CLR)](#range_adapter)|BCL コレクションとして範囲をラップします。|  

|関数|説明|  
|--------------|-----------------|  
|[make_collection (STL/CLR)](#make_collection)|反復子のペアを使用して範囲アダプターを作成します。|   
  
## <a name="members"></a>メンバー

## <a name="collection_adapter"></a> collection_adapter (STL/CLR)
STL/CLR コンテナーとして使用するための .NET コレクションをラップします。 A`collection_adapter`単純 STL/CLR コンテナー オブジェクトを表すテンプレート クラスです。 メソッドは、基本クラス ライブラリ (BCL) インターフェイスをラップし、被制御シーケンスの操作に使用する反復子のペアを返します。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
##### <a name="parameters"></a>パラメーター  
 Coll  
 ラップされたコレクションの型。  
  
### <a name="specializations"></a>特殊化  
  
|特殊化|説明|  
|--------------------|-----------------|  
|IEnumerable|要素間のシーケンス。|  
|ICollection|要素のグループを保持します。|  
|IList|要素の順序付きのグループを保持します。|  
|IDictionary|{キー、値} のセットの管理のペア。|  
|IEnumerable\<値 >|型指定された要素をシーケンス。|  
|ICollection\<値 >|型指定された要素のグループを保持します。|  
|IList\<値 >|型指定された要素の順序付きのグループを保持します。|  
|IDictionary\<値 >|型指定された {キー、値} のセットを維持のペア。|  
  
### <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[collection_adapter::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|  
|[collection_adapter::key_type (STL/CLR)](#key_type)|ディクショナリのキーの型。|  
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|ディクショナリの値の型。|  
|[collection_adapter::reference (STL/CLR)](#reference)|要素への参照の型です。|  
|[collection_adapter::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[collection_adapter::value_type (STL/CLR)](#value_type)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](#base)|ラップされた BCL インターフェイスを指定します。|  
|[collection_adapter::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|  
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|アダプター オブジェクトを構築します。|  
|[collection_adapter::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|  
|[collection_adapter::size (STL/CLR)](#size)|要素の数をカウントします。|  
|[collection_adapter::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](#op_eq)|格納された BCL ハンドルを置換します。|  
  
### <a name="remarks"></a>Remarks  
 STL/CLR コンテナーとして BCL コンテナーを操作するのにには、このテンプレート クラスを使用します。 `collection_adapter`要素のシーケンスを制御 BCL インターフェイスへのハンドルを格納します。 A`collection_adapter`オブジェクト`X`入力反復子のペアを返します`X.begin()`と`X.end()`の順序で、要素のアクセスに使用することです。 特化された型の一部も記述できます`X.size()`被制御シーケンスの長さを決定します。  

## <a name="base"></a> collection_adapter::base (STL/CLR)
ラップされた BCL インターフェイスを指定します。  
  
### <a name="syntax"></a>構文  
  
```  
Coll^ base();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、格納された BCL インターフェイス ハンドルを返します。  
  
### <a name="example"></a>例  
  
```cpp
// cliext_collection_adapter_base.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
base() same = True  
```  

## <a name="begin"></a> collection_adapter::begin (STL/CLR)
被制御シーケンスの先頭を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、または空のシーケンスの最後を越えたところ、被制御シーケンスの最初の要素を指定する入力反復子を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_begin.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mycoll::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  

## <a name="collection_adapter_collection_adapter"></a> collection_adapter::collection_adapter (STL/CLR)
アダプター オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### <a name="parameters"></a>パラメーター  
 コレクション  
 ラップする BCL ハンドルです。  
  
 右  
 コピーするオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 : コンス トラクター  
  
 `collection_adapter();`  
  
 格納されたハンドル初期化`nullptr`です。  
  
 : コンス トラクター  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 格納されたハンドル初期化`right.` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`です。  
  
 : コンス トラクター  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 格納されたハンドル初期化`right->` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`です。  
  
 : コンス トラクター  
  
 `collection_adapter(Coll^ collection);`  
  
 使用したストアド ハンドルを初期化します`collection`です。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
base() null = True  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="difference_type"></a> collection_adapter::difference_type (STL/CLR)
2 つの要素間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、符号付き要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_collection_adapter_difference_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mycoll::difference_type diff = 0;   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="end"></a> collection_adapter::end (STL/CLR)
被制御シーケンスの末尾を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの最後の位置を指し示す入力反復子を返します。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_collection_adapter_end.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="iterator"></a> collection_adapter::iterator (STL/CLR)
被制御シーケンスの反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T1`被制御シーケンスの入力反復子として使用されることができます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_iterator.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="key_type"></a> collection_adapter::key_type (STL/CLR)
ディクショナリのキーの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーターのシノニム`Key`に特殊化で`IDictionary`または`IDictionary<Value>`です。 それ以外の場合は定義されません。  
  
### <a name="example"></a>例  
  
```cpp
// cliext_collection_adapter_key_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="mapped_type"></a> collection_adapter::mapped_type (STL/CLR)
ディクショナリの値の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Value mapped_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーターのシノニム`Value`に特殊化で`IDictionary`または`IDictionary<Value>`です。 それ以外の場合は定義されません。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_mapped_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="op_eq"></a> collection_adapter::operator = (STL/CLR)
格納された BCL ハンドルを置換します。  
  
### <a name="syntax"></a>構文  
  
```  
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするアダプター。  
  
### <a name="remarks"></a>Remarks  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 使用してに格納された BCL ハンドルのコピーで格納された BCL ハンドルを置換する`right`です。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_collection_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mycoll c2;   
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

## <a name="reference"></a> collection_adapter::reference (STL/CLR)
要素への参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、要素への参照を表します。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_collection_adapter_reference.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mycoll::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="size"></a> collection_adapter::size (STL/CLR)
要素の数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの長さを返します。 特殊化で定義されていない`IEnumerable`または`IEnumerable<Value>`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="size_type"></a> collection_adapter::size_type (STL/CLR)
2 つの要素の間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、負でない要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_size_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    Mycoll::size_type size = c1.size();   
    System::Console::WriteLine("size() = {0}", size);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="swap"></a> collection_adapter::swap (STL/CLR)
2 つのコンテナーのコンテンツを交換します。  
  
### <a name="syntax"></a>構文  
  
```  
void swap(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテンツを交換するコンテナー。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数は、スワップの間で格納されている BCL ハンドル`*this`と`right`です。  
  
### <a name="example"></a>例  
  
```cpp
// cliext_collection_adapter_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
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

## <a name="value_type"></a> collection_adapter::value_type (STL/CLR)
要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーターのシノニム`Value`、それ以外の場合のシノニムがある特殊化; に存在する場合`System::Object^`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_collection_adapter_value_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display contents " a b c" using value_type   
    for (Mycoll::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mycoll::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="make_collection"></a> make_collection (STL/CLR)
ように、`range_adapter`反復子のペアにします。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Iter`  
 ラップされた反復子の型。  
  
 `first`  
 ラップする最初の反復子。  
  
 `last`  
 ラップする 2 つ目の反復子。  
  
### <a name="remarks"></a>Remarks  
 このテンプレート関数は `gcnew range_adapter<Iter>(first, last)` を返します。 構築するために使用する、`range_adapter<Iter>`反復子のペアからのオブジェクト。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
Count = 3  
IsSynchronized = False  
SyncRoot not nullptr = True  
 | a b c |  
```  

## <a name="range_adapter"></a> range_adapter (STL/CLR)
いくつかの基本クラス ライブラリ (BCL) インターフェイスを実装するために使用する反復子のペアをラップするテンプレート クラス。 使用する、range_adapter 操作 STL/CLR 範囲 BCL コレクションの場合と同様です。  
  
### <a name="syntax"></a>構文  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 Iter  
 ラップされた反復子に関連付けられている型。  
  
### <a name="members"></a>メンバー  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|アダプター オブジェクトを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|格納された反復子のペアを置き換えます。|  
  
### <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|コレクション内の要素を反復処理します。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|コレクション内の型指定された要素を反復処理.|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|  
  
### <a name="remarks"></a>Remarks  
 Range_adapter は、さらに要素のシーケンスを区切る反復子のペアを格納します。 オブジェクトは、順序内の要素を反復処理するのに便利な次の 4 つの BCL インターフェイスを実装します。 BCL コンテナーと同様に STL/CLR 範囲を操作するのにには、このテンプレート クラスを使用します。  

## <a name="range_adapter_op_eq"></a> range_adapter::operator = (STL/CLR)
格納された反復子のペアを置き換えます。  
  
### <a name="syntax"></a>構文  
  
```  
range_adapter<Iter>% operator=(range_adapter<Iter>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするアダプター。  
  
### <a name="remarks"></a>Remarks  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 使用してに格納された反復子のペアのコピーで、格納された反復子のペアを置換する`right`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_range_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Myrange c1(d1.begin(), d1.end());   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myrange c2;   
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

## <a name="range_adapter_range_adapter"></a> range_adapter::range_adapter (STL/CLR)
アダプター オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 ラップする最初の反復子。  
  
 last  
 ラップする 2 つ目の反復子。  
  
 右  
 コピーするオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 : コンス トラクター  
  
 `range_adapter();`  
  
 既定で構築される反復子を持つ格納された反復子のペアを初期化します。  
  
 : コンス トラクター  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 格納されている組み合わせをコピーして格納された反復子のペアを初期化`right`です。  
  
 : コンス トラクター  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 格納されている組み合わせをコピーして格納された反復子のペアを初期化`*right`です。  
  
 : コンス トラクター  
  
 `range_adapter(Iter^ first, last);`  
  
 格納された反復子のペアを初期化します`first`と`last`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c  
```  