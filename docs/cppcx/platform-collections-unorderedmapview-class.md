---
title: Platform::Collections::UnorderedMapView クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: f0096982ad5d11b9ea394c9f02ba748a52e4216b
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031486"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView クラス

キーと値のペアのコレクションである、 *マップ*への読み取り専用ビューを表します。

## <a name="syntax"></a>構文

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キー/値ペア内のキーの型。

*V*<br/>
キー/値ペア内の値の型。

*C*<br/>
2 つのキー値を比較して等価性を確認できる関数オブジェクトを提供する型。 デフォルトでは[、std::equal_to\<K>](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>解説

順序付けられていないマップ ビューは[、Windows::Foundation::コレクション::IMapView\<K,V>](/uwp/api/windows.foundation.collections.imapview-2)の具体的な実装であり、アプリケーション バイナリ インターフェイス (ABI) を介して渡されます。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[順序付けられていないマップビュー::順序指定されていないマップビュー](#ctor)|UnorderedMapView クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[順序付けされていないマップビュー::最初](#first)|マップ ビュー内の最初の要素に初期化される反復子を返します。|
|[順序付けされていないマップビュー::ハスキー](#haskey)|指定したキーが現在の UnorderedMapView に格納されているかどうかを判定します。|
|[順序付けされていないマップビュー::ルックアップ](#lookup)|現在の UnorderedMapView オブジェクト内の指定されたキーの位置の要素を取得します。|
|[順序指定されていないマップビュー::サイズ](#size)|現在の UnorderedMapView オブジェクトの要素数を返します。|
|[順序付けされていないマップビュー::分割](#split)|元の UnorderedMapView オブジェクトを 2 つの UnorderedMapView オブジェクトに分割します。|

## <a name="inheritance-hierarchy"></a>継承階層

`UnorderedMapView`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a>順序付けされていないマップビュー::最初のメソッド

順序付けられていないマップ内の最初の[Windows::Foundation::コレクション::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>戻り値

マップ ビュー内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myMapView->First();` 」のように入力します。

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a>順序付けられていないマップビュー::ハスキーメソッド

指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。

### <a name="syntax"></a>構文

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
要素の検索に使用するキー。 の型`key`は型名*K*です。

### <a name="return-value"></a>戻り値

キーが見つかった場合は**true。** それ以外の場合**は false。**

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a>順序指定されていないマップビュー::ルックアップ メソッド

型 K の指定されたキーに関連付けられている型 V の値を取得します。

### <a name="syntax"></a>構文

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
UnorderedMapView の要素の検索に使用するキー。 の型`key`は型名*K*です。

### <a name="return-value"></a>戻り値

`key` とペアになる値。 戻り値の型は型名*V*です。

## <a name="unorderedmapviewsize-method"></a><a name="size"></a>順序指定されていないマップビュー::サイズのメソッド

順序指定されていないマップビューの[要素を>する要素\<](/uwp/api/windows.foundation.collections.ikeyvaluepair-2)を返します。

### <a name="syntax"></a>構文

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

Unordered MapView の要素数。

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a>順序指定されていないマップビュー::分割メソッド

現在の UnorderedMapView オブジェクトを 2 つの UnorderedMapView オブジェクトに分割します。 このメソッドは操作不可です。

### <a name="syntax"></a>構文

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>パラメーター

*最初のパーティション*<br/>
元の UnorderedMapView オブジェクトの最初の部分。

*2番目のパーティション*<br/>
元の UnorderedMapView オブジェクトの 2 つ目の部分。

### <a name="remarks"></a>解説

このメソッドは操作可能ではありません。これは何も実行しません。

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a>順序付けされていないマップビュー::順序なしマップビューのコンス トラクター

UnorderedMapView クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>パラメーター

*n*<br/>
領域を事前に割り当てる要素の数。

*Init*<br/>
UnorderedMapView の型名。

*H*<br/>
キーのハッシュ値にできる関数オブジェクト。 デフォルトは、サポートする型に対して[>\<std::hash K](../standard-library/hash-class.md)です。 `std::hash`

*P*<br/>
2 つのキーを比較して等価性を確認できる関数オブジェクトを提供する型。 デフォルトは[std::equal_to\<K>](../standard-library/equal-to-struct.md)です。

*M*<br/>
unorderedMapView を初期化するために使用される[std::unordered_map](../standard-library/unordered-map-class.md)への参照または[Lvalues と Rvalues。](../cpp/lvalues-and-rvalues-visual-cpp.md)

*first*<br/>
UnorderedMapView を初期化するために使用される要素の範囲内の最初の要素の入力反復子。

*last*<br/>
UnorderedMapView を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。

## <a name="see-also"></a>関連項目

[Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/windows.foundation.collections.imapview-2)
