---
title: Platform::Collections::MapView クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: 24995f553c5fcb8626c0d51758577b948c9c67ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354437"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView クラス

キーと値のペアのコレクションである、 *マップ*への読み取り専用ビューを表します。

## <a name="syntax"></a>構文

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キー/値ペア内のキーの型。

*V*<br/>
キー/値ペア内の値の型。

*C*<br/>
並べ替えキーとして 2 つの要素値を比較して MapView 内の相対順序を決定できる関数オブジェクトを提供する型。 デフォルトでは[、std::less\<K>。 ](../standard-library/less-struct.md)

### <a name="remarks"></a>解説

MapView は、アプリケーション バイナリ インターフェイス (ABI) を介して渡される[Windows::Foundation::コレクション::IMapView \<K,V>](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)インターフェイスの具体的な C++ 実装です。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[マップビュー::マップビュー](#ctor)|MapView クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[マップビュー::最初](#first)|マップ ビュー内の最初の要素に初期化される反復子を返します。|
|[マップビュー::ハスキー](#haskey)|現在の MapView に、指定されたキーが含まれているかどうかを判定します。|
|[マップビュー::ルックアップ](#lookup)|現在の MapView オブジェクト内の、指定されたキーの位置の要素を取得します。|
|[MapView::Size](#size)|現在の MapView オブジェクトの要素数を返します。|
|[マップビュー::スプリット](#split)|元の MapView オブジェクトを、2 つの MapView オブジェクトに分割します。|

## <a name="inheritance-hierarchy"></a>継承階層

`MapView`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="mapviewfirst-method"></a><a name="first"></a>マップビュー::最初のメソッド

マップ ビュー内の最初の要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>戻り値

マップ ビュー内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myMapView->First();` 」のように入力します。

## <a name="mapviewhaskey-method"></a><a name="haskey"></a>マップビュー::ハスキーメソッド

現在の MapView に、指定されたキーが含まれているかどうかを判定します。

### <a name="syntax"></a>構文

```

bool HasKey(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
MapView 要素の検索に使用するキー。 *キー*の種類は型名*K*です。

### <a name="return-value"></a>戻り値

キーが見つかった場合は**true。** それ以外の場合**は false。**

## <a name="mapviewlookup-method"></a><a name="lookup"></a>マップビュー::ルックアップメソッド

型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```
V Lookup(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
MapView の要素の検索に使用するキー。 の型`key`は型名*K*です。

### <a name="return-value"></a>戻り値

`key` とペアになる値。 戻り値の型は型名*V*です。

## <a name="mapviewmapview-constructor"></a><a name="ctor"></a>マップビュー::マップビューコンストラクタ

MapView クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>パラメーター

*Init*<br/>
現在の MapView の型名。

*作曲*<br/>
並べ替えキーとして 2 つの要素値を比較して MapView 内の相対順序を決定できる関数オブジェクト。

*M*<br/>
現在の MapView を初期化するために使用`map Class`されるを参照または[Lvalues および Rvalues。](../cpp/lvalues-and-rvalues-visual-cpp.md)

*first*<br/>
現在の MapView を初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
現在の MapView を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

*イリノイ*<br/>
要素が MapView に挿入される[std::initializer_list<std::pair\<K,V>>。](../standard-library/initializer-list-class.md)

## <a name="mapviewsize-method"></a><a name="size"></a>マップビュー::サイズメソッド

現在の MapView オブジェクトの要素数を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

現在の MapView 内の要素数。

## <a name="mapviewsplit-method"></a><a name="split"></a>マップビュー::分割メソッド

現在の MapView を 2 つの MapView オブジェクトに分割します。 このメソッドは操作不可です。

### <a name="syntax"></a>構文

```
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>パラメーター

*最初のパーティション*<br/>
元の MapView オブジェクトの最初の部分。

*2番目のパーティション*<br/>
元の MapView オブジェクトの 2 番目の部分。

### <a name="remarks"></a>解説

このメソッドは操作可能ではありません。これは何も実行しません。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)
