---
title: Platform::Collections::Map クラス
ms.date: 03/27/2019
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
ms.openlocfilehash: ce50290217c7c06e26f26fc50564d3e37c873157
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565283"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map クラス

キー/値ペアのコレクションである *マップ*を表します。

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
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、 [std::less\<K >](../standard-library/less-struct.md)します。

*__is_valid_winrt_type()* コンパイラによって生成された関数の種類を検証する*K*と*V*し型にマップに格納できない場合は、わかりやすいエラー メッセージを提供します。

### <a name="remarks"></a>Remarks

使用できる型は次のとおりです。

- 整数

- インターフェイス クラス ^

- パブリック ref クラス ^

- value struct

- パブリック列挙型クラス

マップは、基本的に [std::map](../standard-library/map-class.md)のラッパーです。 C++ の具象実装では、 [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)と[IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_)Windows ランタイム インターフェイスのパブリックの間で渡される型。 パブリックの戻り値またはパラメーターで `Platform::Collections::Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 パラメーターまたは戻り値の型を変更することで、エラーを修正する[Windows::Foundation::Collections::IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)します。

詳細については、[コレクション](../cppcx/collections-c-cx.md)を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Map::Map](#ctor)|マップ クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Map::Clear](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|
|[Map::First](#first)|マップ内の最初の要素を指定する反復子を返します。|
|[Map::GetView](#getview)|現在のマップの読み取り専用ビュー ( [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)) を返します。|
|[Map::HasKey](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|
|[Map::Insert](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|
|[Map::Lookup](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|
|[Map::Remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|
|[Map::size](#size)|現在のマップ オブジェクト内の要素数を返します。|

### <a name="events"></a>イベント

|||
|-|-|
|名前|説明|
|[Map::mapchanged](#mapchanged)イベント|マップが変更されたときに発生します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Map`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="clear"></a>  Map::clear メソッド

現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Clear();
```

## <a name="first"></a>  Map::first メソッド

マップ内の最初の要素を指定する反復子、またはマップが空の場合は `nullptr` を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>戻り値

マップ内の最初の要素を指定する反復子。

### <a name="remarks"></a>Remarks

First() によって返される反復子を保持する便利な方法で宣言された変数に戻り値を割り当てるには、**自動**推論キーワードを入力します。 たとえば、`auto x = myMap->First();` のようにします。

## <a name="getview"></a>  Map::getview メソッド

現在のマップの読み取り専用ビューを返しますつまり、 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)、実装する、[Windows::Foundation::Collections::IMapView\<K, V >]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) インターフェイス。

### <a name="syntax"></a>構文

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>戻り値

`MapView` オブジェクト。

## <a name="haskey"></a>  Map::haskey メソッド

指定したキーが現在のマップに格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
Map 要素の検索に使用するキー。 型*キー* typename が*K*します。

### <a name="return-value"></a>戻り値

**true**キーが見つかった。 それ以外の場合**false**します。

## <a name="insert"></a>  Map::insert メソッド

指定したキー/値ペアを現在のマップ オブジェクトに追加します。

### <a name="syntax"></a>構文

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 型*キー* typename が*K*します。

*value*<br/>
キー/値ペアの値部分。 型*値*typename が*V*します。

### <a name="return-value"></a>戻り値

**true**現在のマップ内の既存の要素のキーと一致するかどうか*キー*し、その要素の値の部分に設定されている*値*します。 **false**現在のマップ内の既存の要素が一致しない場合*キー*と*キー*と*値*パラメーターはキー/値ペアに加えに追加し、現在のマップ。

## <a name="lookup"></a>  Map::lookup メソッド

キーがある場合は、型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
マップの要素の検索に使用するキー。 型*キー* typename が*K*します。

### <a name="return-value"></a>戻り値

値とペアになっている、*キー*します。 戻り値の型は typename *V*します。

### <a name="remarks"></a>Remarks

キーが存在しない場合、 [platform::outofboundsexception](../cppcx/platform-outofboundsexception-class.md)がスローされます。

## <a name="ctor"></a>  Map::map コンス トラクター

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

*InIt*<br/>
現在のマップの型名。

*comp*<br/>
並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。

*m*<br/>
参照または[rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)を`map Class`現在のマップを初期化するために使用されます。

*first*<br/>
現在のマップを初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在のマップを初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="mapchanged"></a>  Map::MapChanged Event

項目がマップに挿入されたときまたはマップから削除されたときに発生します。

### <a name="syntax"></a>構文

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler)発生した変更の種類と、イベントを発生させたオブジェクトに関する情報を格納します。 参照してください[IMapChangedEventArgs\<K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_)と[CollectionChange 列挙](/uwp/api/windows.foundation.collections.collectionchange)します。

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

C# または Visual Basic を使用する Windows ランタイム アプリ プロジェクト IMap\<K, V > として IDictionary\<K, V >。

## <a name="remove"></a>  Map::remove メソッド

指定したキー/値ペアを現在のマップ オブジェクトから削除します。

### <a name="syntax"></a>構文

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー/値ペアのキー部分。 型*キー* typename が*K*します。

## <a name="size"></a>  Map::size メソッド

数を返します[Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_)マップ内の要素。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

マップの要素数。

## <a name="see-also"></a>関連項目

[プラットフォーム Namespace](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
