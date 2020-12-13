---
description: '詳細情報: IProvideClassInfo2Impl クラス'
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
ms.openlocfilehash: 9c3422c98ebd857231f492efb77d51a0a49acb76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139258"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl クラス

このクラスは、 [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) メソッドと [は iprovideclassinfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) メソッドの既定の実装を提供します。

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
コクラスの既定の送信ディスパッチインターフェイスの識別子へのポインター。

*plibid*<br/>
インターフェイスに関する情報を格納しているタイプライブラリの LIBID へのポインター。 既定では、サーバーレベルのタイプライブラリが渡されます。

*wMajor*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。

*wMinor*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*tihclass*<br/>
コクラスの型情報を管理するために使用されるクラス。 既定値は `CComTypeInfoHolder` です。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl:: Iprovideclassinfo.getclassinfo](#getclassinfo)|`ITypeInfo`コクラスの型情報へのポインターを取得します。|
|[IProvideClassInfo2Impl:: GetGUID](#getguid)|オブジェクトの送信ディスパッチインターフェイスの GUID を取得します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[IProvideClassInfo2Impl:: _tih](#_tih)|コクラスの型情報を管理します。|

## <a name="remarks"></a>解説

[は iprovideclassinfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2)インターフェイスは、メソッドを追加して[IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo)を拡張し `GetGUID` ます。 このメソッドを使用すると、クライアントは、既定のイベントセットに対するオブジェクトの送信インターフェイス IID を取得できます。 クラスは、 `IProvideClassInfo2Impl` メソッドとメソッドの既定の実装を提供し `IProvideClassInfo` `IProvideClassInfo2` ます。

`IProvideClassInfo2Impl``CComTypeInfoHolder`コクラスの型情報を管理する型の静的メンバーを格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a> IProvideClassInfo2Impl:: Iprovideclassinfo.getclassinfo

`ITypeInfo`コクラスの型情報へのポインターを取得します。

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IProvideClassInfo:: iprovideclassinfo.getclassinfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) 」を参照してください。

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a> IProvideClassInfo2Impl:: GetGUID

オブジェクトの送信ディスパッチインターフェイスの GUID を取得します。

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>解説

Windows SDK の「 [は iprovideclassinfo2:: GetGUID](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) 」を参照してください。

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a> IProvideClassInfo2Impl::IProvideClassInfo2Impl

コンストラクターです。

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>解説

`AddRef` [_Tih](#_tih)メンバーに対してを呼び出します。 このデストラクターは `Release` を呼び出します。

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a> IProvideClassInfo2Impl:: _tih

この静的データメンバーはクラステンプレートパラメーター *tihclass* のインスタンスで、既定では `CComTypeInfoHolder` です。

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>解説

`_tih` コクラスの型情報を管理します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
