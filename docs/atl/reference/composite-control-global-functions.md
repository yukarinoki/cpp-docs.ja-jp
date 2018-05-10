---
title: 複合コントロールのグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c62d5056f28460644084296598ae865c6ff5f48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="composite-control-global-functions"></a>複合コントロールのグローバル関数
これらの関数は、ダイアログ ボックスを作成および作成、ホスト、および ActiveX コントロールのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[AtlAxAttachControl](#atlaxattachcontrol)|事前に作成されたコントロールを指定されたウィンドウにアタッチします。|  
|[AtlAxGetHost](#atlaxgethost)|(存在する場合) は、指定したウィンドウ、コンテナーへのダイレクト インターフェイス ポインターを取得するために使用、ハンドルを指定します。|  
|[AtlAxGetControl](#atlaxgetcontrol)|指定のウィンドウ (存在する場合)、内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得するために使用、ハンドルを指定します。|  
|[AtlSetChildSite](#atlsetchildsite)|初期化、 **IUnknown**子サイトのです。|  
|[AtlAxWinInit](#atlaxwininit)|AxWin オブジェクトのホスティング コードを初期化します。|  
|[AtlAxWinTerm](#atlaxwinterm)|AxWin オブジェクトのホスティング コードを非初期化します。|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|オブジェクトの既定のソース インターフェイスに関する情報を返します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlhost.h  

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox  
 ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 [in]実行可能ファイルには、ダイアログ ボックスのテンプレートが含まれるモジュールのインスタンスを識別します。  
  
 `lpTemplateName`  
 [in]ダイアログ ボックスのテンプレートを識別します。 このパラメーターは、ダイアログ ボックスのテンプレートの名前を指定する null で終わる文字列へのポインターまたはダイアログ ボックスのテンプレートのリソース識別子を指定する整数値。 パラメーターは、リソースの識別子を指定する場合は、その上位ワードを 0 にする必要があり、その下位ワードは、識別子を含める必要があります。 使用することができます、[されるときは](http://msdn.microsoft.com/library/windows/desktop/ms648029)マクロをこの値を作成します。  
  
 `hWndParent`  
 [in]ダイアログ ボックスを所有しているウィンドウを識別します。  
  
 `lpDialogProc`  
 [in]ダイアログ ボックス プロシージャへのポインター。 ダイアログ ボックス プロシージャの詳細については、次を参照してください。 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)です。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定します、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージ。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 使用する**AtlAxDialogBox** 、ActiveX コントロールを含むダイアログ テンプレートで指定する有効な**CLSID**、 **APPID**または URL 文字列として、*テキスト*のフィールド、**コントロール**として"AtlAxWin80"と共に、ダイアログ リソースのセクションで、*クラス名*同じセクションの下にあるフィールドです。 次にどのような有効な示します**コントロール**セクションのようになります。  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 リソース スクリプトの編集の詳細については、次を参照してください。[する方法: テキスト形式でリソース スクリプト ファイルを開く](../../windows/how-to-open-a-resource-script-file-in-text-format.md)です。 コントロールのリソース定義ステートメントの詳細については、次を参照してください。[共通管理パラメーター](http://msdn.microsoft.com/library/windows/desktop/aa380902) Windows SDK で *: SDK ツール*です。  
  
 [全般] ダイアログ ボックスの詳細についてを参照してください[ ダイアログ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms645452)と[CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) Windows SDK に含まれています。  
  
##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog  
 ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 [in]実行可能ファイルには、ダイアログ ボックスのテンプレートが含まれるモジュールのインスタンスを識別します。  
  
 `lpTemplateName`  
 [in]ダイアログ ボックスのテンプレートを識別します。 このパラメーターは、ダイアログ ボックスのテンプレートの名前を指定する null で終わる文字列へのポインターまたはダイアログ ボックスのテンプレートのリソース識別子を指定する整数値。 パラメーターは、リソースの識別子を指定する場合は、その上位ワードを 0 にする必要があり、その下位ワードは、識別子を含める必要があります。 使用することができます、[されるときは](http://msdn.microsoft.com/library/windows/desktop/ms648029)マクロをこの値を作成します。  
  
 `hWndParent`  
 [in]ダイアログ ボックスを所有しているウィンドウを識別します。  
  
 `lpDialogProc`  
 [in]ダイアログ ボックス プロシージャへのポインター。 ダイアログ ボックス プロシージャの詳細については、次を参照してください。 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)です。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定します、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージ。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。  
  
 参照してください[CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434)と[CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) Windows SDK にします。  
  
##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。  
  
 `hWnd`  
 [in]コントロールが接続されているウィンドウのハンドルします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 [out]受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 このグローバル関数が呼び出すことと同じ結果を使用する[行うに](#atlaxcreatecontrolex)( `lpszName` **、** `hWnd` **、** `pStream` **、NULL、NULL、NULL、NULL** );。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[して](#atlaxcreatecontrollic)です。  
  
##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。 新しいコントロールのインターフェイス ポインターとイベント シンクも作成されます。  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。  
  
 `hWnd`  
 [in]コントロールが接続されているウィンドウのハンドルします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 [out]受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
 `ppUnkControl`  
 [out]受信するポインターのアドレス、 **IUnknown**に作成されたコントロールのです。 指定できます**NULL**です。  
  
 `iidSink`  
 含まれるオブジェクト上の発信インターフェイスのインターフェイスの識別子です。  
  
 *punkSink*  
 ポインター、 **IUnknown**で指定された接続ポイントに接続するシンク オブジェクトのインターフェイス`iidSink`含まれているオブジェクトが含まれているオブジェクトが作成された後にします。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 `AtlAxCreateControlEx` ような[して](#atlaxcreatecontrol)を新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできますが、します。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)です。  
  
##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。  
  
 `hWnd`  
 コントロールが接続されているウィンドウのハンドルします。  
  
 `pStream`  
 コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
 `bstrLic`  
 コントロールのライセンスを含む BSTR。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)の使用方法のサンプルについては`AtlAxCreateControlLic`します。  
  
##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。 新しいコントロールのインターフェイス ポインターとイベント シンクも作成されます。  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットする必要があります。  
  
-   "MSCAL などを ProgID。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   などの URL"http://www.microsoft.com"  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、html を付ける必要があります。  
  
 `hWnd`  
 コントロールが接続されているウィンドウのハンドルします。  
  
 `pStream`  
 コントロールのプロパティを初期化するために使用されるストリームへのポインター。 指定できます**NULL**です。  
  
 `ppUnkContainer`  
 受信するポインターのアドレス、 **IUnknown**のコンテナーです。 指定できます**NULL**です。  
  
 `ppUnkControl`  
 [out]受信するポインターのアドレス、 **IUnknown**に作成されたコントロールのです。 指定できます**NULL**です。  
  
 `iidSink`  
 含まれるオブジェクト上の発信インターフェイスのインターフェイスの識別子です。  
  
 *punkSink*  
 ポインター、 **IUnknown**で指定された接続ポイントに接続するシンク オブジェクトのインターフェイス`iidSink`含まれているオブジェクトが含まれているオブジェクトが作成された後にします。  
  
 `bstrLic`  
 コントロールのライセンスを含む BSTR。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 `AtlAxCreateControlLicEx` ような[して](#atlaxcreatecontrollic)を新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできますが、します。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)の使用方法のサンプルについては`AtlAxCreateControlLicEx`します。  
  
##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl  
 事前に作成されたコントロールを指定されたウィンドウにアタッチします。  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 [in]ポインター、 **IUnknown**コントロールのです。  
  
 `hWnd`  
 [in]コントロールをホスト ウィンドウへのハンドルします。  
  
 `ppUnkContainer`  
 [out]ポインターへのポインター、 **IUnknown**コンテナー オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 使用して[行うに](#atlaxcreatecontrolex)と[して](#atlaxcreatecontrol)を同時に作成し、コントロールを追加します。  
  
> [!NOTE]
>  アタッチされるコントロール オブジェクトを呼び出す前に正しく初期化する必要があります`AtlAxAttachControl`です。  
  
##  <a name="atlaxgethost"></a>  AtlAxGetHost  
 ハンドルが与えられた指定のウィンドウに対するコンテナーへのダイレクト インターフェイス ポインターを取得します。  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 [in]コントロールをホストしているウィンドウへのハンドル。  
  
 `pp`  
 [out]**IUnknown**のコントロールのコンテナーです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl  
 ハンドルが与えられた指定のウィンドウ内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得します。  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 [in]コントロールをホストしているウィンドウへのハンドル。  
  
 `pp`  
 [out]**IUnknown**ホストされるコントロールのです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="atlsetchildsite"></a>  AtlSetChildSite  
 子オブジェクトのサイトを設定するには、この関数を呼び出す、 **IUnknown**の親オブジェクトです。  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *punkChild*  
 [in]ポインター、 **IUnknown**子のインターフェイスです。  
  
 `punkParent`  
 [in]ポインター、 **IUnknown**親のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="atlaxwininit"></a>  AtlAxWinInit  
 この関数は、ホスティング コードを登録することにより、ATL のコントロールを初期化、 **"AtlAxWin80"** と**AtlAxWinLic80**ウィンドウがいくつかのカスタム ウィンドウ メッセージのクラスです。  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>戻り値  
 コードをホストしているコントロールの初期化が成功した場合は 0 以外。それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 この関数は、ATL コントロール ホスト API を使用する前に呼び出される必要があります。 この関数に対する呼び出しの後、 **"AtlAxWin"** への呼び出しでウィンドウ クラスを使用することができます[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)または[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK で説明されている。  

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm  
 この関数には、ATL のコントロールの登録を解除してコードをホストが初期化されません、 **"AtlAxWin80"** と**AtlAxWinLic80**ウィンドウ クラスです。  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>戻り値  
 常に返します**TRUE**です。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すだけ[UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) Windows SDK」の説明に従ってします。  
  
 呼び出した場合に既存のすべてのホスト ウィンドウが破棄された後にクリーンアップするには、この関数を呼び出す[な](#atlaxwininit)不要になったホスト ウィンドウを作成する必要があります。 この関数が呼び出されない場合、ウィンドウ クラスが登録解除する自動的にプロセスが終了したときにします。  
  
##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface  
 オブジェクトの既定のソース インターフェイスに関する情報を取得します。  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>パラメーター  
 `punkObj`  
 [in]情報が返される対象のオブジェクトへのポインター。  
  
 `plibid`  
 [out]ソース インターフェイスの定義が含まれるタイプ ライブラリの LIBID へのポインター。  
  
 `piid`  
 [out]オブジェクトの既定のソース インターフェイスのインターフェイス ID へのポインター。  
  
 *pdwMajor*  
 [out]ソース インターフェイスの定義が含まれるタイプ ライブラリのメジャー バージョン番号へのポインター。  
  
 *pdwMinor*  
 [out]ソース インターフェイスの定義が含まれるタイプ ライブラリのマイナー バージョン番号へのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 `AtlGetObjectSourceInterface` 既定のソース インターフェイス、LIBID と共にとメジャーのインターフェイス ID で、そのインターフェイスを記述するタイプ ライブラリのマイナー バージョン番号を指定できます。  
  
> [!NOTE]
>  要求された情報を正常に取得するには、この関数によって表されるオブジェクト`punkObj`実装する必要があります`IDispatch`(を通じて型情報を返すと**が**) も必要がありますプラスどちらかを実装`IProvideClassInfo2`または`IPersist`です。 ソース インターフェイスの型情報がの型情報と同じタイプ ライブラリである必要があります`IDispatch`です。  
  
### <a name="example"></a>例  
 次の例は、イベント シンク クラスを定義する方法を示しています。 `CEasySink`、に渡すことができるテンプレート引数の数を削減する`IDispEventImpl`に最低限必要です。 `EasyAdvise` および`EasyUnadvise`使用`AtlGetObjectSourceInterface`初期化するために、 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)メンバーを呼び出す前に[DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)または[DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)です。  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [複合コントロールに関するマクロ](../../atl/reference/composite-control-macros.md)
