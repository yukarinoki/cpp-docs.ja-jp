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
ms.openlocfilehash: 6f5629370bc1f821dac0a08cc76b5df1450f7a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318723"
---
# <a name="caxwindow-class"></a>CAxWindow クラス

このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAxWindow : public CWindow
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[コントロールのアタッチ](#attachcontrol)|既存の ActiveX コントロールをオブジェクト`CAxWindow`にアタッチします。|
|[アクスウィンドウ](#caxwindow)|`CAxWindow` オブジェクトを構築します。|
|[CreateControl](#createcontrol)|ActiveX コントロールを作成し、初期化し、ウィンドウでホストします`CAxWindow`。|
|[コントロールエックスを作成する](#createcontrolex)|ActiveX コントロールを作成し、コントロールからインターフェイス ポインターを取得します。|
|[クラス名](#getwndclassname)|(静的)オブジェクトの定義済みクラス名を`CAxWindow`取得します。|
|[クエリコントロール](#querycontrol)|ホストされた`IUnknown`ActiveX コントロールの を取得します。|
|[クエリホスト](#queryhost)|オブジェクトの`IUnknown`ポインターを`CAxWindow`取得します。|
|[外部ディスパッチを設定します。](#setexternaldispatch)|オブジェクトが使用する外部ディスパッチ インターフェイス`CAxWindow`を設定します。|
|[外部UIハンドラを設定します。](#setexternaluihandler)|オブジェクトが使用`IDocHostUIHandler`する外部インターフェイスを`CAxWindow`設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator_eq)|HWND を既存`CAxWindow`のオブジェクトに割り当てます。|

## <a name="remarks"></a>解説

このクラスには、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。 ホスティングは、 " **AtlAxWin80 "** によってラップされます`CAxWindow`。

クラス`CAxWindow`はクラスの特殊化として実装されます`CAxWindowT`。 この特殊化は、次のように宣言されています。

`typedef CAxWindowT<CWindow> CAxWindow;`

基本クラスを変更する必要がある場合は、新しい`CAxWindowT`基本クラスを使用して、テンプレート引数として指定できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a>コントロールをアタッチします。

ホスト オブジェクトがまだ存在しない場合は、新しいホスト オブジェクトを作成し、指定したコントロールをホストにアタッチします。

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
[in]コントロールの への`IUnknown`ポインター。

*コンテナを使用します。*<br/>
[アウト]ホスト (`AxWin`オブジェクト`IUnknown`) へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

を呼び出す`AttachControl`前に、アタッチされるコントロール オブジェクトを正しく初期化する必要があります。

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a>CAxウィンドウ::CAxウィンドウ

既存のウィンドウ`CAxWindow`オブジェクト ハンドルを使用してオブジェクトを構築します。

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウ オブジェクトへのハンドル。

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a>ウィンドウ::コントロールの作成

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

*名前を指定します。*<br/>
コントロールを作成する文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。 Windows モバイル プラットフォームでは、ProgID と CLSID のみがサポートされます。 Windows CE を組み込んだプラットフォームは、CE IE のサポートを備えた Windows モバイル以外では、ProgID、CLSID、URL、アクティブ ドキュメントへの参照、HTML のフラグメントなど、すべての種類をサポートします。

*pストリーム*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
[アウト]コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*ドヴレシド*<br/>
HTML リソースのリソース ID。 WebBrowser コントロールが作成され、指定されたリソースと共に読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドの 2 番目のバージョンを使用する場合は、HTML コントロールが作成され *、dwResID*で識別されるリソースにバインドされます。

このメソッドは、呼び出しと同じ結果を得られます。

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

ライセンスを取得した ActiveX コントロールを作成、初期化、およびホストするには[、CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`CreateControl`してください。

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a>CAxウィンドウ::コントロールエクスックスを作成します。

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

*名前を指定します。*<br/>
コントロールを作成する文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。 Windows モバイル プラットフォームでは、ProgID と CLSID のみがサポートされます。 Windows CE を組み込んだプラットフォームは、CE IE のサポートを備えた Windows モバイル以外では、ProgID、CLSID、URL、アクティブ ドキュメントへの参照、HTML のフラグメントなど、すべての種類をサポートします。

*pストリーム*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
[アウト]コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*コントロールを実行します。*<br/>
[アウト]コントロールを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*iidシンク*<br/>
[in]含まれているオブジェクトの発信インターフェイスのインターフェイス識別子。 IID_NULLすることができます。

*パンクシンク*<br/>
[in]*iidSink*`IUnknown`で指定された、含まれているオブジェクトの接続ポイントに接続されるシンク オブジェクトのインターフェイスへのポインター。

*ドヴレシド*<br/>
[in]HTML リソースのリソース ID。 WebBrowser コントロールが作成され、指定されたリソースと共に読み込まれます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメソッドは[CAxWindow::CreateControl](#createcontrol)に似ていますが、その`CreateControlEx`メソッドとは異なり、新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受け取るイベント シンクを設定することもできます。

ライセンスを取得した ActiveX コントロールを作成、初期化、およびホストするには[、CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`CreateControlEx`してください。

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a>ウィンドウ::ゲットウーンクラス名

ウィンドウ クラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

ライセンスを持たない ActiveX コントロールをホストできるウィンドウ クラスの名前を含む文字列へのポインター。

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a>CAx ウィンドウ::演算子 =

HWND を既存`CAxWindow`のオブジェクトに割り当てます。

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

現在の `CAxWindow` オブジェクトへの参照を返します。

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a>ウィンドウ::クエリコントロール

ホストされたコントロールの指定されたインターフェイスを取得します。

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]コントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
[アウト]コントロールのインターフェイスへのポインター。 このメソッドのテンプレート バージョンでは、UUID に関連付けられた型指定されたインターフェイスが渡される限り、参照 ID は必要ありません。

*Q*<br/>
[in]照会対象のインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a>ウィンドウ::クエリホスト

ホストの指定されたインターフェイスを返します。

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]コントロールのインターフェイスの IID を指定します。

*ppUnk*<br/>
[アウト]ホスト上のインターフェイスへのポインター。 このメソッドのテンプレート バージョンでは、UUID に関連付けられた型指定されたインターフェイスが渡される限り、参照 ID は必要ありません。

*Q*<br/>
[in]照会対象のインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ホストのインターフェイスを使用すると、 によって`AxWin`実装されるウィンドウ ホスティング コードの基になる機能にアクセスできます。

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>ウィンドウ::外部ディスパッチを設定します。

オブジェクトの外部ディスパッチ インターフェイスを`CAxWindow`設定します。

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]`IDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>ウィンドウ::外部UIハンドラを設定します。

オブジェクトの外部[IDocHostUIHandler ディスパッチ](../../atl/reference/idochostuihandlerdispatch-interface.md)`CAxWindow`インターフェイスを設定します。

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>パラメーター

*pUIハンドラ*<br/>
[in]`IDocHostUIHandlerDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

外部`IDocHostUIHandlerDispatch`インターフェイスは、ホストのサイトにインターフェイスを照会するコントロールによって使用されます`IDocHostUIHandlerDispatch`。 WebBrowser コントロールは、これを行う 1 つのコントロールです。

## <a name="see-also"></a>関連項目

[ATLCON サンプル](../../overview/visual-cpp-samples.md)<br/>
[Cウィンドウクラス](../../atl/reference/cwindow-class.md)<br/>
[複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロール コンテインメント : Q &amp; A 集](../../atl/atl-control-containment-faq.md)
