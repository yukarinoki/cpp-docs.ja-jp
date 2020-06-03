---
title: クラスを追加します。
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: fa6e9f972accd0115d9f1e3248bd97ddde0c3c63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329763"
---
# <a name="idispeventimpl-class"></a>クラスを追加します。

このクラスは、メソッドの実装`IDispatch`を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

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
ソース オブジェクトの一意の識別子。 複合`IDispEventImpl`コントロールの基本クラスである場合は、このパラメーターに対して、目的の包含コントロールのリソース ID を使用します。 それ以外の場合は、任意の正の整数を使用します。

*T*<br/>
から派生`IDispEventImpl`したユーザーのクラス。

*pdiid*<br/>
このクラスによって実装されるイベント のインターフェイスの IID へのポインター。 このインターフェイスは *、plibid*、 *wMajor*、および*wMinor*で示されるタイプ ライブラリで定義する必要があります。

*プリビッド*<br/>
*pdiid*が指すディスパッチ インターフェイスを定義するタイプ ライブラリへのポインタ。 **GUID_NULL&** 場合、タイプ ライブラリはイベントをソースするオブジェクトから読み込まれます。

*wメジャー*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 0 です。

*wマイナー*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*ティクラス*<br/>
*T*の型情報を管理するために使用されるクラス。既定値は型`CComTypeInfoHolder`のクラスです。ただし、以外の型のクラスを指定することで、このテンプレート パラメーターをオーバーライド`CComTypeInfoHolder`できます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[イベントインプル::_tihclass](../../atl/reference/idispeventimpl-class.md)|型情報の管理に使用されるクラス。 既定では、`CComTypeInfoHolder` になります。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[イベントインプル::IDispイベントインプル](#idispeventimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イベントインプル::ゲットファンクインフォスを取得します。](#getfuncinfofromid)|指定したディスパッチ識別子の関数インデックスを検索します。|
|[イベントインプル::ゲットIdSOfNames](#getidsofnames)|単一のメンバーと引数名のオプションのセットを、対応する整数の DPID のセットにマップします。|
|[イベントインプル::GetTypeInfo](#gettypeinfo)|オブジェクトの型情報を取得します。|
|[イベントのインプル::GetTypeInfoカウント](#gettypeinfocount)|型情報インターフェイスの数を取得します。|
|[イベントインプル::ユーザー定義型](#getuserdefinedtype)|ユーザー定義型の基本型を取得します。|

## <a name="remarks"></a>解説

`IDispEventImpl`は、そのインターフェイスのすべてのメソッド/イベントの実装コードを提供することなく、イベントのデスプインターフェイスを実装する方法を提供します。 `IDispEventImpl`メソッドの実装を提供`IDispatch`します。 処理に関心のあるイベントの実装を提供するだけで済みます。

`IDispEventImpl`クラスのイベント シンク マップと連動して、適切なハンドラー関数にイベントをルーティングします。 このクラスを使用するには、次の手順に従います。

処理する各オブジェクトの各イベントについて[、SINK_ENTRY](composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)マクロをイベント シンク マップに追加します。 複合コントロール`IDispEventImpl`の基本クラスとして使用する場合は[、AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap)を呼び出して、イベント シンク マップ内のすべてのエントリのイベント ソースとの接続を確立および解除できます。 その他の場合、またはより大きな制御を行うために[、DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)を呼び出して、ソース オブジェクトと基本クラスの間の接続を確立します。 接続[を切断するには、DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)を呼び出します。

イベントを処理する`IDispEventImpl`必要があるオブジェクトごとに 、 *nID*の固有値を使用して派生させる必要があります。 基本クラスを再利用するには、あるソース オブジェクトに対してアドバイズを解除し、別のソース オブジェクトに対してアドバイズを行いますが、1 つのオブジェクトで一度に処理できるソース`IDispEventImpl`オブジェクトの最大数は、基本クラスの数によって制限されます。

`IDispEventImpl`は、インターフェイスに関する型情報を[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)構造体へのポインターとして指定するのではなく、タイプ ライブラリから取得する点を除いて、 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)と同じ機能を提供します。 イベント`IDispEventSimpleImpl`インターフェイスを記述するタイプ ライブラリがない場合や、タイプ ライブラリの使用に伴うオーバーヘッドを回避する場合に使用します。

> [!NOTE]
> `IDispEventImpl`また`IDispEventSimpleImpl`、メイン COM`IUnknown::QueryInterface`オブジェクトの`IDispEventImpl`クラス`IDispEventSimpleImpl`メンバに直接アクセスできるようにしながら、各基本クラスと基本クラスを個別の COM ID として動作させる独自の実装を提供します。

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

詳細については[、「IDisp イベントImpl のサポート](../../atl/supporting-idispeventimpl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`_IDispEvent`

`_IDispEventLocator`

[イベントシンプルプル](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>イベントインプル::ゲットファンクインフォスを取得します。

指定したディスパッチ識別子の関数インデックスを検索します。

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]関数の ID への参照。

*ディスピッドメンバー*<br/>
[in]関数のディスパッチ ID。

*lcid*<br/>
[in]関数 ID のロケール コンテキスト。

*info*<br/>
[in]関数の呼び出し方法を示す構造体。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>イベントインプル::ゲットIdSOfNames

単一のメンバーとオプションの引数名のセットを[、IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)への後続の呼び出しで使用できる、対応する整数の DPID のセットにマップします。

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetIDsOfNames」](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)を参照してください。

## <a name="idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>イベントインプル::GetTypeInfo

オブジェクトの型情報を取得します。この型情報を使用して、インターフェイスの型情報を取得できます。

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>解説

## <a name="idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>イベントのインプル::GetTypeInfoカウント

オブジェクトが提供する型情報インターフェイスの数 (0 または 1) を取得します。

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetTypeInfoCount」](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)を参照してください。

## <a name="idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>イベントインプル::ユーザー定義型

ユーザー定義型の基本型を取得します。

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>パラメーター

*Pti*<br/>
[in]ユーザー定義型を含む[ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo)インターフェイスへのポインター。

*Hrt*<br/>
[in]取得する型の説明へのハンドル。

### <a name="return-value"></a>戻り値

バリアントの型。

### <a name="remarks"></a>解説

[「ITypeInfo::GetRefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo)」を参照してください。

## <a name="idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>イベントインプル::IDispイベントインプル

コンストラクターです。 クラス テンプレート パラメータ*plibid* *、pdiid* *、wMajor*、および*wMinor*の値を格納します。

```
IDispEventImpl();
```

## <a name="idispeventimpltihclass"></a><a name="tihclass"></a>IDispイベントインプル::ティクラス

この typedef はクラス テンプレート パラメーター *tihclass*のインスタンスです。

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>解説

既定では、クラスは`CComTypeInfoHolder`です。 `CComTypeInfoHolder`は、クラスの型情報を管理します。

## <a name="see-also"></a>関連項目

[_ATL_FUNC_INFO構造](../../atl/reference/atl-func-info-structure.md)<br/>
[クラスをディスパッチインプラ](../../atl/reference/idispatchimpl-class.md)<br/>
[クラスをクラスします。](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
