---
description: 詳細については、「IAxWinHostWindow インターフェイス」を参照してください。
title: IAxWinHostWindow インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: 86cccd2b9ae19d5020cd1cf7ff2f0aff8759060e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139712"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow インターフェイス

このインターフェイスには、コントロールとそのホストオブジェクトを操作するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[AttachControl](#attachcontrol)|既存のコントロールをホストオブジェクトにアタッチします。|
|[CreateControl](#createcontrol)|コントロールを作成し、ホストオブジェクトにアタッチします。|
|[CreateControlEx](#createcontrolex)|コントロールを作成してホストオブジェクトにアタッチし、必要に応じてイベントハンドラーを設定します。|
|[QueryControl](#querycontrol)|ホストされるコントロールへのインターフェイスポインターを返します。|
|[SetExternalDispatch](#setexternaldispatch)|外部インターフェイスを設定 `IDispatch` します。|
|[SetExternalUIHandler](#setexternaluihandler)|外部インターフェイスを設定 `IDocHostUIHandlerDispatch` します。|

## <a name="remarks"></a>解説

このインターフェイスは、ATL の ActiveX コントロールのホストオブジェクトによって公開されます。 このインターフェイスのメソッドを呼び出して、ホストオブジェクトに対してコントロールを作成またはアタッチしたり、ホストされているコントロールからインターフェイスを取得したり、Web ブラウザーをホストするときに使用する外部ディスパッチインターフェイスまたは UI ハンドラーを設定したりします。

## <a name="requirements"></a>要件

このインターフェイスの定義は、次に示すように、IDL または C++ として使用できます。

|[定義の種類]|ファイル|
|---------------------|----------|
|IDL|ATLIFace|
|C++|ATLIFace (ATLBase. h にも含まれる)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a> IAxWinHostWindow:: AttachControl

*HWnd* で識別されるウィンドウを使用して、既存の (および以前に初期化された) コントロールをホストオブジェクトにアタッチします。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*pUnkControl*<br/>
から `IUnknown` ホストオブジェクトにアタッチされるコントロールのインターフェイスへのポインター。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a> IAxWinHostWindow::CreateControl

コントロールを作成して初期化し、 *hWnd* で識別されるウィンドウでホストします。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*lpTricsData*<br/>
から作成するコントロールを識別する文字列。 には、CLSID (中かっこを含める必要があります)、ProgID、URL、または未加工の HTML (プレフィックスは **MSHTML:**) を指定できます。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
からコントロールの初期化データを格納しているストリームのインターフェイスポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このウィンドウは、このインターフェイスを公開するホストオブジェクトによってサブクラス化されます。これにより、メッセージがコントロールに反映され、その他のコンテナー機能が動作するようになります。

このメソッドを呼び出すことは、 [IAxWinHostWindow:: CreateControlEx](#createcontrolex)を呼び出すことと同じです。

ライセンスされた ActiveX コントロールを作成するには、「 [IAxWinHostWindowLic:: CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a> IAxWinHostWindow::CreateControlEx

[IAxWinHostWindow:: CreateControl](#createcontrol)と同様に、ActiveX コントロールを作成して初期化し、指定したウィンドウでホストします。

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>パラメーター

*lpTricsData*<br/>
から作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または未加工の HTML (プレフィックスは **MSHTML:**) にすることができます。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
からコントロールの初期化データを格納しているストリームのインターフェイスポインター。 NULL にすることができます。

*ppUnk*<br/>
入出力 `IUnknown` 作成されたコントロールのインターフェイスを受け取るポインターのアドレス。 NULL にすることができます。

*riidAdvise*<br/>
から含まれているオブジェクトの送信インターフェイスのインターフェイス識別子。 IID_NULL できます。

*punkAdvise*<br/>
から `IUnknown` によって指定された、格納されているオブジェクトのコネクションポイントに接続するシンクオブジェクトのインターフェイスへのポインター `iidSink` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

メソッドとは異なり `CreateControl` 、では、 `CreateControlEx` 新しく作成されたコントロールへのインターフェイスポインターを受け取り、コントロールによって発生するイベントを受け取るようにイベントシンクを設定することもできます。

ライセンスされた ActiveX コントロールを作成するには、「 [IAxWinHostWindowLic:: CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> IAxWinHostWindow:: QueryControl

ホストされるコントロールによって提供される、指定されたインターフェイスポインターを返します。

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
から要求されているコントロールのインターフェイスの ID。

*ppvObject*<br/>
入出力作成されたコントロールの指定されたインターフェイスを受け取るポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> IAxWinHostWindow:: SetExternalDispatch

外部ディスパッチインターフェイスを設定します。これは、 [IDocHostUIHandlerDispatch:: GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) メソッドを介して、含まれるコントロールで使用できます。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
からインターフェイスへのポインター `IDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> IAxWinHostWindow:: SetExternalUIHandler

この関数を呼び出して、オブジェクトの外部 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) インターフェイスを設定し `CAxWindow` ます。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
からインターフェイスへのポインター `IDocHostUIHandlerDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、ホストのサイトに対してインターフェイスを照会するコントロール (Web ブラウザーコントロールなど) によって使用され `IDocHostUIHandlerDispatch` ます。

## <a name="see-also"></a>関連項目

[IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
