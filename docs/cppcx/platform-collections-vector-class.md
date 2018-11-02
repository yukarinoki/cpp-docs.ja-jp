---
title: Platform::Collections::Vector クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: fb03f7a00dfabe9d082ca761552af99e552d3190
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499870"
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector クラス

インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションを表します。

## <a name="syntax"></a>構文

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
Vector オブジェクトに含まれている要素の型。

*E*<br/>
型の値と等しいかどうかをテストする二項述語を指定します*T*します。既定値は `std::equal_to<T>` です。

### <a name="remarks"></a>Remarks

使用できる型は次のとおりです。

1. 整数

1. インターフェイス クラス ^

1. パブリック ref クラス ^

1. value struct

1. パブリック列挙型クラス

**ベクター**クラスは、C++ の具象実装、 [:ivector](/uwp/api/Windows.Foundation.Collections.IVector_T_)インターフェイス。

使用しようとした場合、**ベクター**入力パブリックの戻り値またはパラメーター、コンパイラ エラー C3986 が発生します。 このエラーを修正するには、パラメーターまたは戻り値の型を [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_)に変更します。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Vector::vector](#ctor)|ベクター クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Vector::append](#append)|指定された項目を、現在の Vector の最後の項目の後に挿入します。|
|[Vector::clear](#clear)|現在のベクター内のすべての要素を削除します。|
|[Vector::first](#first)|Vector 内の最初の要素を指定する反復子を返します。|
|[Vector::GetAt](#getat)|指定されたインデックスで識別される現在のベクターの要素を取得します。|
|[Vector::getmany](#getmany)|指定されたインデックスを開始位置として、現在の Vector から項目のシーケンスを取得します。|
|[Vector::getview](#getview)|ベクターの読み取り専用ビュー、つまり [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)を返します。|
|[Vector::indexof](#indexof)|現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|
|[Vector::insertat](#insertat)|指定されたインデックスによって識別される要素の後の現在のベクターに、指定された項目を挿入します。|
|[Vector::ReplaceAll](#replaceall)|現在のベクターの要素を削除し、指定された配列の要素を挿入します。|
|[Vector::RemoveAt](#removeat)|現在のベクターから指定されたインデックスで識別される要素を削除します。|
|[Vector::RemoveAtEnd](#removeatend)|現在の Vector の末尾から要素を削除します。|
|[Vector::setat](#setat)|現在の Vector で、指定されたインデックスによって識別される要素に、指定された値を割り当てます。|
|[Vector::size](#size)|現在のベクター オブジェクトの要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|イベント[Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](/uwp/api/windows.foundation.collections.vectorchangedeventhandler)|Vector が変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Vector`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="append"></a>  Vector::append メソッド

指定された項目を、現在の Vector の最後の項目の後に挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
Vector に挿入する項目。 型*項目*によって定義されます、 *T* typename。

## <a name="clear"></a>  Vector::clear メソッド

現在のベクター内のすべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="first"></a>  Vector::first メソッド

Vector 内の最初の要素を指す反復子を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>戻り値

Vector 内の最初の要素を指す反復子。

### <a name="remarks"></a>Remarks

First() によって返される反復子を保持する便利な方法で宣言された変数に戻り値を割り当てるには、**自動**推論キーワードを入力します。 たとえば、`auto x = myVector->First();` のようにします。 この反復子は、コレクションの長さを認識しています。

STL 関数に渡すを指す反復子のペアが必要なときは、無料の関数を使用して[:foundation:: 開始](../cppcx/begin-function.md)と[:end](../cppcx/end-function.md)

## <a name="getat"></a>  Vector::getat メソッド

指定されたインデックスで識別される現在のベクターの要素を取得します。

### <a name="syntax"></a>構文

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

### <a name="return-value"></a>戻り値

により指定される要素、*インデックス*パラメーター。 要素の型によって定義されます、 *T* typename。

## <a name="getmany"></a>  Vector::getmany メソッド

指定されたインデックスを開始位置として、現在の Vector から項目のシーケンスを取得し、呼び出し元が割り当てた配列にコピーします。

### <a name="syntax"></a>構文

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>パラメーター

*startIndex*<br/>
取得する項目の 0 から始まるインデックス。

*dest*<br/>
指定した要素から開始する項目の呼び出し元が割り当てた配列*startIndex*とベクターの最後の要素で終了します。

### <a name="return-value"></a>戻り値

取得した項目数。

### <a name="remarks"></a>Remarks

この関数は、直接クライアント コードで使用することを目的としたものではありません。 内部で使用される、 [to_vector 関数](../cppcx/to-vector-function.md)Platform::Vector インスタンスの std::vector インスタンスへの効率的な変換を有効にします。

## <a name="getview"></a>  Vector::getview メソッド

Vector の読み取り専用ビュー、つまり IVectorView を返します。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>戻り値

IVectorView オブジェクト。

## <a name="indexof"></a>  Vector::indexof メソッド

現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。

### <a name="syntax"></a>構文

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>パラメーター

*値*<br/>
検索する項目。

*index*<br/>
項目の 0 から始まるインデックス場合パラメーター*値*。 それ以外は 0。

*インデックス*項目は、ベクターの最初の要素か、項目が見つからなかった場合、パラメーターが 0 です。 場合、戻り値は**true**項目が見つかったと最初の要素を;、それ以外の場合、項目が見つかりません。

### <a name="return-value"></a>戻り値

**true**場合、指定した項目が見つからなかった場合は、 **false**します。

### <a name="remarks"></a>Remarks

IndexOf は、std::find_if を使用して項目を検索します。 このため、find_if が必要とする等価比較を有効にするために、カスタム要素の種類で == および != 演算子をオーバーロードする必要があります。

##  <a name="insertat"></a>  Vector::insertat メソッド

指定されたインデックスによって識別される要素の後の現在のベクターに、指定された項目を挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

*item*<br/>
指定された要素の後にベクターに挿入する項目*インデックス*します。 型*項目*によって定義されます、 *T* typename。

## <a name="removeat"></a>  Vector::removeat メソッド

現在のベクターから指定されたインデックスで識別される要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

## <a name="removeatend"></a>  Vector::removeatend メソッド

現在の Vector の末尾から要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void RemoveAtEnd();
```

## <a name="replaceall"></a>  Vector::replaceall メソッド

現在のベクターの要素を削除し、指定された配列の要素を挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>パラメーター

*arr*<br/>
型が定義されているオブジェクトの配列、 *T* typename。

## <a name="setat"></a>  Vector::setat メソッド

現在の Vector で、指定されたインデックスによって識別される要素に、指定された値を割り当てます。

### <a name="syntax"></a>構文

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

*item*<br/>
指定された要素に代入する値。 型*項目*によって定義されます、 *T* typename。

## <a name="size"></a>  Vector::size メソッド

現在のベクター オブジェクトの要素数を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

現在の Vector 内の要素数。

## <a name="ctor"></a>  Vector::vector コンス トラクター

ベクター クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>パラメーター

*a*<br/>
A [std::array](../standard-library/array-class-stl.md)ベクターを初期化するために使用されます。

*arr*<br/>
A [platform::array](../cppcx/platform-array-class.md)ベクターを初期化するために使用されます。

*InIt*<br/>
現在のベクターを初期化するために使用されるオブジェクトのコレクションの型。

*il*<br/>
A [std::initializer_list](../standard-library/initializer-list-class.md)型のオブジェクトの*T*ベクターを初期化するために使用されます。

*N*<br/>
現在のベクターを初期化するために使用されるオブジェクトのコレクションの要素数。

*size*<br/>
ベクターの要素数。

*値*<br/>
現在のベクターの各要素を初期化するために使用される値。

*v*<br/>
[Lvalues と Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)を[std::vector](../standard-library/vector-class.md)現在のベクターを初期化するために使用されます。

*ptr*<br/>
現在のベクターを初期化するために使用される `std::vector` へのポインター。

*first*<br/>
現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最初の要素。 型*最初*によって渡される*完全転送*します。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

*last*<br/>
現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最後の要素。 型*最後*によって渡される*完全転送*します。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プラットフォーム Namespace](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)