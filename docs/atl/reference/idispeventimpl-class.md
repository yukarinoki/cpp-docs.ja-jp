---
title: IDispEventImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2419b4da0cad2662a246c167938d673429afbf26
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060899"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl クラス

このクラスの実装を提供する、`IDispatch`メソッド。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>パラメーター

*nID*<br/>
ソース オブジェクトの一意の識別子。 ときに`IDispEventImpl`基底クラスは、複合コントロールの場合は、このパラメーターの適切な包含コントロールのリソース ID を使用します。 それ以外の場合は、任意の正の整数を使用します。

*T*<br/>
ユーザーのクラスから派生した`IDispEventImpl`します。

*pdiid*<br/>
このクラスによって実装されるイベントのディスパッチ インターフェイスの IID へのポインター。 によって示されるタイプ ライブラリのこのインターフェイスを定義する必要があります*plibid*、 *wMajor*、および*wMinor*します。

*plibid*<br/>
ディスパッチ インターフェイスを定義するタイプ ライブラリへのポインターが指す*pdiid*します。 場合 **& GUID_**、イベント ソーシング オブジェクトからタイプ ライブラリが読み込まれます。

*wMajor*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 0 です。

*wMinor*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*tihclass*<br/>
型情報を管理するために使用するクラス*T*します。既定値は、クラス型の`CComTypeInfoHolder`。 ただし、以外の型のクラスを提供することでこのテンプレート パラメーターをオーバーライドする`CComTypeInfoHolder`します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|型情報を管理するために使用するクラスです。 既定では、`CComTypeInfoHolder`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|指定したディスパッチ識別子の関数のインデックスを検索します。|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|整数の Dispid の対応するセットを 1 つのメンバーとオプションの引数名のセットをマップします。|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|オブジェクトの型情報を取得します。|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|型情報インターフェイスの数を取得します。|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|ユーザー定義型の基本の種類を取得します。|

## <a name="remarks"></a>Remarks

`IDispEventImpl` そのインターフェイスのメソッドとイベントは、すべての実装コードを指定することがなく、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventImpl` 実装を提供、`IDispatch`メソッド。 のみで処理する必要がそのイベントの実装を指定する必要があります。

`IDispEventImpl` 適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携します。 このクラスを使用します。

追加、 [SINK_ENTRY](composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)マクロを各イベントを処理する各オブジェクトのイベント シンク マップします。 使用する場合`IDispEventImpl`複合コントロールの基本クラスを呼び出すこともできます[AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap)を確立し、イベント シンク マップのすべてのエントリのイベント ソースとの接続を解除します。 それ以外の場合やより詳細に制御を呼び出す[DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)をソース オブジェクトと、基底クラス間の接続を確立します。 呼び出す[DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)結合を解除します。

派生する必要があります`IDispEventImpl`(一意の値を使用して*nID*) の各オブジェクトのイベントを処理する必要があります。 別のソース オブジェクトに対してアドバイスを行って、1 つのソース オブジェクトに対してアドバイズで基本クラスを再利用できますが、一度に 1 つのオブジェクトで処理できるソース オブジェクトの最大数の数によって制限されます`IDispEventImpl`基本クラス。

`IDispEventImpl` 同じ機能を提供します[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)を除きへのポインターとして指定されていることのではなく、タイプ ライブラリからインターフェイスに関する型情報を取得、 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)構造体。 使用`IDispEventSimpleImpl`ときに、イベント インターフェイスを記述するタイプ ライブラリがあるまたはしないタイプ ライブラリの使用に関連するオーバーヘッドを回避します。

> [!NOTE]
> `IDispEventImpl` `IDispEventSimpleImpl`の独自の実装を提供`IUnknown::QueryInterface`それぞれを有効にする`IDispEventImpl`と`IDispEventSimpleImpl`基本クラスは、メインの COM オブジェクトのクラス メンバーへの直接アクセスを許可する一方、個別の COM id として機能します。

ActiveX イベント シンクのみサポートの戻り値の HRESULT 型または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。

詳細については、次を参照してください。 [IDispEventImpl のサポート](../../atl/supporting-idispeventimpl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId

指定したディスパッチ識別子の関数のインデックスを検索します。

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]関数の ID への参照。

*dispidMember*<br/>
[in]関数のディスパッチ ID。

*lcid*<br/>
[in]関数の ID のロケール コンテキスト

*情報*<br/>
[in]関数の呼び出し方法を示す構造体。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames

整数 Dispid を後続の呼び出しで使用できる、対応するセットを 1 つのメンバーとオプションの引数名のセットをマップ[idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)します。

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Remarks

参照してください[IDispatch::GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK にします。

##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo

オブジェクトの型情報を取得します。この型情報を使用して、インターフェイスの型情報を取得できます。

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Remarks

##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount

オブジェクトが提供する型情報インターフェイスの数 (0 または 1) を取得します。

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Remarks

参照してください[IDispatch::GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK にします。

##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType

ユーザー定義型の基本の種類を取得します。

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>パラメーター

*PTI*<br/>
[in]ポインター、 [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo)ユーザー定義型を含むインターフェイス。

*hrt*<br/>
[in]取得する型の説明へのハンドル。

### <a name="return-value"></a>戻り値

バリアントの型。

### <a name="remarks"></a>Remarks

参照してください[ITypeInfo::GetRefTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo)します。

##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl

コンストラクターです。 クラス テンプレート パラメーターの値を格納*plibid*、 *pdiid*、 *wMajor*、および*wMinor*します。

```
IDispEventImpl();
```

##  <a name="tihclass"></a>  IDispEventImpl::tihclass

この typedef は、クラス テンプレート パラメーターのインスタンス*tihclass*します。

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Remarks

クラスは、既定では、`CComTypeInfoHolder`します。 `CComTypeInfoHolder` クラスの型情報を管理します。

## <a name="see-also"></a>関連項目

[_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl クラス](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[クラスの概要](../../atl/atl-class-overview.md)