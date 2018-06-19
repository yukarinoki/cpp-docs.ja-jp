---
title: IAxWinHostWindow インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1d0d41439748cd0ddbc981ecb1d74194d5fbd59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365127"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow インターフェイス
このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[関連付け](#attachcontrol)|既存のコントロールをそのホスト オブジェクトにアタッチします。|  
|[CreateControl](#createcontrol)|コントロールを作成し、そのホスト オブジェクトを結び付けます。|  
|[CreateControlEx](#createcontrolex)|コントロールを作成、ホスト オブジェクトにアタッチし、必要に応じて、イベント ハンドラーを設定します。|  
|[QueryControl](#querycontrol)|ホストされるコントロールのインターフェイス ポインターを返します。|  
|[SetExternalDispatch](#setexternaldispatch)|外部の設定`IDispatch`インターフェイスです。|  
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定`IDocHostUIHandlerDispatch`インターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、ATL の ActiveX コントロールをホストしているオブジェクトによって公開されます。 作成または、そのホスト オブジェクトをホストされるコントロールからインターフェイスを取得するか、Web ブラウザーをホストする場合に、外部のディスパッチ インターフェイスまたは使用するための UI ハンドラーを設定するにはコントロールを追加するには、このインターフェイスでメソッドを呼び出します。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のように idl ファイルまたは C++ として使用できます。  
  
|定義の型|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl  
 識別されるウィンドウを使用して、そのホスト オブジェクトを既存の (および前に初期化された) のコントロールを結び付けます`hWnd`です。  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkControl*  
 [in]ポインター、 **IUnknown**そのホスト オブジェクトにアタッチされているコントロールのインターフェイスです。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="createcontrol"></a>  については  
 コントロールを作成し、初期化してによって識別されるウィンドウでホスト`hWnd`です。  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML を指定できます (付きます**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このウィンドウは、メッセージがコントロールに反映させることができ、その他のコンテナーの機能が動作できるように、このインターフェイスを公開する、そのホスト オブジェクトをサブクラス化されます。  
  
 このメソッドの呼び出しは呼び出すことと同じ[詳細](#createcontrolex)です。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)です。  
  
##  <a name="createcontrolex"></a>  詳細  
 ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[については](#createcontrol)します。  
  
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
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML を指定できます (付いて**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 指定できます**NULL**です。  
  
 `ppUnk`  
 [out]受信するポインターのアドレス、 **IUnknown**に作成されたコントロールのインターフェイスです。 指定できます**NULL**です。  
  
 *riidAdvise*  
 [in]含まれるオブジェクト上の発信インターフェイスのインターフェイスの識別子です。 指定できます**iid_ に**です。  
  
 *punkAdvise*  
 [in]ポインター、 **IUnknown**で指定されたコンテナー内のオブジェクトの接続ポイントに接続するシンク オブジェクトのインターフェイス`iidSink`です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 異なり、`CreateControl`メソッド、`CreateControlEx`を新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[呼び出し](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)です。  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 ホストされるコントロールによって提供される、指定されたインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]要求されているコントロールのインターフェイスの ID。  
  
 `ppvObject`  
 [out]作成されたコントロールの指定されたインターフェイスを受信するポインターのアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 を通じて、含まれているコントロールがある外部のディスパッチ インターフェイスの設定、 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md)メソッドです。  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
 外部を設定するには、この関数を呼び出す[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、 **IDocHostUIHandlerDispatch**インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 この関数が、ホストのサイト (Web ブラウザー コントロールで) などのコントロールで使用される、`IDocHostUIHandlerDispatch`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









