---
title: CAxWindow クラス
ms.date: 11/04/2016
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 1301baef874ac4e482a1b2a7f0a2ee6b1b63396f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833830"
---
# <a name="caxwindow-class"></a>CAxWindow クラス

このクラスには、ActiveX コントロールをホストしているウィンドウを操作するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAxWindow : public CWindow
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|関数|説明|
|-|-|
|[AttachControl](#attachcontrol)|既存の ActiveX コントロールをオブジェクトにアタッチ `CAxWindow` します。|
|[CAxWindow](#caxwindow)|`CAxWindow` オブジェクトを構築します。|
|[CreateControl](#createcontrol)|ActiveX コントロールを作成して初期化し、ウィンドウでホストし `CAxWindow` ます。|
|[CreateControlEx](#createcontrolex)|ActiveX コントロールを作成し、コントロールからインターフェイスポインター (またはポインター) を取得します。|
|[GetWndClassName](#getwndclassname)|雑音オブジェクトの定義済みのクラス名を取得し `CAxWindow` ます。|
|[QueryControl](#querycontrol)|ホストされている `IUnknown` ActiveX コントロールのを取得します。|
|[QueryHost](#queryhost)|`IUnknown`オブジェクトのポインターを取得し `CAxWindow` ます。|
|[SetExternalDispatch](#setexternaldispatch)|オブジェクトによって使用される外部ディスパッチインターフェイスを設定し `CAxWindow` ます。|
|[SetExternalUIHandler](#setexternaluihandler)|`IDocHostUIHandler`オブジェクトによって使用される外部インターフェイスを設定し `CAxWindow` ます。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator =](#operator_eq)|HWND を既存のオブジェクトに割り当て `CAxWindow` ます。|

## <a name="remarks"></a>解説

このクラスには、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。 ホスティングは、によってラップされる " **AtlAxWin80"** によって提供され `CAxWindow` ます。

クラス `CAxWindow` は、クラスの特殊化として実装され `CAxWindowT` ます。 この特殊化は次のように宣言されます。

`typedef CAxWindowT<CWindow> CAxWindow;`

基底クラスを変更する必要がある場合は、を使用して、 `CAxWindowT` 新しい基底クラスをテンプレート引数として指定できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a> CAxWindow:: AttachControl

新しいホストオブジェクトがまだ存在しない場合は作成し、指定したコントロールをホストにアタッチします。

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
からコントロールのへのポインター `IUnknown` 。

*ppUnkContainer*<br/>
入出力 `IUnknown` ホスト (オブジェクト) のへのポインター `AxWin` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

を呼び出す前に、アタッチされるコントロールオブジェクトが正しく初期化されている必要があり `AttachControl` ます。

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a> CAxWindow::CAxWindow

既存の `CAxWindow` ウィンドウオブジェクトハンドルを使用してオブジェクトを構築します。

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウオブジェクトを表すハンドル。

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a> CAxWindow::CreateControl

ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。

```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
コントロールを作成する文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- などの ProgID。 `"MSCAL.Calendar.7"`

- などの CLSID `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- のような URL `"<https://www.microsoft.com>"`

- などのアクティブなドキュメントへの参照 `"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント (など) `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に配置する必要があります。 Windows Mobile プラットフォームでは、ProgID と CLSID のみがサポートされています。 CE IE がサポートされている Windows Mobile 以外の Windows CE embedded プラットフォームでは、ProgID、CLSID、URL、active ドキュメントへの参照、HTML のフラグメントを含むすべての型がサポートされます。

*pStream*<br/>
からコントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
入出力コンテナーのを受け取るポインターのアドレス `IUnknown` 。 NULL にすることができます。

*dwResID*<br/>
HTML リソースのリソース ID。 指定したリソースを使用して、WebBrowser コントロールが作成され、読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドの2番目のバージョンを使用すると、HTML コントロールが作成され、 *dwResID*によって識別されるリソースにバインドされます。

このメソッドでは、を呼び出した場合と同じ結果が得られます。

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

ライセンスされた ActiveX コントロールを作成、初期化、およびホストする方法については、「 [CAxWindow2T:: CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) 」を参照してください `CreateControl` 。

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a> CAxWindow::CreateControlEx

ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。

```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
コントロールを作成する文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- などの ProgID。 `"MSCAL.Calendar.7"`

- などの CLSID `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- のような URL `"<https://www.microsoft.com>"`

- などのアクティブなドキュメントへの参照 `"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント (など) `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に配置する必要があります。 Windows Mobile プラットフォームでは、ProgID と CLSID のみがサポートされています。 CE IE がサポートされている Windows Mobile 以外の Windows CE embedded プラットフォームでは、ProgID、CLSID、URL、active ドキュメントへの参照、HTML のフラグメントを含むすべての型がサポートされます。

*pStream*<br/>
からコントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
入出力コンテナーのを受け取るポインターのアドレス `IUnknown` 。 NULL にすることができます。

*ppUnkControl*<br/>
入出力コントロールのを受け取るポインターのアドレス `IUnknown` 。 NULL にすることができます。

*iidSink*<br/>
から含まれているオブジェクトの送信インターフェイスのインターフェイス識別子。 IID_NULL できます。

*punkSink*<br/>
から `IUnknown` *Iidsink*によって指定された、格納されているオブジェクトのコネクションポイントに接続するシンクオブジェクトのインターフェイスへのポインター。

*dwResID*<br/>
からHTML リソースのリソース ID。 指定したリソースを使用して、WebBrowser コントロールが作成され、読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドは [CAxWindow:: CreateControl](#createcontrol)に似ていますが、そのメソッドとは異なり、 `CreateControlEx` 新しく作成されたコントロールへのインターフェイスポインターを受け取り、コントロールによって発生するイベントを受け取るようにイベントシンクを設定することもできます。

ライセンスされた ActiveX コントロールを作成、初期化、およびホストする方法については、「 [CAxWindow2T:: CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) 」を参照してください `CreateControlEx` 。

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a> CAxWindow::GetWndClassName

ウィンドウクラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

Nonlicensed ActiveX コントロールをホストできるウィンドウクラスの名前を格納している文字列へのポインター。

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a> CAxWindow:: operator =

HWND を既存のオブジェクトに割り当て `CAxWindow` ます。

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウを処理するハンドル。

### <a name="return-value"></a>戻り値

現在の `CAxWindow` オブジェクトへの参照を返します。

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a> CAxWindow:: QueryControl

ホストされているコントロールの指定したインターフェイスを取得します。

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からコントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
入出力コントロールのインターフェイスへのポインター。 このメソッドのテンプレートバージョンでは、関連付けられている UUID を持つ型指定されたインターフェイスが渡される限り、参照 ID は必要ありません。

*Q.*<br/>
から照会されているインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a> CAxWindow:: QueryHost

ホストの指定されたインターフェイスを返します。

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からコントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
入出力ホスト上のインターフェイスへのポインター。 このメソッドのテンプレートバージョンでは、関連付けられている UUID を持つ型指定されたインターフェイスが渡される限り、参照 ID は必要ありません。

*Q.*<br/>
から照会されているインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ホストのインターフェイスを使用すると、によって実装されるウィンドウホストコードの基になる機能にアクセスでき `AxWin` ます。

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> CAxWindow:: SetExternalDispatch

オブジェクトの外部ディスパッチインターフェイスを設定し `CAxWindow` ます。

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
からインターフェイスへのポインター `IDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> CAxWindow:: SetExternalUIHandler

オブジェクトの外部 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) インターフェイスを設定し `CAxWindow` ます。

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>パラメーター

*pUIHandler*<br/>
からインターフェイスへのポインター `IDocHostUIHandlerDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

外部 `IDocHostUIHandlerDispatch` インターフェイスは、ホストのサイトにインターフェイスのクエリを実行するコントロールによって使用され `IDocHostUIHandlerDispatch` ます。 WebBrowser コントロールは、これを行う1つのコントロールです。

## <a name="see-also"></a>関連項目

[ATLCON サンプル](../../overview/visual-cpp-samples.md)<br/>
[CWindow クラス](../../atl/reference/cwindow-class.md)<br/>
[複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロール コンテインメント : Q &amp; A 集](../../atl/atl-control-containment-faq.md)
