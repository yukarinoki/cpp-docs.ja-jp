---
title: Platform::Collections::Vector クラス
ms.date: 12/04/2019
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
ms.openlocfilehash: 60c82a113bc19e9652af8c1ad531e1c479077f20
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032123"
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector クラス

インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションを表します。 XAML[データ バインディング](/windows/uwp/data-binding/data-binding-in-depth)を支援する[Windows::ファウンデーション:コレクション::IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1)を実装します。

## <a name="syntax"></a>構文

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
Vector オブジェクトに含まれている要素の型。

*E*<br/>
*型 T*の値と等しい値をテストするための二項述語を指定します。既定値は です`std::equal_to<T>`。

### <a name="remarks"></a>解説

使用できる型は次のとおりです。

1. 整数

1. インターフェイス クラス^

1. パブリック ref クラス ^

1. value struct

1. パブリック列挙型クラス

**ベクター**クラスは[、Windows::Foundation::コレクション::IVector](/uwp/api/windows.foundation.collections.ivector-1)インターフェイスの C++ 具体的な実装です。

パブリックの戻り値またはパラメーターで**Vector**型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーを修正するには、パラメーターまたは戻り値の型を [Windows::Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1)に変更します。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ベクトル::ベクトル](#ctor)|ベクター クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Vector::Append](#append)|指定された項目を、現在の Vector の最後の項目の後に挿入します。|
|[ベクトル::クリア](#clear)|現在のベクター内のすべての要素を削除します。|
|[ベクトル::最初](#first)|Vector 内の最初の要素を指定する反復子を返します。|
|[ベクトル::ゲットアット](#getat)|指定されたインデックスで識別される現在のベクターの要素を取得します。|
|[ベクトル::ゲットマニー](#getmany)|指定されたインデックスを開始位置として、現在の Vector から項目のシーケンスを取得します。|
|[ベクトル::ゲットビュー](#getview)|ベクターの読み取り専用ビュー、つまり [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)を返します。|
|[ベクトル::インデックスOf](#indexof)|現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|
|[Vector::InsertAt](#insertat)|指定した項目を、指定したインデックスで識別される要素の現在のベクターに挿入します。|
|[Vector::ReplaceAll](#replaceall)|現在のベクターの要素を削除し、指定された配列の要素を挿入します。|
|[Vector::RemoveAt](#removeat)|現在のベクターから指定されたインデックスで識別される要素を削除します。|
|[Vector::RemoveAtEnd](#removeatend)|現在の Vector の末尾から要素を削除します。|
|[Vector::SetAt](#setat)|現在の Vector で、指定されたインデックスによって識別される要素に、指定された値を割り当てます。|
|[ベクトル::サイズ](#size)|現在のベクター オブジェクトの要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|イベント[ウィンドウズ::ファウンデーション:コレクション::ベクター\<変更イベントハンドラT>^ ベクトル変更](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1)|Vector が変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Vector`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectorappend-method"></a><a name="append"></a>ベクトル::追加メソッド

指定された項目を、現在の Vector の最後の項目の後に挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
Vector に挿入する項目。 *項目*のタイプは T*型名*で定義されます。

## <a name="vectorclear-method"></a><a name="clear"></a>ベクトル::クリアメソッド

現在のベクター内のすべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a>ベクトル::最初の方法

Vector 内の最初の要素を指す反復子を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>戻り値

Vector 内の最初の要素を指す反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myVector->First();` 」のように入力します。 この反復子は、コレクションの長さを認識しています。

STL 関数に渡す反復子のペアが必要な場合は、フリー関数を使用[します。](../cppcx/begin-function.md) [Windows::Foundation::Collections::end](../cppcx/end-function.md)

## <a name="vectorgetat-method"></a><a name="getat"></a>ベクトル::GetAtメソッド

指定されたインデックスで識別される現在のベクターの要素を取得します。

### <a name="syntax"></a>構文

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

### <a name="return-value"></a>戻り値

*インデックス*パラメーターで指定された要素。 要素の型は*T*型名で定義されます。

## <a name="vectorgetmany-method"></a><a name="getmany"></a>ベクトル::Get多くのメソッド

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
*startIndex*で指定された要素から始まり、Vector の最後の要素で終了する、呼び出し元が割り当てた項目の配列。

### <a name="return-value"></a>戻り値

取得した項目数。

### <a name="remarks"></a>解説

この関数は、直接クライアント コードで使用することを目的としたものではありません。 これは、プラットフォーム::ベクトルインタンスをstd::vectorインスタンスに効率的に変換できるようにするために[、to_vector関数](../cppcx/to-vector-function.md)で内部的に使用されます。

## <a name="vectorgetview-method"></a><a name="getview"></a>ベクトル::GetViewメソッド

Vector の読み取り専用ビュー、つまり IVectorView を返します。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>戻り値

IVectorView オブジェクト。

## <a name="vectorindexof-method"></a><a name="indexof"></a>ベクトル::インデックスのメソッド

現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。

### <a name="syntax"></a>構文

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
検索する項目。

*index*<br/>
パラメーター*値*が見つかった場合は、項目の 0 から始まるインデックス。それ以外の場合は 0。

項目が Vector の最初の要素であるか、または項目が見つからなかった場合 *、index*パラメーターは 0 です。 戻り値が**true**の場合、項目が見つかり、最初の要素になります。それ以外の場合、アイテムは見つかりませんでした。

### <a name="return-value"></a>戻り値

指定した項目が見つかった場合は true、指定したアイテムが見つかった場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

IndexOf は、std::find_if を使用して項目を検索します。 このため、find_if が必要とする等価比較を有効にするために、カスタム要素の種類で == および != 演算子をオーバーロードする必要があります。

## <a name="vectorinsertat-method"></a><a name="insertat"></a>ベクトル::挿入メソッド

指定した項目を、指定したインデックスで識別される要素の現在のベクターに挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

*item*<br/>
*index*で指定された要素のベクターに挿入する項目。 *項目*のタイプは T*型名*で定義されます。

## <a name="vectorremoveat-method"></a><a name="removeat"></a>ベクトル::RemoveAtメソッド

現在のベクターから指定されたインデックスで識別される要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a>ベクトル::RemoveAtEndメソッド

現在の Vector の末尾から要素を削除します。

### <a name="syntax"></a>構文

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a>ベクトル::すべてのメソッドを置換

現在のベクターの要素を削除し、指定された配列の要素を挿入します。

### <a name="syntax"></a>構文

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>パラメーター

*Arr*<br/>
型が*T*型名で定義されているオブジェクトの配列。

## <a name="vectorsetat-method"></a><a name="setat"></a>ベクトル::セットアットメソッド

現在の Vector で、指定されたインデックスによって識別される要素に、指定された値を割り当てます。

### <a name="syntax"></a>構文

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

*item*<br/>
指定された要素に代入する値。 *項目*のタイプは T*型名*で定義されます。

## <a name="vectorsize-method"></a><a name="size"></a>ベクトル::サイズ法

現在のベクター オブジェクトの要素数を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

現在の Vector 内の要素数。

## <a name="vectorvector-constructor"></a><a name="ctor"></a>ベクトル::ベクトルコンストラクタ

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

*A*<br/>
ベクトルの初期化に使用される[std::配列](../standard-library/array-class-stl.md)。

*Arr*<br/>
ベクトルの初期化に使用される[プラットフォーム::配列](../cppcx/platform-array-class.md)。

*Init*<br/>
現在のベクターを初期化するために使用されるオブジェクトのコレクションの型。

*イリノイ*<br/>
ベクトルの初期化に使用される*T*型のオブジェクトの[std::initializer_list。](../standard-library/initializer-list-class.md)

*N*<br/>
現在のベクターを初期化するために使用されるオブジェクトのコレクションの要素数。

*size*<br/>
ベクターの要素数。

*value*<br/>
現在のベクターの各要素を初期化するために使用される値。

*V*<br/>
現在のベクトルを初期化するために使用される[std::vector](../standard-library/vector-class.md)への[Lvalues および Rvalues。](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ptr*<br/>
現在のベクターを初期化するために使用される `std::vector` へのポインター。

*first*<br/>
現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最初の要素。 *最初*のタイプは*完全な転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

*last*<br/>
現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最後の要素。 *最後*のタイプは*完全な転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コレクション (C++/CX)](collections-c-cx.md)<br/>
[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
