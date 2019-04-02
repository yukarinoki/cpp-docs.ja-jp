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
ms.openlocfilehash: 33c5b48c88a6fc7a4ed18a93e874d318a16a20dd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775440"
---
# <a name="caxwindow-class"></a>CAxWindow クラス

このクラスは、ActiveX コントロールをホスト ウィンドウを操作するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAxWindow : public CWindow
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AttachControl](#attachcontrol)|アタッチに既存の ActiveX コントロール、`CAxWindow`オブジェクト。|
|[CAxWindow](#caxwindow)|`CAxWindow` オブジェクトを構築します。|
|[CreateControl](#createcontrol)|ActiveX コントロールを作成しを初期化し、ホストで、`CAxWindow`ウィンドウ。|
|[CreateControlEx](#createcontrolex)|ActiveX コントロールを作成し、コントロールからインターフェイス ポインターを (またはポインター) を取得します。|
|[GetWndClassName](#getwndclassname)|(静的)定義済みのクラスの名前を取得、`CAxWindow`オブジェクト。|
|[QueryControl](#querycontrol)|取得、`IUnknown`ホストされている ActiveX コントロールの。|
|[QueryHost](#queryhost)|取得、`IUnknown`のポインター、`CAxWindow`オブジェクト。|
|[SetExternalDispatch](#setexternaldispatch)|によって使用される外部のディスパッチ インターフェイスの設定、`CAxWindow`オブジェクト。|
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定`IDocHostUIHandler`インターフェイスで使用される、`CAxWindow`オブジェクト。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](#operator_eq)|既存の HWND を割り当てます`CAxWindow`オブジェクト。|

## <a name="remarks"></a>Remarks

このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 によって提供されるホスティング" **AtlAxWin80"**、によってラップされる`CAxWindow`します。

クラス`CAxWindow`の特殊化として実装されます、`CAxWindowT`クラス。 この特殊化は、としてを宣言されます。

`typedef CAxWindowT<CWindow> CAxWindow;`

使用することができます、基底クラスを変更する必要がある場合`CAxWindowT`し、テンプレート引数として新しい基本クラスを指定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

##  <a name="attachcontrol"></a>  CAxWindow::AttachControl

既に存在しないと、ホストに指定したコントロールをアタッチします。 1 つである場合は、新しいホスト オブジェクトを作成します。

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
[in]ポインター、`IUnknown`のコントロール。

*ppUnkContainer*<br/>
[out]ポインター、`IUnknown`ホストの (、`AxWin`オブジェクト)。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

アタッチされるコントロール オブジェクトを呼び出す前に正しく初期化する必要があります`AttachControl`します。

##  <a name="caxwindow"></a>  CAxWindow::CAxWindow

構築、`CAxWindow`既存ウィンドウ オブジェクトのハンドルを使用するオブジェクトします。

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウ オブジェクトへのハンドル。

##  <a name="createcontrol"></a>  CAxWindow::CreateControl

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
コントロールを作成する文字列へのポインター。 次の方法のいずれかで書式設定する必要があります。

- "MSCAL などを ProgID。Calendar.7"

- "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID

- などの URL"<http://www.microsoft.com>"

- A reference to an Active document such as "file://\\\Documents\MyDoc.doc"

- などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:"、MSHTML ストリームとして指定されているように、HTML フラグメントを付ける必要があります。 ProgID と CLSID は、Windows Mobile プラットフォームでサポートされます。 Windows CE の組み込みのプラットフォーム、CE IE サポート対応の Windows Mobile 以外、ProgID を含むすべての型 CLSID、URL、参照にアクティブなドキュメント、および HTML のフラグメント。

*pStream*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
[out]受信するポインターのアドレス、`IUnknown`のコンテナー。 NULL にすることができます。

*dwResID*<br/>
HTML リソースのリソース ID。 WebBrowser コントロールが作成され、指定されたリソースで読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

このメソッドの 2 番目のバージョンを使用する場合、HTML コントロールが作成されで識別されるリソースにバインドされている*され*します。

この方法では、呼び出すことと同じ結果を使用します。

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

参照してください[CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic)を作成するには、初期化、およびライセンスされた ActiveX コントロールをホストします。

### <a name="example"></a>例

参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CreateControl`します。

##  <a name="createcontrolex"></a>  CAxWindow::CreateControlEx

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
コントロールを作成する文字列へのポインター。 次の方法のいずれかで書式設定する必要があります。

- "MSCAL などを ProgID。Calendar.7"

- "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID

- などの URL"<http://www.microsoft.com>"

- A reference to an Active document such as "file://\\\Documents\MyDoc.doc"

- などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:"、MSHTML ストリームとして指定されているように、HTML フラグメントを付ける必要があります。 ProgID と CLSID は、Windows Mobile プラットフォームでサポートされます。 Windows CE の組み込みのプラットフォーム、CE IE サポート対応の Windows Mobile 以外、ProgID を含むすべての型 CLSID、URL、参照にアクティブなドキュメント、および HTML のフラグメント。

*pStream*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
[out]受信するポインターのアドレス、`IUnknown`のコンテナー。 NULL にすることができます。

*ppUnkControl*<br/>
[out]受信するポインターのアドレス、`IUnknown`のコントロール。 NULL にすることができます。

*れて*<br/>
[in]送信のインターフェイスに含まれるオブジェクトのインターフェイスの識別子です。 Iid_ をすることができます。

*punkSink*<br/>
[in]ポインター、`IUnknown`で指定された、含まれるオブジェクトの接続ポイントに接続されているシンク オブジェクトのインターフェイス*れて*します。

*dwResID*<br/>
[in]HTML リソースのリソース ID。 WebBrowser コントロールが作成され、指定されたリソースで読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

このメソッドは[については](#createcontrol)、しかし、そのメソッドとは異なり`CreateControlEx`新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するために、イベント シンクをセットアップすることもできます。

参照してください[CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex)を作成するには、初期化、およびライセンスされた ActiveX コントロールをホストします。

### <a name="example"></a>例

参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CreateControlEx`します。

##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName

ウィンドウ クラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

ない ActiveX コントロールをホストできるウィンドウ クラスの名前を含む文字列へのポインター。

##  <a name="operator_eq"></a>  CAxWindow::operator =

既存の HWND を割り当てます`CAxWindow`オブジェクト。

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

現在の `CAxWindow` オブジェクトへの参照を返します。

##  <a name="querycontrol"></a>  CAxWindow::QueryControl

ホストされるコントロールの指定したインターフェイスを取得します。

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]コントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
[out]コントロールのインターフェイスへのポインター。 このメソッドのテンプレート バージョンで必要はありません参照 id 関連の UUID で型指定されたインターフェイスが渡される限りです。

*Q*<br/>
[in]インターフェイスのクエリが対象です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="queryhost"></a>  CAxWindow::QueryHost

ホストの指定したインターフェイスを返します。

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]コントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
[out]ホスト上のインターフェイスへのポインター。 このメソッドのテンプレート バージョンで必要はありません参照 id 関連の UUID で型指定されたインターフェイスが渡される限りです。

*Q*<br/>
[in]インターフェイスのクエリが対象です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ホストのインターフェイスによって実装される、ホストするウィンドウのコードの基になる機能へのアクセスを許可する`AxWin`します。

##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch

外部のディスパッチ インターフェイスの設定、`CAxWindow`オブジェクト。

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]ポインター、`IDispatch`インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler

外部の設定[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>パラメーター

*pUIHandler*<br/>
[in]ポインター、`IDocHostUIHandlerDispatch`インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

外部`IDocHostUIHandlerDispatch`インターフェイスは、ホストのサイト コントロールによって使用、`IDocHostUIHandlerDispatch`インターフェイス。 WebBrowser コントロールは、これは 1 つのコントロールです。

## <a name="see-also"></a>関連項目

[ATLCON サンプル](../../overview/visual-cpp-samples.md)<br/>
[CWindow クラス](../../atl/reference/cwindow-class.md)<br/>
[複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロール コンテインメント:](../../atl/atl-control-containment-faq.md)
