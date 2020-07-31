---
title: IDataObjectImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 379dd3304d96afcd2b0e98ec4a98f1bac64d4ad9
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470772"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl クラス

このクラスには、Uniform Data Transfer をサポートし、接続を管理するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IDataObjectImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IDataObjectImpl::D アドバイス](#dadvise)|データオブジェクトとアドバイズシンク間の接続を確立します。 これにより、アドバイズシンクは、オブジェクトの変更の通知を受け取ることができます。|
|[IDataObjectImpl::D のアドバイズ中止](#dunadvise)|によって以前に確立された接続を終了 `DAdvise` します。|
|[IDataObjectImpl:: EnumDAdvise](#enumdadvise)|現在のアドバイザリコネクションを反復処理する列挙子を作成します。|
|[IDataObjectImpl:: EnumFormatEtc](#enumformatetc)|`FORMATETC`データオブジェクトでサポートされている構造体を反復処理する列挙子を作成します。 ATL 実装は E_NOTIMPL を返します。|
|[IDataObjectImpl:: 焼討 Datachange](#firedatachange)|各アドバイズシンクに変更通知を送り返します。|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|論理的に等価な `FORMATETC` 構造体を、より複雑なものに取得します。 ATL 実装は E_NOTIMPL を返します。|
|[IDataObjectImpl:: GetData](#getdata)|データオブジェクトからクライアントにデータを転送します。 データは構造体で記述され、 `FORMATETC` 構造体を通じて転送され `STGMEDIUM` ます。|
|[IDataObjectImpl:: GetDataHere](#getdatahere)|と似て `GetData` いますが、クライアントが構造体を割り当てる必要がある点が異なり `STGMEDIUM` ます。 ATL 実装は E_NOTIMPL を返します。|
|[IDataObjectImpl:: QueryGetData](#querygetdata)|データオブジェクトが、データ転送の特定の構造をサポートしているかどうかを判断し `FORMATETC` ます。 ATL 実装は E_NOTIMPL を返します。|
|[IDataObjectImpl:: SetData](#setdata)|クライアントからデータオブジェクトにデータを転送します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>Remarks

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)インターフェイスには、Uniform Data Transfer をサポートするメソッドが用意されています。 `IDataObject`では、 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)および[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1)という標準の形式の構造を使用してデータを取得し、格納します。

`IDataObject`では、データ変更通知を処理するための接続も管理します。 クライアントがデータオブジェクトからデータ変更通知を受信するためには、クライアントはアドバイズシンクと呼ばれるオブジェクトに[IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)インターフェイスを実装する必要があります。 次にクライアントがを呼び出すと `IDataObject::DAdvise` 、データオブジェクトとアドバイズシンクの間に接続が確立されます。

クラス `IDataObjectImpl` は、の既定の実装を提供 `IDataObject` し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl. h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::D アドバイス

データオブジェクトとアドバイズシンク間の接続を確立します。

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Remarks

これにより、アドバイズシンクは、オブジェクトの変更の通知を受け取ることができます。

接続を終了するには、 [DUnadvise](#dunadvise)を呼び出します。

Windows SDK の「 [IDataObject::D advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) 」を参照してください。

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::D のアドバイズ中止

以前に[Dadvise](#dadvise)を使用して確立された接続を終了します。

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject::D アドバイズ](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise)」を参照してください。

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl:: EnumDAdvise

現在のアドバイザリコネクションを反復処理する列挙子を作成します。

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: EnumDAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) 」を参照してください。

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IDataObjectImpl:: EnumFormatEtc

`FORMATETC`データオブジェクトでサポートされている構造体を反復処理する列挙子を作成します。

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) 」を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl:: 焼討 Datachange

現在管理されている各アドバイズシンクに変更通知を送り返します。

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc

論理的に等価な `FORMATETC` 構造体を、より複雑なものに取得します。

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: GetCanonicalFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) 」を参照してください。

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl:: GetData

データオブジェクトからクライアントにデータを転送します。

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Remarks

*PformatetcIn*パラメーターには、TYMED_MFPICT のストレージメディアの種類を指定する必要があります。

Windows SDK の「 [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 」を参照してください。

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl:: GetDataHere

と似て `GetData` いますが、クライアントが構造体を割り当てる必要がある点が異なり `STGMEDIUM` ます。

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) 」を参照してください。

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl:: QueryGetData

データオブジェクトが、データ転送の特定の構造をサポートしているかどうかを判断し `FORMATETC` ます。

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) 」を参照してください。

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>IDataObjectImpl:: SetData

クライアントからデータオブジェクトにデータを転送します。

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

Windows SDK の「 [IDataObject:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) 」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
