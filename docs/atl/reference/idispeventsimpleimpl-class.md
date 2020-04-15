---
title: クラスをクラスします。
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 779e143094760c7bd868ad33f590f7fd8f004762
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329729"
---
# <a name="idispeventsimpleimpl-class"></a>クラスをクラスします。

このクラスは、タイプ ライブラリ`IDispatch`から型情報を取得せずにメソッドの実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>パラメーター

*nID*<br/>
ソース オブジェクトの一意の識別子。 複合`IDispEventSimpleImpl`コントロールの基本クラスである場合は、このパラメーターに対して、目的の包含コントロールのリソース ID を使用します。 それ以外の場合は、任意の正の整数を使用します。

*T*<br/>
から派生`IDispEventSimpleImpl`したユーザーのクラス。

*pdiid*<br/>
このクラスによって実装されるイベント のインターフェイスの IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IDispイベントシンプルプル::アドバイス](#advise)|既定のイベント ソースとの接続を確立します。|
|[IDisp イベントシンプルプル::Dイベントアダベント](#dispeventadvise)|イベント ソースとの接続を確立します。|
|[IDisp イベントシンプルプル::Dイベントアンアドバイス](#dispeventunadvise)|イベント ソースとの接続を解除します。|
|[IDisp イベントシンプルインプル::GetIDsOfNames](#getidsofnames)|E_NOTIMPL を返します。|
|[イベントシンプルインプル::GetTypeInfo](#gettypeinfo)|E_NOTIMPL を返します。|
|[イベントシンプルなインプル::GetTypeInfoカウント](#gettypeinfocount)|E_NOTIMPL を返します。|
|[IDisp イベントシンプルプル::呼び出し](#invoke)|イベント シンク マップに一覧表示されているイベント ハンドラーを呼び出します。|
|[IDispイベントシンプルプル::アドバイスなし](#unadvise)|既定のイベント ソースとの接続を解除します。|

## <a name="remarks"></a>解説

`IDispEventSimpleImpl`は、そのインターフェイスのすべてのメソッド/イベントの実装コードを提供することなく、イベントのデスプインターフェイスを実装する方法を提供します。 `IDispEventSimpleImpl`メソッドの実装を提供`IDispatch`します。 処理に関心のあるイベントの実装を提供するだけで済みます。

`IDispEventSimpleImpl`クラスのイベント シンク マップと連動して、適切なハンドラー関数にイベントをルーティングします。 このクラスを使用するには、次の手順に従います。

- 処理する各オブジェクトの各イベントについて[、SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロをイベント シンク マップに追加します。

- 各エントリにパラメーターとして[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)構造体へのポインターを渡すことによって、各イベントの型情報を提供します。 x86 プラットフォームでは、値`_ATL_FUNC_INFO.cc`は、__stdcallのコールバック関数呼び出しメソッドとCC_CDECLする必要があります。

- ソース オブジェクトと基本クラスの間の接続を確立するには[、DispEventAdvise](#dispeventadvise)を呼び出します。

- 接続[を切断するには、DispEventUnadvise](#dispeventunadvise)を呼び出します。

イベントを処理する`IDispEventSimpleImpl`必要があるオブジェクトごとに 、 *nID*の固有値を使用して派生させる必要があります。 基本クラスを再利用するには、あるソース オブジェクトに対してアドバイズを解除し、別のソース オブジェクトに対してアドバイズを行いますが、1 つのオブジェクトで一度に処理できるソース`IDispEventSimpleImpl`オブジェクトの最大数は、基本クラスの数によって制限されます。

`IDispEventSimplImpl`は、タイプ ライブラリからインターフェイスに関する型情報を取得しない点を除いて、 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)と同じ機能を提供します。 ウィザードでは、 に`IDispEventImpl`基づいてコードを生成しますが、`IDispEventSimpleImpl`コードを手入力で追加することで使用できます。 イベント`IDispEventSimpleImpl`インターフェイスを記述するタイプ ライブラリがない場合や、タイプ ライブラリの使用に伴うオーバーヘッドを回避する場合に使用します。

> [!NOTE]
> `IDispEventImpl`また`IDispEventSimpleImpl`、各`IUnknown::QueryInterface``IDispEventImpl`基本クラスまたは`IDispEventSimpleImpl`基本クラスが個別の COM ID として動作し、メイン COM オブジェクトのクラス メンバに直接アクセスできるようにする独自の実装を提供します。

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

詳細については[、「IDisp イベントImpl のサポート](../../atl/supporting-idispeventimpl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="idispeventsimpleimpladvise"></a><a name="advise"></a>IDispイベントシンプルプル::アドバイス

*pUnk*で表されるイベント ソースとの接続を確立します。

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]イベント ソース`IUnknown`オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

S_OKまたは失敗した HRESULT 値。

### <a name="remarks"></a>解説

接続が確立されると *、pUnk*から発生したイベントは、イベント シンク マップを使用してクラス内のハンドラーにルーティングされます。

> [!NOTE]
> クラスが複数`IDispEventSimpleImpl`のクラスから派生している場合は、目的の特定の基本クラスで呼び出しをスコープすることによって、このメソッドの呼び出しを明確にする必要があります。

`Advise`既定のイベント ソースとの接続を確立し[、AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)で決定されたオブジェクトの既定のイベント ソースの IID を取得します。

## <a name="idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDisp イベントシンプルプル::Dイベントアダベント

*pUnk*で表されるイベント ソースとの接続を確立します。

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]イベント ソース`IUnknown`オブジェクトのインターフェイスへのポインター。

*ピッド*<br/>
イベント ソース オブジェクトの IID へのポインター。

### <a name="return-value"></a>戻り値

S_OKまたは失敗した HRESULT 値。

### <a name="remarks"></a>解説

その後 *、pUnk*から発生したイベントは、イベント シンク マップを通してクラス内のハンドラにルーティングされます。

> [!NOTE]
> クラスが複数`IDispEventSimpleImpl`のクラスから派生している場合は、目的の特定の基本クラスで呼び出しをスコープすることによって、このメソッドの呼び出しを明確にする必要があります。

`DispEventAdvise`で指定されたイベント ソースとの接続を`pdiid`確立します。

## <a name="idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDisp イベントシンプルプル::Dイベントアンアドバイス

*pUnk*で表されるイベント ソースとの接続を解除します。

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]イベント ソース`IUnknown`オブジェクトのインターフェイスへのポインター。

*ピッド*<br/>
イベント ソース オブジェクトの IID へのポインター。

### <a name="return-value"></a>戻り値

S_OKまたは失敗した HRESULT 値。

### <a name="remarks"></a>解説

接続が切断されると、イベント シンク マップにリストされているハンドラー関数にイベントがルーティングされなくなります。

> [!NOTE]
> クラスが複数`IDispEventSimpleImpl`のクラスから派生している場合は、目的の特定の基本クラスで呼び出しをスコープすることによって、このメソッドの呼び出しを明確にする必要があります。

`DispEventAdvise`で指定されたイベント ソースと確立された接続を`pdiid`切断します。

## <a name="idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDisp イベントシンプルインプル::GetIDsOfNames

この戻り`IDispatch::GetIDsOfNames`E_NOTIMPLの実装。

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetIDsOfNames」](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)を参照してください。

## <a name="idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>イベントシンプルインプル::GetTypeInfo

この戻り`IDispatch::GetTypeInfo`E_NOTIMPLの実装。

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetTypeInfo」](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo)を参照してください。

## <a name="idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>イベントシンプルなインプル::GetTypeInfoカウント

この戻り`IDispatch::GetTypeInfoCount`E_NOTIMPLの実装。

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetTypeInfoCount」](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)を参照してください。

## <a name="idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDisp イベントシンプルプル::呼び出し

この実装では`IDispatch::Invoke`、イベント シンク マップにリストされているイベント ハンドラーを呼び出します。

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>解説

[「IDispatch::呼び出し](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)」を参照してください。

## <a name="idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispイベントシンプルプル::アドバイスなし

*pUnk*で表されるイベント ソースとの接続を解除します。

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]イベント ソース`IUnknown`オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

S_OKまたは失敗した HRESULT 値。

### <a name="remarks"></a>解説

接続が切断されると、イベント シンク マップにリストされているハンドラー関数にイベントがルーティングされなくなります。

> [!NOTE]
> クラスが複数`IDispEventSimpleImpl`のクラスから派生している場合は、目的の特定の基本クラスで呼び出しをスコープすることによって、このメソッドの呼び出しを明確にする必要があります。

`Unadvise`で指定された既定のイベント ソースで確立された接続を`pdiid`切断します。

`Unavise`既定のイベント ソースとの接続を解除すると[、AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)で決定されたオブジェクトの既定のイベント ソースの IID を取得します。

## <a name="see-also"></a>関連項目

[_ATL_FUNC_INFO構造](../../atl/reference/atl-func-info-structure.md)<br/>
[クラスをディスパッチインプラ](../../atl/reference/idispatchimpl-class.md)<br/>
[クラスを追加します。](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
