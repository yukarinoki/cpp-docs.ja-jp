---
title: Platform::Collections::Map クラス
ms.date: 10/01/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: 0ddb15507c97c0dfff48575e476b57fe91359239
ms.sourcegitcommit: 65fead53d56d531d71be42216056aca5f44def11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88610908"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map クラス

キー/値ペアのコレクションである *マップ*を表します。 XAML[データバインディング](/windows/uwp/data-binding/data-binding-in-depth)を支援するために、 [Windows:: Foundation:: Collections:: IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2)を実装します。

## <a name="syntax"></a>構文

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>パラメーター

*Kb*<br/>
キー/値ペア内のキーの型。

*画像*<br/>
キー/値ペア内の値の型。

*C*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、 [std:: \<K> less](../standard-library/less-struct.md)です。

*__is_valid_winrt_type ()**K*および*V*の型を検証し、型がマップに格納できない場合はわかりやすいエラーメッセージを提供する、コンパイラによって生成される関数。

### <a name="remarks"></a>注釈

使用できる型は次のとおりです。

- integers

- インターフェイスクラス ^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

マップは、基本的に [std::map](../standard-library/map-class.md)のラッパーです。 これは、パブリック Windows ランタイムインターフェイスで渡される[Windows:: Foundation:: Collections: \<Windows::Foundation::Collections::IKeyValuePair\<K,V> > : IMap](/uwp/api/windows.foundation.collections.imap-2)型と[IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2)型の C++ の具象実装です。 パブリックの戻り値またはパラメーターで `Platform::Collections::Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーを修正するには、パラメーターまたは戻り値の型を[Windows:: Foundation:: Collections:: IMap \<K,V> ](/uwp/api/windows.foundation.collections.imap-2)に変更します。

詳細については、[コレクション](../cppcx/collections-c-cx.md) を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Map:: Map](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Map:: Clear](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[Map:: First](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[Map:: GetView](#getview)|現在のマップの読み取り専用ビュー ( [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)) を返します。|
|[Map:: HasKey](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[Map:: Insert](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[Map:: Lookup](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[Map::Remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[Map:: Size](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>events

|||
|-|-|
|名前|説明|
|[Map:: MapChanged](#mapchanged) イベント|マップが変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Map`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="mapclear-method"></a><a name="clear"></a> Map:: Clear メソッド

現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a> Map:: First メソッド

Map 内の最初の要素を指定する反復子を返し **`nullptr`** ます。マップが空の場合はを返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>注釈

First () によって返される反復子を保持する便利な方法は、型推論キーワードで宣言された変数に戻り値を代入することです **`auto`** 。 たとえば、「 `auto x = myMap->First();` 」のように入力します。

## <a name="mapgetview-method"></a><a name="getview"></a> Map:: GetView メソッド

現在のマップの読み取り専用ビューを返します。これは、 [Windows:: Foundation:: collections:: IMapView \<K,V> ](/uwp/api/windows.foundation.collections.imapview-2)インターフェイスを実装する[Platform:: Collections:: mapview クラス](../cppcx/platform-collections-mapview-class.md)です。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`MapView` オブジェクト。

## <a name="maphaskey-method"></a><a name="haskey"></a> Map:: HasKey メソッド

指定したキーが現在のマップに格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
Map 要素の検索に使用するキー。 *キー*の型は typename *K*です。

### <a name="return-value"></a>戻り値

**`true`** キーが見つかった場合は。それ以外の場合は **`false`** 。

## <a name="mapinsert-method"></a><a name="insert"></a> Map:: Insert メソッド

指定したキー/値ペアを現在のマップ オブジェクトに追加します。

### <a name="syntax"></a>構文

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー*の型は typename *K*です。

*value*<br/>
キー/値ペアの値部分。 *値*の型は typename *V*です。

### <a name="return-value"></a>戻り値

**`true`** 現在のマップ内の既存の要素のキーが *キー* と一致し、その要素の値部分が *value*に設定されている場合は。 **`false`** 現在のマップ内の既存の要素が*キー*と一致せず、キーと*値*のパラメーターがキーと値のペアに*なり、現在*のマップに追加されている場合は。

## <a name="maplookup-method"></a><a name="lookup"></a> Map:: Lookup メソッド

キーがある場合は、型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
マップの要素の検索に使用するキー。 *キー*の型は typename *K*です。

### <a name="return-value"></a>戻り値

*キー*とペアになる値。 戻り値の型は typename *V*です。

### <a name="remarks"></a>注釈

キーが存在しない場合は、 [Platform:: OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) がスローされます。

## <a name="mapmap-constructor"></a><a name="ctor"></a> Map:: Map コンストラクター

マップ クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>パラメーター

*初期化*<br/>
現在のマップの型名。

*comp*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。

*m*<br/>
現在のマップ[rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)を `map Class` 初期化するために使用されるへの参照または右辺値。

*first*<br/>
現在のマップを初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在のマップを初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a> Map:: MapChanged イベント

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

イベントを発生させたオブジェクトと発生した変更の種類に関する情報を含む[Mapchangedeventhandler \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) 。 「 [」 \<K> ](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) And [collectionchange 列挙型](/uwp/api/windows.foundation.collections.collectionchange)」も参照してください。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

C# または Visual Basic project IMap を IDictionary として使用するアプリを Windows ランタイム \<K,V> \<K,V> します。

## <a name="mapremove-method"></a><a name="remove"></a> Map:: Remove メソッド

指定したキー/値ペアを現在のマップ オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー*の型は typename *K*です。

## <a name="mapsize-method"></a><a name="size"></a> Map:: Size メソッド

Map 内の[Windows:: Foundation:: Collections:: ikeyvaluepair<k, \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素の数を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

マップの要素数。

## <a name="see-also"></a>関連項目

[コレクション (C++/CX)](collections-c-cx.md)<br/>
[Platform 名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
