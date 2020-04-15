---
title: Platform::Collections::VectorView クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
ms.openlocfilehash: cecbd61ad8862d5046cab9e0b418d5c4d16829d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363803"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView クラス

インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションの読み取り専用ビューを表します。 コレクション内の各オブジェクトの型は、テンプレート パラメーターによって指定されます。

## <a name="syntax"></a>構文

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
`VectorView` オブジェクトに格納されている要素の型。

*E*<br/>
`T`型の値との等値性をテストするための二項述語を指定します。 既定値は `std::equal_to<T>` です。

### <a name="remarks"></a>解説

クラス`VectorView`は[、Windows::Foundation::コレクション::IVectorView\<T>](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)インターフェイス、および標準テンプレート ライブラリ反復子のサポートを実装します。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ベクトルビュー::ベクトルビュー](#ctor)|VectorView クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ベクトルビュー::最初](#first)|VectorView 内の最初の要素を指定する反復子を返します。|
|[ベクトルビュー::ゲットアット](#getat)|指定されたインデックスで示される現在の VectorView の要素を取得します。|
|[ベクトルビュー::ゲットマニ](#getmany)|指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。|
|[ベクトルビュー::インデックスOf](#indexof)|現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|
|[VectorView::Size](#size)|現在の VectorView オブジェクトの要素数を返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VectorView`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a>ベクトルビュー::最初のメソッド

VectorView 内の最初の要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>戻り値

VectorView 内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First() によって返される反復器を保持する便利な方法は **、auto**型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、「 `auto x = myVectorView->First();` 」のように入力します。

## <a name="vectorviewgetat-method"></a><a name="getat"></a>ベクトルビュー::GetAtメソッド

指定されたインデックスで示される現在の VectorView の要素を取得します。

### <a name="syntax"></a>構文

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
VectorView オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

### <a name="return-value"></a>戻り値

`index` パラメーターで指定された要素。 要素の型は、VectorView テンプレート パラメーター T で指定*します。*

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a>ベクトルビュー::多くのメソッドを取得します。

指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。

### <a name="syntax"></a>構文

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>パラメーター

*startIndex*<br/>
取得する項目の 0 から始まるインデックス。

*dest*<br/>
この操作が完了するときに、`startIndex` で指定された要素を開始位置とし、VectorView 内の最後の要素を終了位置とする、項目の配列。

### <a name="return-value"></a>戻り値

取得した項目数。

## <a name="vectorviewindexof-method"></a><a name="indexof"></a>ベクトルビュー::メソッドのインデックス

現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。

### <a name="syntax"></a>構文

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
検索する項目。

*index*<br/>
`value` パラメーターが見つかった場合は、項目の 0 から始まるインデックス。それ以外の場合は 0。

項目が 最初の要素であるか、`VectorView`項目が見つからなかった場合 *、index*パラメーターは 0 です。 戻り値が**true**の場合、項目が見つかり、最初の要素になります。それ以外の場合、アイテムは見つかりませんでした。

### <a name="return-value"></a>戻り値

指定した項目が見つかった場合は true、指定したアイテムが見つかった場合は**true。** それ以外の場合**は false。**

## <a name="vectorviewsize-method"></a><a name="size"></a>ベクトルビュー::サイズメソッド

現在の VectorView オブジェクトの要素数を返します。

### <a name="syntax"></a>構文

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

現在の VectorView 内の要素数。

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a>ベクトルビュー::ベクトルビューコンストラクタ

VectorView クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```
VectorView();
explicit VectorView(
   UInt32 size
);
VectorView(
   UInt32 size,
   T value
);
explicit VectorView(
   const ::std::vector<T>& v
);
explicit VectorView(
   ::std::vector<T>&& v
);
VectorView(
   const T * ptr,
   UInt32 size
);

template <
   size_t N
>
explicit VectorView(
   const T (&arr)[N]
);

template <
   size_t N
>
explicit VectorView(
   const ::std::array<T,
   N>& a
);

explicit VectorView(
   const ::Platform::Array<T>^ arr
);

template <
   typename InIt
>
VectorView(
   InItfirst,
   InItlast
);

VectorView(
   std::initializer_list<T> il
);
```

### <a name="parameters"></a>パラメーター

*Init*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのコレクションの型。

*イリノイ*<br/>
vectorView の初期化に使用される要素を持つ[std::initializer_list。](../standard-library/initializer-list-class.md)

*N*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのコレクションの要素数。

*サイズ*<br/>
VectorView の要素数。

*value*<br/>
現在の VectorView の各要素を初期化するために使用される値。

*V*<br/>
現在[のベクトル](../cpp/lvalues-and-rvalues-visual-cpp.md)ビューを初期化するために使用される[std::vector](../standard-library/vector-class.md)への値と値。

*Ptr*<br/>
現在の VectorView を初期化するために使用される `std::vector` へのポインター。

*Arr*<br/>
現在のベクター ビューを初期化するために使用される[プラットフォーム::配列](../cppcx/platform-array-class.md)オブジェクト。

*A*<br/>
現在のベクタービューを初期化するために使用される[std::配列](../standard-library/array-class-stl.md)オブジェクト。

*first*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最初の要素。 のタイプ`first`は*完全な転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

*last*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最後の要素。 のタイプ`last`は*完全な転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
