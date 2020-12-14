---
description: '詳細情報: Platform:: Collections:: VectorView クラス'
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
ms.openlocfilehash: f0d1244ed5331fa9732bdfef1f1b7e2133f99442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250037"
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

### <a name="remarks"></a>Remarks

クラスは、 `VectorView` [Windows:: Foundation:: Collections:: IVectorView \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1)インターフェイスを実装し、標準テンプレートライブラリ反復子をサポートします。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[VectorView:: VectorView](#ctor)|VectorView クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[VectorView:: First](#first)|VectorView 内の最初の要素を指定する反復子を返します。|
|[VectorView:: GetAt](#getat)|指定されたインデックスで示される現在の VectorView の要素を取得します。|
|[VectorView:: GetMany](#getmany)|指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。|
|[VectorView:: IndexOf](#indexof)|現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|
|[VectorView::Size](#size)|現在の VectorView オブジェクトの要素数を返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VectorView`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a> VectorView:: First メソッド

VectorView 内の最初の要素を指定する反復子を返します。

### <a name="syntax"></a>構文

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>戻り値

VectorView 内の最初の要素を指定する反復子。

### <a name="remarks"></a>解説

First () によって返される反復子を保持する便利な方法は、型推論キーワードで宣言された変数に戻り値を代入することです **`auto`** 。 たとえば、「 `auto x = myVectorView->First();` 」のように入力します。

## <a name="vectorviewgetat-method"></a><a name="getat"></a> VectorView:: GetAt メソッド

指定されたインデックスで示される現在の VectorView の要素を取得します。

### <a name="syntax"></a>構文

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
VectorView オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。

### <a name="return-value"></a>戻り値

`index` パラメーターで指定された要素。 要素の型は、VectorView テンプレートパラメーター *T* によって指定されます。

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a> VectorView:: GetMany メソッド

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

*先*<br/>
この操作が完了するときに、`startIndex` で指定された要素を開始位置とし、VectorView 内の最後の要素を終了位置とする、項目の配列。

### <a name="return-value"></a>戻り値

取得した項目数。

## <a name="vectorviewindexof-method"></a><a name="indexof"></a> VectorView:: IndexOf メソッド

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

*インデックス*<br/>
`value` パラメーターが見つかった場合は、項目の 0 から始まるインデックス。それ以外の場合は 0。

*インデックス* パラメーターは、項目がの最初の要素であるか、項目が見つからなかった場合は0になり `VectorView` ます。 戻り値がの場合、項目が見つかり、それが最初の要素になります。 **`true`** それ以外の場合、項目は見つかりませんでした。

### <a name="return-value"></a>戻り値

**`true`** 指定した項目が見つかった場合は。それ以外の場合は **`false`** 。

## <a name="vectorviewsize-method"></a><a name="size"></a> VectorView:: Size メソッド

現在の VectorView オブジェクトの要素数を返します。

### <a name="syntax"></a>構文

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>戻り値

現在の VectorView 内の要素数。

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a> VectorView:: VectorView コンストラクター

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

*初期化*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのコレクションの型。

*自動車*<br/>
VectorView の初期化に使用される要素を持つ [std:: initializer_list](../standard-library/initializer-list-class.md) 。

*N*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのコレクションの要素数。

*size*<br/>
VectorView の要素数。

*value*<br/>
現在の VectorView の各要素を初期化するために使用される値。

*v*<br/>
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)は、現在の VectorView を初期化するために使用される[std:: vector](../standard-library/vector-class.md)になります。

*ptr*<br/>
現在の VectorView を初期化するために使用される `std::vector` へのポインター。

*→*<br/>
現在の VectorView を初期化するために使用される [Platform:: Array](../cppcx/platform-array-class.md) オブジェクト。

*ある*<br/>
現在の VectorView を初期化するために使用される [std:: array](../standard-library/array-class-stl.md) オブジェクト。

*first*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最初の要素。 の型は、 `first` *完全転送* によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

*last*<br/>
現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最後の要素。 の型は、 `last` *完全転送* によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
