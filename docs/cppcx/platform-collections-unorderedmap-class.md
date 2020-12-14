---
description: '詳細情報: Platform:: Collections:: UnorderedMap クラス'
title: Platform::Collections::UnorderedMap クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 51acfa7e411f96addd8a33024224779c32ebcda0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242536"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap クラス

キー/値ペアのコレクションである順序なしの *マップ* を表します。

## <a name="syntax"></a>構文

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キー/値ペア内のキーの型。

*V*<br/>
キー/値ペア内の値の型。

*C*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、 [std:: \<K> equal_to](../standard-library/equal-to-struct.md)になります。

### <a name="remarks"></a>解説

使用できる型は次のとおりです。

- integers

- インターフェイスクラス ^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

**UnorderedMap** は基本的に、Windows ランタイム型のストレージをサポートする [std:: unordered_map](../standard-library/unordered-map-class.md) のラッパーです。 これは、パブリック Windows ランタイムインターフェイスで渡される [Windows:: Foundation:: Collections:: IMap](/uwp/api/windows.foundation.collections.imap-2) 型と [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) 型の具象実装です。 パブリックの戻り値またはパラメーターで `Platform::Collections::UnorderedMap` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 エラーを修正するには、パラメーターや戻り値の型を [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2)に変更します。

詳細については、[コレクション](../cppcx/collections-c-cx.md) を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[UnorderedMap:: UnorderedMap](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[UnorderedMap:: Clear](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[UnorderedMap:: First](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[UnorderedMap:: GetView](#getview)|現在のマップの読み取り専用ビューである Platform::Collections::UnorderedMapView クラスを返します。|
|[UnorderedMap:: HasKey](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[UnorderedMap:: Insert](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[UnorderedMap:: Lookup](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[UnorderedMap:: Remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[UnorderedMap:: Size](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>イベント

| 名前 | 説明 |
|--|--|
| [Map:: MapChanged](#mapchanged) イベント | マップが変更されたときに発生します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`UnorderedMap`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a> UnorderedMap:: Clear メソッド

現在の UnorderedMap オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a> UnorderedMap:: First メソッド

順序なしのマップ内の最初の[Windows:: Foundation:: Collections:: \<K,V> ikeyvaluepair<k,](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First () によって返される反復子を保持する便利な方法は、型推論キーワードで宣言された変数に戻り値を代入することです **`auto`** 。 たとえば、「 `auto x = myUnorderedMap->First();` 」のように入力します。

## <a name="unorderedmapgetview-method"></a><a name="getview"></a> UnorderedMap:: GetView メソッド

現在の UnorderedMap の読み取り専用ビューを返します。これは、 [Windows:: Foundation:: collections:: IMapView:: IMapView](/uwp/api/windows.foundation.collections.imapview-2)インターフェイスを実装する[Platform:: Collections:: UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)です。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`UnorderedMapView` オブジェクト。

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a> UnorderedMap:: HasKey メソッド

指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
UnorderedMap 要素の検索に使用するキー。 *キー* の型は typename *K* です。

### <a name="return-value"></a>戻り値

**`true`** キーが見つかった場合は。それ以外の場合は **`false`** 。

## <a name="unorderedmapinsert-method"></a><a name="insert"></a> UnorderedMap:: Insert メソッド

指定したキー/値ペアを現在の UnorderedMap オブジェクトに追加します。

### <a name="syntax"></a>構文

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー* の型は typename *K* です。

*value*<br/>
キー/値ペアの値部分。 *値* の型は typename *V* です。

### <a name="return-value"></a>戻り値

**`true`** 現在のマップ内の既存の要素のキーが *キー* と一致し、その要素の値部分が *value* に設定されている場合は。 **`false`** 現在のマップ内の既存の要素が *キー* と一致せず、キーと *値**のパラメーター* がキーと値のペアになり、現在の UnorderedMap に追加されている場合は。

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a> UnorderedMap:: Lookup メソッド

型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
UnorderedMap の要素の検索に使用するキー。 *キー* の型は typename *K* です。

### <a name="return-value"></a>戻り値

*キー* とペアになる値。 戻り値の型は typename *V* です。

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a> UnorderedMap:: MapChanged

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

イベントを発生させたオブジェクトと発生した変更の種類に関する情報を含む[Mapchangedeventhandler \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) 。 「 [」 \<K> ](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) And [collectionchange 列挙型](/uwp/api/windows.foundation.collections.collectionchange)」も参照してください。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

C# または Visual Basic プロジェクトの IMap として Windows ランタイムアプリを \<K,V> IDictionary として \<K,V> します。

## <a name="unorderedmapremove-method"></a><a name="remove"></a> UnorderedMap:: Remove メソッド

指定したキー/値ペアを UnorderedMap オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー* の型は typename *K* です。

## <a name="unorderedmapsize-method"></a><a name="size"></a> UnorderedMap:: Size メソッド

UnorderedMap 内の[Windows:: Foundation:: Collections:: ikeyvaluepair<k, \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素の数を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

順序なしのマップの要素数。

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a> UnorderedMap:: UnorderedMap コンストラクター

UnorderedMap クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>パラメーター

*初期化*<br/>
現在の UnorderedMap の型名。

*P*<br/>
2 つのキーを比較してそれらが等しいかどうかを判定できる関数オブジェクト。 このパラメーターの既定値は[std: \<K> : equal_to](../standard-library/equal-to-struct.md)です。

*H*<br/>
キーのハッシュ値を生成する関数オブジェクト。 このパラメーターの既定値は、クラスがサポートするキーの種類の [ハッシュクラス 1](../standard-library/hash-class.md) です。

*m*<br/>
現在の UnorderedMap を初期化するために使用される[std:: unordered_map](../standard-library/unordered-map-class.md)への参照または[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)。

*自動車*<br/>
Std: [: initializer_list](../standard-library/initializer-list-class.md) : マップを初期化するために使用される [std::p air](../standard-library/pair-structure.md) オブジェクト。

*first*<br/>
現在の UnorderedMap を初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在の UnorderedMap を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)<br/>
[Platform:: Collections 名前空間](../cppcx/platform-collections-namespace.md)<br/>
[Platform:: Collections:: Map クラス](../cppcx/platform-collections-map-class.md)<br/>
[Platform:: Collections:: UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[コレクション](../cppcx/collections-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
