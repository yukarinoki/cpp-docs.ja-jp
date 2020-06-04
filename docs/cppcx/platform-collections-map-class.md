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
ms.openlocfilehash: ff27f6c543a2326dd4318f66aae51b89092b28e2
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032448"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map クラス

キー/値ペアのコレクションである *マップ*を表します。 XAML[データ バインディング](/windows/uwp/data-binding/data-binding-in-depth)を支援する[Windows::ファウンデーション:コレクション::IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2)を実装します。

## <a name="syntax"></a>構文

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>パラメーター

*K*<br/>
キー/値ペア内のキーの型。

*V*<br/>
キー/値ペア内の値の型。

*C*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 デフォルトでは[、std::less\<K>。 ](../standard-library/less-struct.md)

*__is_valid_winrt_type()**K*と*V*の型を検証し、型を Map に格納できない場合にわかりやすいエラー メッセージを提供するコンパイラによって生成された関数。

### <a name="remarks"></a>解説

使用できる型は次のとおりです。

- 整数

- インターフェイス クラス^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

マップは、基本的に [std::map](../standard-library/map-class.md)のラッパーです。 これは、Windows の C++ 具体的な実装です[::コレクション::IMap<::コレクション::IKeyValuePair\<K,V>>](/uwp/api/windows.foundation.collections.imap-2)および[IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2)型は、パブリック Windows ランタイム インターフェイスを介して渡されます。 パブリックの戻り値またはパラメーターで `Platform::Collections::Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 パラメーターまたは戻り値の型を[Windows::Foundation::コレクション::IMap\<K,V>](/uwp/api/windows.foundation.collections.imap-2)に変更することで、エラーを修正できます。

詳細については、[コレクション](../cppcx/collections-c-cx.md) を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[地図::地図](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[地図::クリア](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[地図::最初](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[マップ::ゲットビュー](#getview)|現在のマップの読み取り専用ビュー ( [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)) を返します。|
|[マップ::ハスキー](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[マップ::挿入](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[地図:ルックアップ](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[Map::Remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[地図::サイズ](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|[マップ:マップ変更イベント](#mapchanged)|マップが変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Map`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="mapclear-method"></a><a name="clear"></a>マップ::メソッドのクリア

現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a>地図::最初の方法

マップ内の最初の要素を指定する反復子、またはマップが空の場合は `nullptr` を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myMap->First();` 」のように入力します。

## <a name="mapgetview-method"></a><a name="getview"></a>マップ::GetView メソッド

現在のマップの読み取り専用ビューを返します。つまり[、>\<](/uwp/api/windows.foundation.collections.imapview-2) [プラットフォーム::コレクション::マップビュークラス](../cppcx/platform-collections-mapview-class.md)を実装しています。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`MapView` オブジェクト。

## <a name="maphaskey-method"></a><a name="haskey"></a>マップ::ハズキーメソッド

指定したキーが現在のマップに格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
Map 要素の検索に使用するキー。 *キー*の種類は型名*K*です。

### <a name="return-value"></a>戻り値

キーが見つかった場合は**true。** それ以外の場合**は false。**

## <a name="mapinsert-method"></a><a name="insert"></a>マップ::メソッドの挿入

指定したキー/値ペアを現在のマップ オブジェクトに追加します。

### <a name="syntax"></a>構文

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー*の種類は型名*K*です。

*value*<br/>
キー/値ペアの値部分。 *値*の型は型名*V*です。

### <a name="return-value"></a>戻り値

現在の Map 内の既存の要素のキーが*キー*に一致し、その要素の値部分が*value*に設定されている場合は**true。** 現在のマップ内の既存の要素が*キー*と一致しない場合、*キー*と*値*のパラメータがキーと値のペアに設定され、現在のマップに追加される場合は**false。**

## <a name="maplookup-method"></a><a name="lookup"></a>マップ::ルックアップメソッド

キーがある場合は、型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
マップの要素の検索に使用するキー。 *キー*の種類は型名*K*です。

### <a name="return-value"></a>戻り値

*キー*と対になっている値。 戻り値の型は型名*V*です。

### <a name="remarks"></a>解説

キーが存在しない場合は、[プラットフォーム::アウトオブバウンド例外](../cppcx/platform-outofboundsexception-class.md)がスローされます。

## <a name="mapmap-constructor"></a><a name="ctor"></a>マップ::マップコンストラクタ

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

*Init*<br/>
現在のマップの型名。

*作曲*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。

*M*<br/>
現在のマップを初期化するために使用`map Class`される を参照または[右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)。

*first*<br/>
現在のマップを初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在のマップを初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a>マップ:マップ変更イベント

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

イベントを発生させたオブジェクトと発生した変更の種類に関する情報を含む>。 [\<](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) [「iMapChangedEventArgs\<K>」](/uwp/api/windows.foundation.collections.imapchangedeventargs-1)および「[コレクション変更列挙」](/uwp/api/windows.foundation.collections.collectionchange)も参照してください。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

C# または Visual Basic プロジェクト IMap\<K,V>を\<使用する Windows ランタイム アプリは、iDictionary K,V>として使用されます。

## <a name="mapremove-method"></a><a name="remove"></a>マップ::メソッドの削除

指定したキー/値ペアを現在のマップ オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 *キー*の種類は型名*K*です。

## <a name="mapsize-method"></a><a name="size"></a>マップ::サイズの方法

マップ内の[要素を>する要素を\<返](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

マップの要素数。

## <a name="see-also"></a>関連項目

[コレクション (C++/CX)](collections-c-cx.md)<br/>
[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
