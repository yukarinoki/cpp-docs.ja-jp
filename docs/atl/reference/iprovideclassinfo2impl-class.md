---
title: クラスをクラスします。
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: 0d1ee9acc1cfabc71ecf33fcb5919d826899c671
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329569"
---
# <a name="iprovideclassinfo2impl-class"></a>クラスをクラスします。

このクラスは、[メソッド](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo)の既定の[実装を提供](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2)します。

## <a name="syntax"></a>構文

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>パラメーター

*プコクシド*<br/>
コクラスの識別子へのポインター。

*psrcid*<br/>
コクラスの既定の発信ディスイクス インターフェイスの識別子へのポインター。

*プリビッド*<br/>
インターフェイスに関する情報を含むタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。

*wメジャー*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。

*wマイナー*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*ティクラス*<br/>
コクラスの型情報を管理するために使用されるクラス。 既定値は `CComTypeInfoHolder` です。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[2Impl::クラス情報2Impl](#iprovideclassinfo2impl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クラス情報2Impl::Getクラス情報](#getclassinfo)|コクラスの`ITypeInfo`型情報へのポインターを取得します。|
|[2 次の機能を提供します。](#getguid)|オブジェクトの発信の disp インターフェイスの GUID を取得します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[2Impl::_tih](#_tih)|コクラスの型情報を管理します。|

## <a name="remarks"></a>解説

インターフェイスは、メソッド[を](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2)追加することによって[IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo)を拡張`GetGUID`します。 このメソッドを使用すると、クライアントは、既定のイベント セットに対するオブジェクトの出力インターフェイス IID を取得できます。 クラス`IProvideClassInfo2Impl`は、 メソッドの既定`IProvideClassInfo`の`IProvideClassInfo2`実装を提供します。

`IProvideClassInfo2Impl`には、コクラスの型`CComTypeInfoHolder`情報を管理する型の静的メンバーが含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a>クラス情報2Impl::Getクラス情報

コクラスの`ITypeInfo`型情報へのポインターを取得します。

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>解説

次[を参照](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo)してください。

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a>2 次の機能を提供します。

オブジェクトの発信の disp インターフェイスの GUID を取得します。

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>解説

Windows SDK[の「クラス情報2::GetGUID」を](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid)参照してください。

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a>2Impl::クラス情報2Impl

コンストラクターです。

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>解説

_tih`AddRef`メンバー[_tih](#_tih)を呼び出します。 このデストラクターは `Release` を呼び出します。

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a>2Impl::_tih

この静的データ メンバーは、クラス テンプレート パラメーター *tihclass*のインスタンスで、`CComTypeInfoHolder`既定ではです。

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>解説

`_tih`コクラスの型情報を管理します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
