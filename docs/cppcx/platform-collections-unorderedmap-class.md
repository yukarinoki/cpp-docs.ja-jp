---
title: Platform::Collections::UnorderedMap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbc1905023f64c4983cf041eda244b28ce507abc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap クラス

キー/値ペアのコレクションである順序なしの *マップ*を表します。

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

*K*  
キー/値ペア内のキーの型。

*V*  
キー/値ペア内の値の型。

*C*  
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、 [std::equal_to\<K >](../standard-library/equal-to-struct.md)です。

### <a name="remarks"></a>コメント

使用できる型は次のとおりです。

- 整数

- インターフェイス クラス ^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

**UnorderedMap**のラッパーは、基本的に[std::unordered_map](../standard-library/unordered-map-class.md) Windows ランタイム型の記憶域をサポートします。 具象実装、 [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)と[IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_)パブリック間で渡される型の Windows ランタイム インターフェイスです。 パブリックの戻り値またはパラメーターで `Platform::Collections::UnorderedMap` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 パラメーターまたは戻り値の型を変更することで、エラーを修正することができます[Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)です。

詳細については、次を参照してください。[コレクション](../cppcx/collections-c-cx.md)です。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[UnorderedMap::First](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[UnorderedMap::GetView](#getview)|現在のマップの読み取り専用ビューである Platform::Collections::UnorderedMapView クラスを返します。|
|[UnorderedMap::HasKey](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[Unorderedmap::insert](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[UnorderedMap::Lookup](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[UnorderedMap::Remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[UnorderedMap::Size](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|[Map::mapchanged](#mapchanged)イベント|マップが変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`UnorderedMap`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="clear"></a>  Unorderedmap::clear メソッド

現在の UnorderedMap オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="first"></a>  Unorderedmap::first メソッド

1 つを指定する反復子を返します[Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)順序なしのマップ内の要素。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ 
   First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>コメント

First() によって返される反復子を保持する便利な方法で宣言された変数に戻り値を割り当てるには、**自動**推論キーワードを入力します。 たとえば、`auto x = myUnorderedMap->First();` のようにします。

## <a name="getview"></a>  Unorderedmap::getview メソッド

現在の UnorderedMap の読み取り専用ビューを返しますつまり、 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)を実装する、 [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)インターフェイスです。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`UnorderedMapView` オブジェクト。

## <a name="haskey"></a>  Unorderedmap::haskey メソッド

指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*  
UnorderedMap 要素の検索に使用するキー。 型*キー* typename は*K*です。

### <a name="return-value"></a>戻り値

キーが見つかった場合は `true`。それ以外の場合は `false`。

## <a name="insert"></a>  UnorderedMap::Insert Method

指定したキー/値ペアを現在の UnorderedMap オブジェクトに追加します。

### <a name="syntax"></a>構文

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>パラメーター

*key*  
キー/値ペアのキー部分。 型*キー* typename は*K*です。

*値*  
キー/値ペアの値部分。 型*値*typename は*V*です。

### <a name="return-value"></a>戻り値

`true` 現在のマップ内の既存の要素のキーと一致するかどうかは*キー*し、その要素の値部分に設定されている*値*です。 `false` 現在のマップ内の既存の要素が一致しない場合*キー*と*キー*と*値*パラメーターがキー/値ペアになっていて、現在の UnorderedMap に追加します。

## <a name="lookup"></a>  Unorderedmap::lookup メソッド

型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*  
UnorderedMap の要素の検索に使用するキー。 型*キー* typename は*K*です。

### <a name="return-value"></a>戻り値

ペアになり、値、*キー*です。 戻り値の型は typename *V*です。

## <a name="mapchanged"></a>  Unorderedmap::mapchanged

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx)イベント、および発生した変更の種類を発生させたオブジェクトに関する情報を格納します。 関連項目[IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx)と[collectionchange Enumeration 列挙型](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)です。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

C# または Visual Basic プロジェクト IMap 使用する Windows ランタイム アプリ\<K, V > を IDictionary として\<K, V >。

## <a name="remove"></a>  Unorderedmap::remove メソッド

指定したキー/値ペアを UnorderedMap オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>パラメーター

*key*  
キー/値ペアのキー部分。 型*キー* typename は*K*です。

## <a name="size"></a>  Unorderedmap::size メソッド

数を返します[Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMap の要素。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

順序なしのマップの要素数。

## <a name="ctor"></a>  UnorderedMap::UnorderedMap コンストラクター

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

*InIt*  
現在の UnorderedMap の型名。

*P*  
2 つのキーを比較してそれらが等しいかどうかを判定できる関数オブジェクト。 このパラメーターの既定値[std::equal_to\<K >](../standard-library/equal-to-struct.md)です。

*H*  
キーのハッシュ値を生成する関数オブジェクト。 このパラメーターの既定値[クラス 1 をハッシュ](../standard-library/hash-class.md)キーの型をクラスでサポートされるのです。

*m*  
参照または[Lvalue と Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)を[std::unordered_map](../standard-library/unordered-map-class.md)現在の UnorderedMap を初期化するために使用されます。

*il* A [std::initializer_list](../standard-library/initializer-list-class.md)の[std::pair](../standard-library/pair-structure.md)マップを初期化するために使用されるオブジェクト。

*first*  
現在の UnorderedMap を初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*  
現在の UnorderedMap を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="see-also"></a>関連項目

[プラットフォーム Namespace](platform-namespace-c-cx.md)  
[Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)  
[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)  
[Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)  
[コレクション](../cppcx/collections-c-cx.md)  
[C++ での Windows ランタイム コンポーネントを作成します。](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
