---
title: Platform::Collections::UnorderedMap クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 80b46cb95f2fdb83922ca22e8aa06a89aca4bfde
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031499"
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

*K*<br/>
キー/値ペア内のキーの型。

*V*<br/>
キー/値ペア内の値の型。

*C*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では[、std::equal_to\<K>。 ](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>解説

使用できる型は次のとおりです。

- 整数

- インターフェイス クラス^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

**順序なしマップ**は、基本的には、Windows ランタイム型のストレージをサポートする[std::unordered_map](../standard-library/unordered-map-class.md)のラッパーです。 これは、パブリック Windows ランタイム インターフェイス間で渡される[Windows::Foundation::コレクション::IMap](/uwp/api/windows.foundation.collections.imap-2)型と[IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2)型の具体的な実装です。 パブリックの戻り値またはパラメーターで `Platform::Collections::UnorderedMap` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 エラーを修正するには、パラメーターや戻り値の型を [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2)に変更します。

詳細については、[コレクション](../cppcx/collections-c-cx.md) を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[順序付けされていないマップ::順序のないマップ](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[順序付けされていないマップ::クリア](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[順序付けされていないマップ::最初](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[順序付けされていないマップ::GetView](#getview)|現在のマップの読み取り専用ビューである Platform::Collections::UnorderedMapView クラスを返します。|
|[順序付けされていないマップ::ハスキー](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[順序指定されていないマップ::挿入](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[順序指定されていないマップ::ルックアップ](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[順序指定されていないマップ::削除](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[順序指定されていないマップ::サイズ](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|[マップ:マップ変更イベント](#mapchanged)|マップが変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`UnorderedMap`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a>順序指定されていないマップ::メソッドのクリア

現在の UnorderedMap オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a>順序指定されていないマップ::最初のメソッド

順序付けられていないマップ内の最初の[Windows::Foundation::コレクション::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myUnorderedMap->First();` 」のように入力します。

## <a name="unorderedmapgetview-method"></a><a name="getview"></a>順序指定されていないマップ::GetView メソッド

現在の UnorderedMap の読み取り専用ビューを返します。つまり、[プラットフォーム::コレクション::順序指定されていないマップビュー クラス](../cppcx/platform-collections-unorderedmapview-class.md)を実装する[クラス](/uwp/api/windows.foundation.collections.imapview-2)を実装します。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`UnorderedMapView` オブジェクトです。

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a>順序付けされていないマップ::ハスキーメソッド

指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
UnorderedMap 要素の検索に使用するキー。 *キー*の種類は型名*K*です。

### <a name="return-value"></a>戻り値

キーが見つかった場合は**true。** それ以外の場合**は false。**

## <a name="unorderedmapinsert-method"></a><a name="insert"></a>順序指定されていないマップ::メソッドの挿入

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
キー/値ペアのキー部分。 *キー*の種類は型名*K*です。

*value*<br/>
キー/値ペアの値部分。 *値*の型は型名*V*です。

### <a name="return-value"></a>戻り値

現在の Map 内の既存の要素のキーが*キー*に一致し、その要素の値部分が*value*に設定されている場合は**true。** 現在のマップ内の既存の要素が*キー*と一致しない場合、*キー*と*値*のパラメータがキーと値のペアに作成され、現在の UnorderedMap に追加された場合は**false。**

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a>順序指定されていないマップ::ルックアップ メソッド

型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
UnorderedMap の要素の検索に使用するキー。 *キー*の種類は型名*K*です。

### <a name="return-value"></a>戻り値

*キー*と対になっている値。 戻り値の型は型名*V*です。

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a>順序指定されていないマップ::マップが変更されました

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

イベントを発生させたオブジェクトと発生した変更の種類に関する情報を含む>。 [\<](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) [「iMapChangedEventArgs\<K>」](/uwp/api/windows.foundation.collections.imapchangedeventargs-1)および「[コレクション変更列挙」](/uwp/api/windows.foundation.collections.collectionchange)も参照してください。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

Windows ランタイム アプリ c# または Visual\<Basic プロジェクト IMap\<K,V> IDictionary K,V>。

## <a name="unorderedmapremove-method"></a><a name="remove"></a>順序のないマップ::メソッドの削除

指定したキー/値ペアを UnorderedMap オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー*の種類は型名*K*です。

## <a name="unorderedmapsize-method"></a><a name="size"></a>順序指定されていないマップ::サイズメソッド

順序指定されていないマップの[要素を>する\<](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

順序なしのマップの要素数。

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a>順序なしマップ::順序なしマップのコンストラクタ

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

*Init*<br/>
現在の UnorderedMap の型名。

*P*<br/>
2 つのキーを比較してそれらが等しいかどうかを判定できる関数オブジェクト。 このパラメータのデフォルトは[\<std::equal_to K>](../standard-library/equal-to-struct.md)です。

*H*<br/>
キーのハッシュ値を生成する関数オブジェクト。 このパラメーターは、クラスがサポートするキーの種類に対して[、クラス 1](../standard-library/hash-class.md)をハッシュします。

*M*<br/>
現在の UnorderedMap を初期化するために使用される[std::unordered_map](../standard-library/unordered-map-class.md)への参照または[Lvalues および Rvalues。](../cpp/lvalues-and-rvalues-visual-cpp.md)

*イリノイ*<br/>
マップの初期化に使用される[std::pair](../standard-library/pair-structure.md)オブジェクトの[std::initializer_list。](../standard-library/initializer-list-class.md)

*first*<br/>
現在の UnorderedMap を初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在の UnorderedMap を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)<br/>
[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)<br/>
[Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[コレクション](../cppcx/collections-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
