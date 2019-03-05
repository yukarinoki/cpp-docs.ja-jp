---
title: IProvideClassInfo2Impl クラス
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
ms.openlocfilehash: 41a0756250e749a07d48ad4f090c2f1c322aa558
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289937"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl クラス

このクラスの既定の実装を提供する、 [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo)と[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2)メソッド。

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

*pcoclsid*<br/>
コクラスの識別子へのポインター。

*psrcid*<br/>
コクラスの既定のディスパッチ インターフェイスの送信の識別子へのポインター。

*plibid*<br/>
インターフェイスに関する情報を格納するタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。

*wMajor*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。

*wMinor*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*tihclass*<br/>
コクラスの種類の情報を管理するために使用するクラスです。 既定値は `CComTypeInfoHolder` です。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|取得、`ITypeInfo`コクラスの種類の情報へのポインター。|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|オブジェクトの送信のディスパッチ インターフェイスの GUID を取得します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|コクラスの型情報を管理します。|

## <a name="remarks"></a>Remarks

[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2)インターフェイスは、拡張[IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo)を追加して、`GetGUID`メソッド。 このメソッドでは、クライアントは既定のイベント セットのオブジェクトのアウトゴーイング インターフェイス IID を取得できます。 クラス`IProvideClassInfo2Impl`の既定の実装を提供します、`IProvideClassInfo`と`IProvideClassInfo2`メソッド。

`IProvideClassInfo2Impl` 型の静的メンバーを含む`CComTypeInfoHolder`コクラスの型情報を管理します。

## <a name="inheritance-hierarchy"></a>継承階層

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo

取得、`ITypeInfo`コクラスの種類の情報へのポインター。

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Remarks

参照してください[IProvideClassInfo::GetClassInfo](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) Windows SDK にします。

##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID

オブジェクトの送信のディスパッチ インターフェイスの GUID を取得します。

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Remarks

参照してください[IProvideClassInfo2::GetGUID](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) Windows SDK にします。

##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl

コンストラクターです。

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Remarks

呼び出し`AddRef`上、 [_tih](#_tih)メンバー。 このデストラクターは `Release` を呼び出します。

##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih

この静的データ メンバーは、クラス テンプレート パラメーターのインスタンス*tihclass*、既定では、`CComTypeInfoHolder`します。

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Remarks

`_tih` コクラスの型情報を管理します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
