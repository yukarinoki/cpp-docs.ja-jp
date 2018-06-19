---
title: CAxWindow クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 052e7ad2bfa8cc03c4eadd4926dbd84c4fd60223
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364318"
---
# <a name="caxwindow-class"></a>CAxWindow クラス
このクラスは、ActiveX コントロールをホストしているウィンドウを操作するためのメソッドを提供します。  
  
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
|[関連付け](#attachcontrol)|アタッチに既存の ActiveX コントロール、`CAxWindow`オブジェクト。|  
|[CAxWindow](#caxwindow)|`CAxWindow` オブジェクトを構築します。|  
|[CreateControl](#createcontrol)|ActiveX コントロールを作成し、初期化でホストして、`CAxWindow`ウィンドウです。|  
|[CreateControlEx](#createcontrolex)|ActiveX コントロールを作成し、コントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[GetWndClassName](#getwndclassname)|(静的)定義済みのクラス名を取得、`CAxWindow`オブジェクト。|  
|[QueryControl](#querycontrol)|取得、 **IUnknown**ホストされている ActiveX コントロールのです。|  
|[QueryHost](#queryhost)|取得、 **IUnknown**のポインター、`CAxWindow`オブジェクト。|  
|[SetExternalDispatch](#setexternaldispatch)|によって使用される外部ディスパッチ インターフェイスの設定、`CAxWindow`オブジェクト。|  
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定**IDocHostUIHandler**インターフェイスで使用される、`CAxWindow`オブジェクト。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|割り当てます、 **HWND**既存**CAxWindow**オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 によって提供されるホスティング" **AtlAxWin80"**、によってラップされている`CAxWindow`です。  
  
 クラス`CAxWindow`を特化したクラスとして実装されて、`CAxWindowT`クラスです。 この特殊化は、としてを宣言されます。  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 使用することができます、基本クラスを変更する必要がある場合`CAxWindowT`し、テンプレート引数として新しい基本クラスを指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="attachcontrol"></a>  CAxWindow::AttachControl  
 いずれかが既に存在しないし、指定したコントロールをホストにアタッチする場合は、新しいホスト オブジェクトを作成します。  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 [in]ポインター、 **IUnknown**コントロールのです。  
  
 `ppUnkContainer`  
 [out]ポインター、 **IUnknown**ホストの (、 **AxWin**オブジェクト)。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 アタッチされるコントロール オブジェクトを呼び出す前に正しく初期化する必要があります`AttachControl`です。  
  
##  <a name="caxwindow"></a>  CAxWindow::CAxWindow  
 構築、`CAxWindow`オブジェクト既存ウィンドウ オブジェクトのハンドルを使用します。  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 ウィンドウの既存のオブジェクトへのハンドル。  
  
##  <a name="createcontrol"></a>  については  
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
 `lpszName`  
 コントロールを作成する文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。 ProgID と CLSID は、Windows Mobile プラットフォームでサポートされます。 プラットフォームが Windows CE に埋め込まれている、以外のサポートが CE IE サポート Windows Mobile ProgID を含むすべての型の CLSID、URL への参照をアクティブなドキュメント、および HTML のフラグメント。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 [out]受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
 `dwResID`  
 HTML リソースのリソース ID です。 WebBrowser コントロールが作成され、指定されたリソースを使用して読み込まです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドの 2 番目のバージョンを使用する場合、HTML コントロールが作成されで識別されるリソースにバインドされている`dwResID`です。  
  
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
 `lpszName`  
 コントロールを作成する文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。 ProgID と CLSID は、Windows Mobile プラットフォームでサポートされます。 プラットフォームが Windows CE に埋め込まれている、以外のサポートが CE IE サポート Windows Mobile ProgID を含むすべての型の CLSID、URL への参照をアクティブなドキュメント、および HTML のフラグメント。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 [out]受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
 `ppUnkControl`  
 [out]受信するポインターのアドレス、 **IUnknown**コントロールのです。 指定できます**NULL**です。  
  
 `iidSink`  
 [in]含まれるオブジェクト上の発信インターフェイスのインターフェイスの識別子です。 指定できます**iid_ に**です。  
  
 *punkSink*  
 [in]ポインター、 **IUnknown**で指定されたコンテナー内のオブジェクトの接続ポイントに接続するシンク オブジェクトのインターフェイス`iidSink`です。  
  
 `dwResID`  
 [in]HTML リソースのリソース ID です。 WebBrowser コントロールが作成され、指定されたリソースを使用して読み込まです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドはのような[については](#createcontrol)、このメソッドとは異なり`CreateControlEx`を新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
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
 割り当てます、`HWND`既存`CAxWindow`オブジェクト。  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 現在の `CAxWindow` オブジェクトへの参照を返します。  
  
##  <a name="querycontrol"></a>  CAxWindow::QueryControl  
 ホストされるコントロールの指定されたインターフェイスを取得します。  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コントロールのインターフェイスの IID を指定します。  
  
 `ppUnk`  
 [out]コントロールのインターフェイスへのポインター。 このメソッドのテンプレート バージョンで必要はありません参照 ID に対して、関連付けられている UUID と型指定されたインターフェイスが渡される限り、します。  
  
 `Q`  
 [in]このインターフェイスはクエリが実行されるためです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="queryhost"></a>  CAxWindow::QueryHost  
 ホストの指定したインターフェイスを返します。  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コントロールのインターフェイスの IID を指定します。  
  
 `ppUnk`  
 [out]ホスト上のインターフェイスへのポインター。 このメソッドのテンプレート バージョンで必要はありません参照 ID に対して、関連付けられている UUID と型指定されたインターフェイスが渡される限り、します。  
  
 `Q`  
 [in]このインターフェイスはクエリが実行されるためです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ホストのインターフェイスによって実装されるウィンドウ ホスティング コードの基になる機能へのアクセスを許可する**AxWin**です。  
  
##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch  
 外部のディスパッチ インターフェイスを設定、`CAxWindow`オブジェクト。  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler  
 外部の設定[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUIHandler*  
 [in]ポインター、 **IDocHostUIHandlerDispatch**インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 外部`IDocHostUIHandlerDispatch`インターフェイスが、ホストのサイト コントロールで使用される、`IDocHostUIHandlerDispatch`インターフェイスです。 WebBrowser コントロールは、これを行う 1 つのコントロールです。  
  
## <a name="see-also"></a>関連項目  
 [ATLCON サンプル](../../visual-cpp-samples.md)   
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [コントロール コンテインメントよく寄せられる質問](../../atl/atl-control-containment-faq.md)

