---
title: クラス
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
ms.openlocfilehash: 618f8248a03297120ae2504bcb30ba8f080b184d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329839"
---
# <a name="idataobjectimpl-class"></a>クラス

このクラスには、統一データ転送をサポートし、接続を管理するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IDataObjectImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IDataObjectImpl::Dアドバイス](#dadvise)|データ オブジェクトとアアドバイス シンクの間の接続を確立します。 これにより、オブジェクトの変更の通知を受信するアドバイス シンクが有効になります。|
|[IDataObjectImpl::Dアアドバイスなし](#dunadvise)|を使用して以前に確立された`DAdvise`接続を終了します。|
|[IData オブジェクトインプル::列挙型アドバイス](#enumdadvise)|現在のアドバイザリ接続を反復処理する列挙子を作成します。|
|[IData オブジェクト インプル::列挙形式の挿入](#enumformatetc)|データ オブジェクトでサポートされる構造体`FORMATETC`を反復処理する列挙子を作成します。 ATL の実装はE_NOTIMPL返します。|
|[IData オブジェクトインプル::FireDataChange](#firedatachange)|各アドバイス シンクに変更通知を送信します。|
|[IDataObjectImpl::取得カニカルフォーマットその他](#getcanonicalformatetc)|論理的に等価`FORMATETC`な構造体を、より複雑な構造体に対して取得します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトのインプル::取得データ](#getdata)|データ オブジェクトからクライアントにデータを転送します。 データは`FORMATETC`構造に記述され、構造を`STGMEDIUM`通して転送されます。|
|[IData オブジェクトインプル::取得データをここに](#getdatahere)|と同様`GetData`に、クライアントは構造体を`STGMEDIUM`割り当てる必要があります。 ATL の実装はE_NOTIMPL返します。|
|[を返します。](#querygetdata)|データ オブジェクトがデータ転送に使用`FORMATETC`する特定の構造をサポートするかどうかを決定します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトのインプレッシッター::データセット](#setdata)|クライアントからデータ オブジェクトにデータを転送します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)インターフェイスは、統一されたデータ転送をサポートするメソッドを提供します。 `IDataObject`は、標準フォーマット構造体[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)および[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)を使用してデータを取得および格納します。

`IDataObject`また、データ変更通知を処理するシンクにアドバイスを提供する接続を管理します。 クライアントがデータ オブジェクトからデータ変更通知を受信するには、クライアントは、アドバイス シンクと呼ばれるオブジェクトに[IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)インターフェイスを実装する必要があります。 クライアントが 呼び`IDataObject::DAdvise`出すと、データ オブジェクトとアアドバイス シンクの間に接続が確立されます。

クラス`IDataObjectImpl`は、デバッグ ビルド`IDataObject`でダンプ`IUnknown`デバイスに情報を送信することにより、既定の実装と実装を提供します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::Dアドバイス

データ オブジェクトとアアドバイス シンクの間の接続を確立します。

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>解説

これにより、オブジェクトの変更の通知を受信するアドバイス シンクが有効になります。

接続を終了するには[、DUnadvise](#dunadvise)に電話します。

Windows SDK[の「IDataObject::Dアドバイス](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise)」を参照してください。

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::Dアアドバイスなし

以前に[DAdvise](#dadvise)を使用して確立された接続を終了します。

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::Dアアドバイスを](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise)参照してください。

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IData オブジェクトインプル::列挙型アドバイス

現在のアドバイザリ接続を反復処理する列挙子を作成します。

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::列挙アダアドバイス](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise)」を参照してください。

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IData オブジェクト インプル::列挙形式の挿入

データ オブジェクトでサポートされる構造体`FORMATETC`を反復処理する列挙子を作成します。

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::列挙形式」を](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc)参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IData オブジェクトインプル::FireDataChange

現在管理されている各アドバイス シンクに変更通知を送信します。

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::取得カニカルフォーマットその他

論理的に等価`FORMATETC`な構造体を、より複雑な構造体に対して取得します。

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::GetCanonical フォーマットの追加」](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc)を参照してください。

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>オブジェクトのインプル::取得データ

データ オブジェクトからクライアントにデータを転送します。

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>解説

*pformatetcIn*パラメーターは、ストレージ・メディア・タイプのTYMED_MFPICTを指定する必要があります。

Windows SDK[の「IDataObject::GetData」](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)を参照してください。

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IData オブジェクトインプル::取得データをここに

と同様`GetData`に、クライアントは構造体を`STGMEDIUM`割り当てる必要があります。

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::GetDataHere」](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere)を参照してください。

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>を返します。

データ オブジェクトがデータ転送に使用`FORMATETC`する特定の構造をサポートするかどうかを決定します。

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IDataObject::クエリGetデータ](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata)」を参照してください。

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>オブジェクトのインプレッシッター::データセット

クライアントからデータ オブジェクトにデータを転送します。

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IData オブジェクト::セットデータ](/windows/win32/api/objidl/nf-objidl-idataobject-setdata)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
