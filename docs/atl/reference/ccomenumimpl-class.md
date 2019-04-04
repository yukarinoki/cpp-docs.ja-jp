---
title: CComEnumImpl クラス
ms.date: 11/04/2016
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: ccd083f3bfd9ae694c97e466fcb40b348fec0c27
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273777"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl クラス

このクラスは、配列に列挙されている項目を格納する、COM の列挙子インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
COM の列挙子インターフェイス。 参照してください[IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring)例についてはします。

*piid*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の種類。

*コピー*<br/>
同種[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|コンストラクターです。|
|[CComEnumImpl::~CComEnumImpl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComEnumImpl::Clone](#clone)|実装、**複製**インターフェイスのメソッドを列挙します。|
|[CComEnumImpl::Init](#init)|列挙子を初期化します。|
|[CComEnumImpl::Next](#next)|実装**次**します。|
|[CComEnumImpl::Reset](#reset)|実装**リセット**します。|
|[CComEnumImpl::Skip](#skip)|実装**スキップ**します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|配列の最初の項目へのポインター。|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|を通じて渡されるコピー フラグ`Init`します。|
|[CComEnumImpl::m_end](#m_end)|配列の最後の項目の次の位置へのポインター。|
|[CComEnumImpl::m_iter](#m_iter)|配列内の現在の項目へのポインター。|
|[CComEnumImpl::m_spUnk](#m_spunk)|`IUnknown`列挙されているコレクションを提供するオブジェクトのポインター。|

## <a name="remarks"></a>Remarks

参照してください[IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring)メソッドの実装の例についてはします。 `CComEnumImpl` 配列内に列挙されている項目が格納 COM 列挙子インターフェイスの実装を提供します。 このクラスに似ています、`IEnumOnSTLImpl`クラス、列挙子インターフェイスの実装を提供する C++ 標準ライブラリ コンテナーに基づいています。

> [!NOTE]
>  さらに間の違いについて詳しく`CComEnumImpl`と`IEnumOnSTLImpl`を参照してください[保ちます](#init)します。

通常、*いない*このインターフェイスの実装から派生することによって、独自の列挙子クラスを作成する必要があります。 インスタンスを作成するが一般的では、配列に基づく ATL が指定した列挙子を使用する場合は、 [CComEnum](../../atl/reference/ccomenum-class.md)します。

ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開している) カスタム列挙子を提供する必要がある場合は、このクラスから派生することができます。 このような状況で可能性をオーバーライドする必要がありますが、 [CComEnumImpl::Clone](#clone)独自の実装を提供するメソッド。

詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComEnumImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="ccomenumimpl"></a>  CComEnumImpl::CComEnumImpl

コンストラクターです。

```
CComEnumImpl();
```

##  <a name="dtor"></a>  CComEnumImpl::~CComEnumImpl

デストラクターです。

```
~CComEnumImpl();
```

##  <a name="init"></a>  CComEnumImpl::Init

クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>パラメーター

*begin*<br/>
列挙するアイテムを含む配列の最初の要素へのポインター。

*end*<br/>
列挙するアイテムを含む配列の最後の要素の次の位置へのポインター。

*pUnk*<br/>
[in]`IUnknown`保持する必要がアライブ列挙子の有効期間中にオブジェクトのポインター。 このようなオブジェクトが存在しない場合は、NULL を渡します。

*flags*<br/>
列挙子が配列の所有権を取得する必要があるかどうか、またはそのコピーを作成かどうかを指定するフラグ。 使用可能な値は次のとおりです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

このメソッドを 1 回だけ呼び出す: 列挙子を初期化し、それを使用して、廃棄します。

別のオブジェクトに保持されている配列内の項目にポインターを渡す場合 (および、データをコピーする列挙子を確認しない) 場合は使用できます、 *pUnk*パラメーター オブジェクトと配列を保持している限り、列挙子を利用できるようにすることを確認するにはその必要があります。 列挙子を維持するオブジェクトを COM 参照を保持するだけです。 列挙子が破棄されるときに、COM 参照は自動的に解放されます。

*フラグ*パラメーターでは、列挙子が渡された配列の要素を処理する方法を指定することができます。 *フラグ*から値のいずれかを実行、`CComEnumFlags`次に示す列挙体。

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy` 配列の有効期間が、列挙子によって制御されていないことを意味します。 静的またはで識別されるオブジェクトに、配列がここでは、する*pUnk*不要になったときに、配列を解放する必要になります。

`AtlFlagTakeOwnership` 配列の破棄は、列挙子によって制御することを意味します。 ここでは、配列する必要がありますが動的に割り当てられて使用**新しい**します。 列挙子、デストラクターで配列が削除されます。 NULL を渡すと、通常*pUnk*、何らかの理由により、列挙子の破棄の通知を受け取る必要がある場合でも、有効なポインターを渡すことができます。

`AtlFlagCopy` 新しい配列が渡された配列にコピーすることによって作成されることを意味`Init`します。 新しい配列の有効期間は、列挙子によって制御されます。 列挙子、デストラクターで配列が削除されます。 NULL を渡すと、通常*pUnk*、何らかの理由により、列挙子の破棄の通知を受け取る必要がある場合でも、有効なポインターを渡すことができます。

> [!NOTE]
>  このメソッドのプロトタイプでは、配列の要素を指定の型として`T`ここで、`T`クラスをテンプレート パラメーターとして定義されました。 これは、COM インターフェイスのメソッドを使用して公開されている同じ種類[CComEnumImpl::Next](#next)します。 このこととは異なり[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)、このクラスは、別のストレージをサポートしていませんし、データ型を公開します。 配列内の要素のデータ型は COM インターフェイスを使用して公開されるデータ型と同じである必要があります。

##  <a name="clone"></a>  CComEnumImpl::Clone

このメソッドの実装を提供、**複製**メソッド型のオブジェクトを作成して`CComEnum`、同じ配列と、現在のオブジェクトで使用される反復子で初期化して、新しく作成された、インターフェイスを返すオブジェクト。

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>パラメーター

*ppEnum*<br/>
[out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ある複製された列挙子を加えないでください独自に注意してください。 元の列挙子によって使用されるデータのコピー (または所有権の取得)。 必要に応じて、複製された列挙子は維持元の列挙子 (COM の参照を使用) する必要がある限り、データが使用できることを確認します。

##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk

このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、残っているアライブ列挙子の有効期間中にことを確認します。

```
CComPtr<IUnknown> m_spUnk;
```

##  <a name="m_begin"></a>  CComEnumImpl::m_begin

列挙するアイテムを含む配列の最後の要素の次の位置へのポインター。

```
T* m_begin;
```

##  <a name="m_end"></a>  CComEnumImpl::m_end

列挙するアイテムを含む配列の最初の要素へのポインター。

```
T* m_end;
```

##  <a name="m_iter"></a>  CComEnumImpl::m_iter

列挙するアイテムを含む配列の現在の要素へのポインター。

```
T* m_iter;
```

##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags

渡される、フラグ[保ちます](#init)します。

```
DWORD m_dwFlags;
```

##  <a name="next"></a>  CComEnumImpl::Next

このメソッドの実装を提供、**次**メソッド。

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]要求された要素の数。

*rgelt*<br/>
[out]要素を格納する配列。

*内*<br/>
[out]実際に返される要素の数*rgelt*します。 これより小さい*celt*場合よりも少ない*celt*要素がリストに残っています。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="reset"></a>  CComEnumImpl::Reset

このメソッドの実装を提供、**リセット**メソッド。

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="skip"></a>  CComEnumImpl::Skip

このメソッドの実装を提供、**スキップ**メソッド。

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]スキップする要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

場合、E_INVALIDARG を返します*celt* 0 より小さい場合は S_FALSE 返します*celt*要素が返されます、それ以外の場合は S_OK を返します。

## <a name="see-also"></a>関連項目

[IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum クラス](../../atl/reference/ccomenum-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
