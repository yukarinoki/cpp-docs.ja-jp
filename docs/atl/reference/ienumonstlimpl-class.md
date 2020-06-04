---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 2fbe6ccfbea2836c42a054da7ea9ebeac4e1555d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329705"
---
# <a name="ienumonstlimpl-class"></a>クラス

このクラスは、C++ 標準ライブラリ コレクションに基づいて列挙子インターフェイスを定義します。

## <a name="syntax"></a>構文

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
COM 列挙子。 例については[、IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring)を参照してください。

*ピッド*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の型。

*コピー*<br/>
[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)。

*コルタイプ*<br/>
C++ 標準ライブラリ コンテナー クラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イエヌオンストルプル::クローン](#clone)|**クローン**の実装。|
|[イエヌオンストルプル::イニト](#init)|列挙子を初期化します。|
|[イエヌオンストルプル::次へ](#next)|**Next**の実装。|
|[イエヌオンストルプル::リセット](#reset)|**リセット**の実装。|
|[イエヌオンストルプル::スキップ](#skip)|**スキップ**の実装。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[イエヌオンストルプル::m_iter](#m_iter)|コレクション内での列挙子の現在の位置を表す反復子。|
|[イエヌオンストルプル::m_pcollection](#m_pcollection)|列挙する項目を保持する C++ 標準ライブラリ コンテナーへのポインター。|
|[イエヌオンストルプル::m_spUnk](#m_spunk)|コレクション`IUnknown`を提供するオブジェクトのポインター。|

## <a name="remarks"></a>解説

`IEnumOnSTLImpl`は、列挙される項目が C++ 標準ライブラリ互換コンテナーに格納される COM 列挙子インターフェイスの実装を提供します。 このクラスは、配列に基づく列挙子インターフェイスの実装を提供する[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)クラスに似ています。

> [!NOTE]
> と の`CComEnumImpl``IEnumOnSTLImpl`違いの詳細については[、CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init)を参照してください。

通常、このインターフェイスの実装から派生して独自の列挙子クラスを作成する必要*はありません*。 C++ 標準ライブラリ コンテナーに基づいて ATL 提供の列挙子を使用する場合は[、CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)のインスタンスを作成するか[、ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)から派生して列挙子を返すコレクション クラスを作成する方が一般的です。

ただし、カスタム列挙子 (たとえば、列挙子インターフェイスに加えてインターフェイスを公開する列挙子) を指定する必要がある場合は、このクラスから派生できます。 このような状況では、独自の実装を提供するために[Clone](#clone)メソッドをオーバーライドする必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ienumonstlimplinit"></a><a name="init"></a>イエヌオンストルプル::イニト

列挙子を初期化します。

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>パラメーター

*リリースを確認する*<br/>
[in]列挙`IUnknown`子の有効期間中に保持する必要があるオブジェクトのポインター。 そのようなオブジェクトが存在しない場合は NULL を渡します。

*コレクション*<br/>
列挙する項目を保持する C++ 標準ライブラリ コンテナーへの参照。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

別のオブジェクト`Init`に保持されているコレクションへの参照を渡す場合は *、pUnkForRelease*パラメーターを使用して、列挙子が必要な限り、オブジェクトとオブジェクトが保持するコレクションを使用できるようにします。

列挙子インターフェイスへのポインターをクライアントに返す前に、このメソッドを呼び出す必要があります。

## <a name="ienumonstlimplclone"></a><a name="clone"></a>イエヌオンストルプル::クローン

このメソッドは、型`CComEnumOnSTL`のオブジェクトを作成し、現在のオブジェクトで使用されるのと同じコレクションと反復器で初期化し、新しく作成されたオブジェクトのインターフェイスを返すことによって **、Clone**メソッドの実装を提供します。

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>パラメーター

*ppEnum*<br/>
[アウト]現在の列挙子から複製された新しく作成されたオブジェクトの列挙子インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a>イエヌオンストルプル::m_spUnk

コレクション`IUnknown`を提供するオブジェクトのポインター。

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>解説

このスマート ポインターは、列挙子の有効期間中も保持することを保証する[IEnumOnSTLImpl::Init](#init)に渡されるオブジェクトの参照を保持します。

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a>イエヌオンストルプル::m_pcollection

このメンバーは、列挙子インターフェイスの実装を促進するデータを提供するコレクションを指します。

```
CollType* m_pcollection;
```

### <a name="remarks"></a>解説

このメンバーは、呼び出しによって初期化[されます](#init)。

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a>イエヌオンストルプル::m_iter

このメンバーは、コレクション内の現在位置をマークし、後続の要素に移動するために使用される反復子を保持します。

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a>イエヌオンストルプル::次へ

このメソッドは **、Next**メソッドの実装を提供します。

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]要求された要素の数。

*ルゲルト*<br/>
[アウト]要素を格納する配列。

*pceltFetched*<br/>
[アウト]実際に*rgelt*で返される要素の数。 リストに残っている*celt*要素よりも少ない場合、これは*celt*より小さくなる可能性があります。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ienumonstlimplreset"></a><a name="reset"></a>イエヌオンストルプル::リセット

このメソッドは **、Reset**メソッドの実装を提供します。

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ienumonstlimplskip"></a><a name="skip"></a>イエヌオンストルプル::スキップ

このメソッドは **、Skip**メソッドの実装を提供します。

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]スキップする要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
