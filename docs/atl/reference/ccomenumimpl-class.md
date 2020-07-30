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
ms.openlocfilehash: 517a4e90ca21e22dcf161aefcff61a40437eabe0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226608"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl クラス

このクラスは、列挙される項目が配列に格納される COM 列挙子インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
COM 列挙子インターフェイス。 例については、「 [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) 」を参照してください。

*piid*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の型。

*コピー*<br/>
同種の[コピーポリシークラス](../../atl/atl-copy-policy-classes.md)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|コンストラクターです。|
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CComEnumImpl:: Clone](#clone)|**Clone**列挙インターフェイスメソッドの実装。|
|[CComEnumImpl:: Init](#init)|列挙子を初期化します。|
|[CComEnumImpl:: 次へ](#next)|**Next**の実装。|
|[CComEnumImpl:: Reset](#reset)|**Reset**の実装。|
|[CComEnumImpl:: Skip](#skip)|**Skip**の実装。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|[説明]|
|----------|-----------------|
|[CComEnumImpl:: m_begin](#m_begin)|配列内の最初の項目へのポインター。|
|[CComEnumImpl:: m_dwFlags](#m_dwflags)|コピーフラグが渡さ `Init` れます。|
|[CComEnumImpl:: m_end](#m_end)|配列内の最後の項目の次の位置を指すポインター。|
|[CComEnumImpl:: m_iter](#m_iter)|配列内の現在の項目へのポインター。|
|[CComEnumImpl:: m_spUnk](#m_spunk)|`IUnknown`列挙されるコレクションを提供するオブジェクトのポインター。|

## <a name="remarks"></a>解説

メソッド実装の例については、「 [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) 」を参照してください。 `CComEnumImpl`列挙される項目が配列に格納される COM 列挙子インターフェイスの実装を提供します。 このクラスは、 `IEnumOnSTLImpl` C++ 標準ライブラリコンテナーに基づく列挙子インターフェイスの実装を提供するクラスに似ています。

> [!NOTE]
> とのその他の相違点の詳細につい `CComEnumImpl` `IEnumOnSTLImpl` ては、「 [CComEnumImpl:: Init](#init)」を参照してください。

通常、このインターフェイスの実装から派生することで、独自の列挙子クラスを作成する必要はあり*ません*。 配列に基づいて ATL で提供される列挙子を使用する場合は、 [CComEnum](../../atl/reference/ccomenum-class.md)のインスタンスを作成する方が一般的です。

ただし、カスタム列挙子を提供する必要がある場合 (列挙子インターフェイスに加えてインターフェイスを公開するものなど)、このクラスから派生させることができます。 このような状況では、独自の実装を提供するために、 [CComEnumImpl:: Clone](#clone)メソッドをオーバーライドする必要がある可能性があります。

詳細については、「 [ATL コレクションと列挙子](../../atl/atl-collections-and-enumerators.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComEnumImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl

コンストラクターです。

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl

デストラクターです。

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>CComEnumImpl:: Init

列挙子インターフェイスへのポインターを任意のクライアントに渡す前に、このメソッドを呼び出す必要があります。

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>パラメーター

*初め*<br/>
列挙される項目を格納している配列の最初の要素へのポインター。

*end*<br/>
列挙される項目を格納している配列の最後の要素の次の位置を指すポインター。

*パンク*<br/>
から`IUnknown`列挙子の有効期間中に保持する必要があるオブジェクトのポインター。 そのようなオブジェクトが存在しない場合は、NULL を渡します。

*flags*<br/>
列挙子が配列の所有権を取得する必要があるかどうか、またはそのコピーを作成するかどうかを指定するフラグ。 使用可能な値を以下に示します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドを1回だけ呼び出します。列挙子を初期化し、使用してから破棄します。

別のオブジェクトに保持されている配列内の項目にポインターを渡す場合 (データをコピーするように列挙子に要求しない場合)、 *pUnk*パラメーターを使用して、列挙子が必要とする限り、そのオブジェクトと保持する配列を使用できるようにすることができます。 列挙子は、オブジェクトに対する COM 参照を保持するだけです。 COM 参照は、列挙子が破棄されると自動的に解放されます。

*Flags*パラメーターを使用すると、列挙子が渡された配列要素をどのように処理するかを指定できます。 *フラグ*は、次に示す列挙のいずれかの値を取ることができ `CComEnumFlags` ます。

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`は、配列の有効期間が列挙子によって制御されないことを意味します。 この場合、配列が静的になるか、または*pUnk*によって識別されるオブジェクトが、不要になったときに配列を解放する必要があります。

`AtlFlagTakeOwnership`は、配列の破棄が列挙子によって制御されることを意味します。 この場合、配列はを使用して動的に割り当てられている必要があり **`new`** ます。 列挙子は、そのデストラクター内の配列を削除します。 通常、 *pUnk*には NULL を渡しますが、何らかの理由で列挙子の破棄を通知する必要がある場合は、有効なポインターを渡すこともできます。

`AtlFlagCopy`は、に渡された配列をコピーすることによって、新しい配列を作成することを意味 `Init` します。 新しい配列の有効期間は、列挙子によって制御されます。 列挙子は、そのデストラクター内の配列を削除します。 通常、 *pUnk*には NULL を渡しますが、何らかの理由で列挙子の破棄を通知する必要がある場合は、有効なポインターを渡すこともできます。

> [!NOTE]
> このメソッドのプロトタイプは、配列要素を型として指定します `T` 。ここで、 `T` はクラスのテンプレートパラメーターとして定義されています。 これは、COM インターフェイスメソッド[CComEnumImpl:: Next](#next)を通じて公開される同じ型です。 これは、 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)とは異なり、このクラスは異なるストレージと公開されたデータ型をサポートしていないことを意味します。 配列内の要素のデータ型は、COM インターフェイスによって公開されるデータ型と同じである必要があります。

## <a name="ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl:: Clone

このメソッドは、型のオブジェクト**Clone**を作成し `CComEnum` 、現在のオブジェクトによって使用される同じ配列と反復子を使用して初期化し、新しく作成されたオブジェクトのインターフェイスを返すことによって、Clone メソッドの実装を提供します。

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>パラメーター

*ppEnum*<br/>
入出力現在の列挙子から複製された、新しく作成されたオブジェクトの列挙子インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

複製された列挙子は、元の列挙子によって使用されるデータのコピー (または所有権の取得) を行わないことに注意してください。 必要に応じて、複製された列挙子は、元の列挙子を (COM 参照を使用して) 保持したままにして、必要な限りデータを確実に使用できるようにします。

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>CComEnumImpl:: m_spUnk

このスマートポインターは、 [CComEnumImpl:: Init](#init)に渡されたオブジェクトへの参照を保持し、列挙子の有効期間中もそのままの状態を維持します。

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>CComEnumImpl:: m_begin

列挙される項目を格納している配列の最後の要素の次の位置を指すポインター。

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>CComEnumImpl:: m_end

列挙される項目を格納している配列の最初の要素へのポインター。

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>CComEnumImpl:: m_iter

列挙される項目を格納している配列の現在の要素へのポインター。

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>CComEnumImpl:: m_dwFlags

[CComEnumImpl:: Init](#init)に渡されるフラグ。

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>CComEnumImpl:: 次へ

このメソッドは、**次**のメソッドの実装を提供します。

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
から要求された要素の数。

*rgelt*<br/>
入出力要素を格納する配列。

*pceltFetched*<br/>
入出力*Rgelt*で実際に返される要素の数。 リストに残って*いる要素数が2未満*の場合は、この値が*2 未満に*なることがあります。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl:: Reset

このメソッドは、 **Reset**メソッドの実装を提供します。

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl:: Skip

このメソッドは、 **Skip**メソッドの実装を提供します。

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
からスキップする要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

E_INVALIDARG を返します。が0の場合は、S_FALSE を返します *。2を*超える要素が返された場合は、それ以外*の場合は*S_OK を返します。

## <a name="see-also"></a>関連項目

[IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum クラス](../../atl/reference/ccomenum-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
