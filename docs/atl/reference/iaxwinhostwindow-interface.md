---
title: インターフェイス
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
ms.openlocfilehash: ebecc611660a788ce59bb11beb95bd60eacaf01b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329993"
---
# <a name="iaxwinhostwindow-interface"></a>インターフェイス

このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[コントロールのアタッチ](#attachcontrol)|既存のコントロールをホスト オブジェクトにアタッチします。|
|[CreateControl](#createcontrol)|コントロールを作成し、ホスト オブジェクトにアタッチします。|
|[コントロールエックスを作成する](#createcontrolex)|コントロールを作成し、ホスト オブジェクトに接続し、必要に応じてイベント ハンドラーを設定します。|
|[クエリコントロール](#querycontrol)|ホストされたコントロールへのインターフェイス ポインターを返します。|
|[外部ディスパッチを設定します。](#setexternaldispatch)|外部`IDispatch`インターフェイスを設定します。|
|[外部UIハンドラを設定します。](#setexternaluihandler)|外部`IDocHostUIHandlerDispatch`インターフェイスを設定します。|

## <a name="remarks"></a>解説

このインターフェイスは、ATL の ActiveX コントロールホスト オブジェクトによって公開されます。 ホスト オブジェクトにコントロールを作成またはアタッチしたり、ホストされたコントロールからインターフェイスを取得したり、Web ブラウザーをホストするときに使用する外部の dispinterface または UI ハンドラーを設定したりするには、このインターフェイスのメソッドを呼び出します。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次に示すように、IDL または C++ として使用できます。

|[定義の種類]|ファイル|
|---------------------|----------|
|Idl|アトリフェイス.idl|
|C++|ATLIFace.h (ATLBase.h にも含まれています)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>ウィンドウ::コントロールをアタッチします。

*hWnd*で識別されるウィンドウを使用して、既存の (および以前に初期化された) コントロールをホスト オブジェクトにアタッチします。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*コントロールを確認する*<br/>
[in]ホスト オブジェクトに`IUnknown`アタッチされるコントロールのインターフェイスへのポインター。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>ウィンドウ::コントロールの作成

コントロールを作成し、初期化し *、hWnd*で識別されるウィンドウでホストします。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または生の HTML **(MSHTML:** の接頭辞) を指定できます。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このウィンドウは、メッセージをコントロールに反映できるように、このインターフェイスを公開するホスト オブジェクトによってサブクラス化され、他のコンテナー機能が機能します。

このメソッドを呼び出すことは、呼び出す[の](#createcontrolex)と同じです。

ライセンスを取得した ActiveX コントロールを作成するには[、「IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>ウィンドウ::コントロールエクスを作成します。

ActiveX コントロールを作成し、初期化し、指定したウィンドウで[ホストします。](#createcontrol)

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

*データ*<br/>
[in]作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または生の HTML (プレフィックスは**MSHTML:**) です。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

*ppUnk*<br/>
[アウト]作成されたコントロールのインターフェイスを`IUnknown`受け取るポインターのアドレス。 NULL にすることができます。

*リドアドバイス*<br/>
[in]含まれているオブジェクトの発信インターフェイスのインターフェイス識別子。 IID_NULLすることができます。

*パンクアドバイス*<br/>
[in]で`iidSink`指定された格納`IUnknown`されているオブジェクトの接続ポイントに接続されるシンク オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`CreateControl`メソッドとは異`CreateControlEx`なり、新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクを設定することもできます。

ライセンスを取得した ActiveX コントロールを作成するには[、「IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>ウィンドウ::クエリコントロール

ホストされたコントロールによって提供される指定されたインターフェイス ポインターを返します。

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
[in]要求されているコントロールのインターフェイスの ID。

*オブジェクト*<br/>
[アウト]作成されたコントロールの指定されたインターフェイスを受け取るポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>ウィンドウ::外部ディスパッチを設定します。

メソッドを通じて含まれるコントロールに使用できる外部ディスパッチ インターフェイス[を](../../atl/reference/idochostuihandlerdispatch-interface.md)設定します。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]`IDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>ウィンドウ::外部UIハンドラを設定します。

オブジェクトの外部[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)インターフェイスを設定するには、`CAxWindow`この関数を呼び出します。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]`IDocHostUIHandlerDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、ホストのサイトにインターフェイスを照会するコントロール (Web ブラウザー コントロールなど)`IDocHostUIHandlerDispatch`によって使用されます。

## <a name="see-also"></a>関連項目

[インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[ウィンドウ::クエリホスト](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
