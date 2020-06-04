---
title: クラス
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
ms.openlocfilehash: 965e0a8bf6c890882754b60e2785832933d1c52c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327863"
---
# <a name="ccomenumimpl-class"></a>クラス

このクラスは、列挙される項目が配列に格納される COM 列挙子インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
COM 列挙子インターフェイス。 例については[、IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring)を参照してください。

*ピッド*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の型。

*コピー*<br/>
同種[のコピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コマヌビレンプル::コマヌプル](#ccomenumimpl)|コンストラクターです。|
|[コマヌプル::~コマヌプル](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クコム列挙型::クローン](#clone)|**Clone**列挙インターフェイス メソッドの実装。|
|[コマヌビレンプル::イニト](#init)|列挙子を初期化します。|
|[コマヌビImpl::次へ](#next)|**Next**の実装。|
|[クコム列挙型::リセット](#reset)|**リセット**の実装。|
|[クコム列挙型::スキップ](#skip)|**スキップ**の実装。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コム列挙型::m_begin](#m_begin)|配列の最初の項目へのポインター。|
|[コム列挙型::m_dwFlags](#m_dwflags)|を通過するフラグ`Init`をコピーします。|
|[コマ列挙型::m_end](#m_end)|配列の最後の項目のすぐ外にある位置へのポインター。|
|[コム列挙型::m_iter](#m_iter)|配列内の現在の項目へのポインター。|
|[コマ列挙型::m_spUnk](#m_spunk)|列挙`IUnknown`されるコレクションを提供するオブジェクトのポインター。|

## <a name="remarks"></a>解説

メソッドの実装例については[、「IEnumString」](/windows/win32/api/objidl/nn-objidl-ienumstring)を参照してください。 `CComEnumImpl`は、列挙される項目が配列に格納される COM 列挙子インターフェイスの実装を提供します。 このクラスは、C++`IEnumOnSTLImpl`標準ライブラリ コンテナーに基づく列挙子インターフェイスの実装を提供するクラスに似ています。

> [!NOTE]
> と の`CComEnumImpl``IEnumOnSTLImpl`違いの詳細については[、「CComEnumImpl::Init](#init)」を参照してください。

通常、このインターフェイスの実装から派生して独自の列挙子クラスを作成する必要*はありません*。 配列に基づいて ATL が提供する列挙子を使用する場合は[、CComEnum](../../atl/reference/ccomenum-class.md)のインスタンスを作成する方が一般的です。

ただし、カスタム列挙子 (たとえば、列挙子インターフェイスに加えてインターフェイスを公開する列挙子) を指定する必要がある場合は、このクラスから派生できます。 このような場合は、独自の実装を提供する[CComEnumImpl::Clone](#clone)メソッドをオーバーライドする必要があります。

詳細については、「 [ATL コレクションと列挙子](../../atl/atl-collections-and-enumerators.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComEnumImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>コマヌビレンプル::コマヌプル

コンストラクターです。

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>コマヌプル::~コマヌプル

デストラクターです。

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>コマヌビレンプル::イニト

列挙子インターフェイスへのポインターをクライアントに返す前に、このメソッドを呼び出す必要があります。

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>パラメーター

*開始*<br/>
列挙する項目を含む配列の最初の要素へのポインター。

*end*<br/>
列挙する項目を含む配列の最後の要素のちょうど後の位置へのポインター。

*パンク*<br/>
[in]列挙`IUnknown`子の有効期間中に保持する必要があるオブジェクトのポインター。 そのようなオブジェクトが存在しない場合は NULL を渡します。

*フラグ*<br/>
列挙子が配列の所有権を取得するか、または配列のコピーを作成するかを指定するフラグ。 使用できる値は以下のとおりです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドを 1 回だけ呼び出す — 列挙子を初期化し、それを使用して、それを捨てる。

別のオブジェクトに保持されている配列内の項目へのポインタを渡す場合 (および列挙子にデータのコピーを要求しない場合 *)、pUnk*パラメータを使用して、列挙子が必要な限り、オブジェクトとそれが保持する配列を使用できるようにします。 列挙子は、オブジェクトの COM 参照を保持して、オブジェクトを保持します。 COM 参照は、列挙子が破棄されると自動的に解放されます。

*flags*パラメーターを使用すると、列挙子が渡される配列要素をどのように処理するかを指定できます。 *フラグ*は、次の`CComEnumFlags`列挙体の値の 1 つを取ることができます。

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`配列の有効期間が列挙子によって制御されないことを意味します。 この場合、配列が静的であるか *、pUnk*で識別されたオブジェクトが不要になったときに配列を解放する必要があります。

`AtlFlagTakeOwnership`配列の破棄は列挙子によって制御されることを意味します。 この場合、配列は**new**を使用して動的に割り当てられている必要があります。 列挙子は、デストラクター内の配列を削除します。 通常は、何らかの理由で列挙子の破棄を通知する必要がある場合でも、有効なポインタを渡すことができますが、 *pUnk*には NULL を渡します。

`AtlFlagCopy`に渡された配列をコピーして新しい配列を作成することを意味します`Init`。 新しい配列の有効期間は、列挙子によって制御されます。 列挙子は、デストラクター内の配列を削除します。 通常は、何らかの理由で列挙子の破棄を通知する必要がある場合でも、有効なポインタを渡すことができますが、 *pUnk*には NULL を渡します。

> [!NOTE]
> このメソッドのプロトタイプは、クラスのテンプレート パラメーターとして定義`T``T`された配列要素を type として指定します。 これは、COM インターフェイス メソッド[によって](#next)公開されるのと同じ型です。 このことは[、IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)とは異なり、このクラスは、異なるストレージと公開データ型をサポートしていないということを意味します。 配列内の要素のデータ型は、COM インターフェイスによって公開されるデータ型と同じである必要があります。

## <a name="ccomenumimplclone"></a><a name="clone"></a>クコム列挙型::クローン

このメソッドは、型`CComEnum`のオブジェクトを作成し、現在のオブジェクトで使用されるのと同じ配列と反復器で初期化し、新しく作成されたオブジェクトのインターフェイスを返すことによって **、Clone**メソッドの実装を提供します。

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>パラメーター

*ppEnum*<br/>
[アウト]現在の列挙子から複製された新しく作成されたオブジェクトの列挙子インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

複製された列挙子は、元の列挙子で使用されるデータの独自のコピーを作成 (または所有権を取得) することはありません。 必要に応じて、複製された列挙子は、元の列挙子を (COM 参照を使用して) 保持し、データが必要な限り使用可能であることを確認します。

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>コマ列挙型::m_spUnk

このスマート ポインターは[、CComEnumImpl::Init](#init)に渡されるオブジェクトの参照を保持し、列挙子の有効期間中もそのオブジェクトが保持されるようにします。

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>コム列挙型::m_begin

列挙する項目を含む配列の最後の要素のちょうど後の位置へのポインター。

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>コマ列挙型::m_end

列挙する項目を含む配列の最初の要素へのポインター。

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>コム列挙型::m_iter

列挙する項目を含む配列の現在の要素へのポインター。

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>コム列挙型::m_dwFlags

に渡されたフラグ[: :Init](#init).

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>コマヌビImpl::次へ

このメソッドは **、Next**メソッドの実装を提供します。

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]要求された要素の数。

*ルゲルト*<br/>
[アウト]要素で埋める配列。

*pceltFetched*<br/>
[アウト]実際に*rgelt*で返される要素の数。 これは、リストに残っている*celt*要素よりも少ない場合は *、celt*よりも小さくなる可能性があります。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomenumimplreset"></a><a name="reset"></a>クコム列挙型::リセット

このメソッドは **、Reset**メソッドの実装を提供します。

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomenumimplskip"></a><a name="skip"></a>クコム列挙型::スキップ

このメソッドは **、Skip**メソッドの実装を提供します。

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>パラメーター

*celt*<br/>
[in]スキップする要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*celt*がゼロの場合E_INVALIDARGを返し *、celt*要素が返される値より小さい場合はS_FALSEを返し、それ以外の場合は S_OKを返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ienumonstlimpl-class.md)<br/>
[クラス](../../atl/reference/ccomenum-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
