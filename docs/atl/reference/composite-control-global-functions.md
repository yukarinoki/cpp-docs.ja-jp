---
title: 複合コントロールのグローバル関数
ms.date: 11/04/2016
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
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: 525fc01247053a1e2bc993398978cb332262a1a5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864746"
---
# <a name="composite-control-global-functions"></a>複合コントロールのグローバル関数

これらの関数は、ダイアログボックスを作成し、ActiveX コントロールを作成、ホスト、およびライセンスするためのサポートを提供します。

> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。 表示されるダイアログボックスには、ActiveX コントロールを含めることができます。|
|[AtlAxCreateDialog](#atlaxcreatedialog)|ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。 表示されるダイアログボックスには、ActiveX コントロールを含めることができます。|
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストし、インターフェイスポインター (またはポインター) をコントロールから取得します。|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成して初期化し、指定したウィンドウでホストし、インターフェイスポインター (またはポインター) をコントロールから取得します。|
|[AtlAxAttachControl](#atlaxattachcontrol)|事前に作成されたコントロールを指定されたウィンドウにアタッチします。|
|[AtlAxGetHost](#atlaxgethost)|ハンドルを指定して、指定したウィンドウ (存在する場合) のコンテナーへの直接インターフェイスポインターを取得するために使用します。|
|[AtlAxGetControl](#atlaxgetcontrol)|ハンドルを指定して、指定したウィンドウ内に格納されているコントロールへの直接インターフェイスポインター (存在する場合) を取得するために使用します。|
|[AtlSetChildSite](#atlsetchildsite)|子サイトの `IUnknown` を初期化します。|
|[AtlAxWinInit](#atlaxwininit)|AxWin オブジェクトのホストコードを初期化します。|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin オブジェクトのホストコードを初期化前します。|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|オブジェクトの既定のソースインターフェイスに関する情報を返します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlhost. h

##  <a name="atlaxdialogbox"></a>AtlAxDialogBox

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

*hInstance*<br/>
からダイアログボックステンプレートを含む実行可能ファイルを持つモジュールのインスタンスを識別します。

*lpTemplateName*<br/>
からダイアログボックステンプレートを識別します。 このパラメーターは、ダイアログボックステンプレートの名前を指定する null で終わる文字列へのポインターか、ダイアログボックステンプレートのリソース識別子を指定する整数値です。 パラメーターがリソース識別子を指定する場合、その上位ワードはゼロにする必要があり、その下位ワードには識別子が含まれている必要があります。 [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew)マクロを使用して、この値を作成できます。

*hWndParent*<br/>
からダイアログボックスを所有するウィンドウを識別します。

*Lpの Proc*<br/>
からダイアログボックスのプロシージャを指します。 ダイアログボックスの手順の詳細については[、「プロパティ](/windows/win32/api/winuser/nc-winuser-dlgproc)」を参照してください。

*dwInitParam*<br/>
からWM_INITDIALOG メッセージの*lParam*パラメーターのダイアログボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

ActiveX コントロールを含むダイアログテンプレートで `AtlAxDialogBox` を使用するには、ダイアログリソースの**コントロール**セクションの*テキスト*フィールドとして有効な CLSID、APPID、または URL 文字列を指定し、同じセクションの下にある "AtlAxWin80" を*クラス名*フィールドとして指定します。 有効な**コントロール**セクションは次のようになります。

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

リソーススクリプトの編集の詳細については、「[方法: テキスト形式でリソーススクリプトファイルを開く](../../windows/how-to-open-a-resource-script-file-in-text-format.md)」を参照してください。 コントロールのリソース定義ステートメントの詳細については、「Windows SDK: SDK Tools」の「[コモンコントロールパラメーター](/windows/win32/menurc/common-control-parameters) 」を参照してください。

一般的なダイアログボックスの詳細については、Windows SDK の「ダイアログボックスと[Createdialogparam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 」を[参照して](/windows/win32/api/winuser/nf-winuser-dialogboxw)ください。

##  <a name="atlaxcreatedialog"></a>AtlAxCreateDialog

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

*hInstance*<br/>
からダイアログボックステンプレートを含む実行可能ファイルを持つモジュールのインスタンスを識別します。

*lpTemplateName*<br/>
からダイアログボックステンプレートを識別します。 このパラメーターは、ダイアログボックステンプレートの名前を指定する null で終わる文字列へのポインターか、ダイアログボックステンプレートのリソース識別子を指定する整数値です。 パラメーターがリソース識別子を指定する場合、その上位ワードはゼロにする必要があり、その下位ワードには識別子が含まれている必要があります。 [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew)マクロを使用して、この値を作成できます。

*hWndParent*<br/>
からダイアログボックスを所有するウィンドウを識別します。

*Lpの Proc*<br/>
からダイアログボックスのプロシージャを指します。 ダイアログボックスの手順の詳細については[、「プロパティ](/windows/win32/api/winuser/nc-winuser-dlgproc)」を参照してください。

*dwInitParam*<br/>
からWM_INITDIALOG メッセージの*lParam*パラメーターのダイアログボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

表示されるダイアログボックスには、ActiveX コントロールを含めることができます。

Windows SDK の「 [Createdialog](/windows/win32/api/winuser/nf-winuser-createdialogw) And [Createdialogparam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 」を参照してください。

##  <a name="atlaxcreatecontrol"></a>AtlAxCreateControl

ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- `"MSCAL.Calendar.7"` などの ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` などの CLSID

- URL (`"<https://www.microsoft.com>"` など)

- `"file://\\\Documents\MyDoc.doc"` などのアクティブなドキュメントへの参照

- HTML のフラグメント (`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` など)

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に記述する必要があります。

*hWnd*<br/>
からコントロールがアタッチされるウィンドウへのハンドル。

*pStream*<br/>
からコントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
入出力コンテナーの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

このグローバル関数は、 [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszname*、 *hWnd*、 *PSTREAM*、null、null、null、null) を呼び出した場合と同じ結果を得ます。

ライセンスされた ActiveX コントロールを作成するには、「 [AtlAxCreateControlLic](#atlaxcreatecontrollic)」を参照してください。

##  <a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx

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

*lpszName*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- `"MSCAL.Calendar.7"` などの ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` などの CLSID

- URL (`"<https://www.microsoft.com>"` など)

- `"file://\\\Documents\MyDoc.doc"` などのアクティブなドキュメントへの参照

- HTML のフラグメント (`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` など)

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に記述する必要があります。

*hWnd*<br/>
からコントロールがアタッチされるウィンドウへのハンドル。

*pStream*<br/>
からコントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
入出力コンテナーの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

*ppUnkControl*<br/>
入出力作成されたコントロールの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

*iidSink*<br/>
含まれているオブジェクトの送信インターフェイスのインターフェイス識別子。

*punkSink*<br/>
含まれているオブジェクトが正常に作成された後に、含まれているオブジェクトの*Iidsink*によって指定されたコネクションポイントに接続されるシンクオブジェクトの `IUnknown` インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

`AtlAxCreateControlEx` は[AtlAxCreateControl](#atlaxcreatecontrol)に似ていますが、新しく作成されたコントロールへのインターフェイスポインターを受け取り、コントロールによって発生するイベントを受け取るようにイベントシンクを設定することもできます。

ライセンスされた ActiveX コントロールを作成するには、「 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)」を参照してください。

##  <a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic

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

*lpszName*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- `"MSCAL.Calendar.7"` などの ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` などの CLSID

- URL (`"<https://www.microsoft.com>"` など)

- `"file://\\\Documents\MyDoc.doc"` などのアクティブなドキュメントへの参照

- HTML のフラグメント (`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` など)

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に記述する必要があります。

*hWnd*<br/>
コントロールがアタッチされるウィンドウへのハンドル。

*pStream*<br/>
コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
コンテナーの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

*bstrLic*<br/>
コントロールのライセンスを格納している BSTR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="example"></a>例

`AtlAxCreateControlLic`の使用方法のサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

##  <a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx

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

*lpszName*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法で書式設定する必要があります。

- `"MSCAL.Calendar.7"` などの ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` などの CLSID

- URL (`"<https://www.microsoft.com>"` など)

- `"file://\\\Documents\MyDoc.doc"` などのアクティブなドキュメントへの参照

- HTML のフラグメント (`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` など)

   > [!NOTE]
   > `"MSHTML:"` は、MSHTML ストリームとして指定されるように、HTML フラグメントの前に記述する必要があります。

*hWnd*<br/>
コントロールがアタッチされるウィンドウへのハンドル。

*pStream*<br/>
コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*ppUnkContainer*<br/>
コンテナーの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

*ppUnkControl*<br/>
入出力作成されたコントロールの `IUnknown` を受け取るポインターのアドレス。 NULL にすることができます。

*iidSink*<br/>
含まれているオブジェクトの送信インターフェイスのインターフェイス識別子。

*punkSink*<br/>
含まれているオブジェクトが正常に作成された後に、含まれているオブジェクトの*Iidsink*によって指定されたコネクションポイントに接続されるシンクオブジェクトの `IUnknown` インターフェイスへのポインター。

*bstrLic*<br/>
コントロールのライセンスを格納している BSTR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

`AtlAxCreateControlLicEx` は[AtlAxCreateControlLic](#atlaxcreatecontrollic)に似ていますが、新しく作成されたコントロールへのインターフェイスポインターを受け取り、コントロールによって発生するイベントを受け取るようにイベントシンクを設定することもできます。

### <a name="example"></a>例

`AtlAxCreateControlLicEx`の使用方法のサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

##  <a name="atlaxattachcontrol"></a>AtlAxAttachControl

事前に作成されたコントロールを指定されたウィンドウにアタッチします。

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
からコントロールの `IUnknown` へのポインター。

*hWnd*<br/>
からコントロールをホストするウィンドウへのハンドル。

*ppUnkContainer*<br/>
入出力コンテナーオブジェクトの `IUnknown` へのポインターへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

コントロールを同時に作成してアタッチするには、 [AtlAxCreateControlEx](#atlaxcreatecontrolex)と[AtlAxCreateControl](#atlaxcreatecontrol)を使用します。

> [!NOTE]
>  `AtlAxAttachControl`を呼び出す前に、アタッチされるコントロールオブジェクトが正しく初期化されている必要があります。

##  <a name="atlaxgethost"></a>AtlAxGetHost

ハンドルが与えられた指定のウィンドウに対するコンテナーへのダイレクト インターフェイス ポインターを取得します。

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
からコントロールをホストしているウィンドウへのハンドル。

*ページ*<br/>
入出力コントロールのコンテナーの `IUnknown`。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

##  <a name="atlaxgetcontrol"></a>AtlAxGetControl

ハンドルが与えられた指定のウィンドウ内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得します。

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
からコントロールをホストしているウィンドウへのハンドル。

*ページ*<br/>
入出力ホストされているコントロールの `IUnknown`。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

##  <a name="atlsetchildsite"></a>AtlSetChildSite

子オブジェクトのサイトを親オブジェクトの `IUnknown` に設定するには、この関数を呼び出します。

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>パラメーター

*punkChild*<br/>
から子の `IUnknown` インターフェイスへのポインター。

*punkParent*<br/>
から親の `IUnknown` インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="atlaxwininit"></a>AtlAxWinInit

この関数は、 **"AtlAxWin80"** と **"AtlAxWinLic80"** の各ウィンドウクラスといくつかのカスタムウィンドウメッセージを登録することによって、ATL のコントロールホスティングコードを初期化します。

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>戻り値

コントロールをホストしているコードが正常に初期化された場合は0以外の場合は。それ以外の場合は FALSE。

### <a name="remarks"></a>コメント

ATL コントロールをホストする API を使用する前に、この関数を呼び出す必要があります。 この関数を呼び出すと、「Windows SDK」で説明されているように、 **"AtlAxWin"** ウィンドウクラスを[CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww)または[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の呼び出しで使用できます。

##  <a name="atlaxwinterm"></a>AtlAxWinTerm

この関数は、 **"AtlAxWin80"** および **"AtlAxWinLic80"** ウィンドウクラスの登録を解除することによって、ATL のコントロールホスティングコードを初期化前します。

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>コメント

この関数は、Windows SDK で説明されているように、単に[UnregisterClass](/windows/win32/api/winuser/nf-winuser-unregisterclassw)を呼び出します。

[AtlAxWinInit](#atlaxwininit)を呼び出した後、ホストウィンドウを作成する必要がなくなった場合に、既存のすべてのホストウィンドウが破棄された後に、この関数を呼び出してクリーンアップします。 この関数を呼び出さない場合、プロセスの終了時にウィンドウクラスが自動的に登録解除されます。

##  <a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface

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

*punkObj*<br/>
から情報が返されるオブジェクトへのポインター。

*plibid*<br/>
入出力ソースインターフェイスの定義を格納しているタイプライブラリの LIBID へのポインター。

*piid*<br/>
入出力オブジェクトの既定のソースインターフェイスのインターフェイス ID へのポインター。

*pdwMajor*<br/>
入出力ソースインターフェイスの定義を格納しているタイプライブラリのメジャーバージョン番号へのポインター。

*pdwMinor*<br/>
入出力ソースインターフェイスの定義を格納しているタイプライブラリのマイナーバージョン番号へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>コメント

`AtlGetObjectSourceInterface` は、既定のソースインターフェイスのインターフェイス ID と、そのインターフェイスを記述するタイプライブラリの LIBID およびメジャーバージョン番号とマイナーバージョン番号を提供します。

> [!NOTE]
>  この関数が要求された情報を正常に取得するには、 *punkObj*によって表されるオブジェクトが `IDispatch` を実装し、`IDispatch::GetTypeInfo`を介して型情報を返す必要があります。さらに、`IProvideClassInfo2` または `IPersist`も実装する必要があります。 ソースインターフェイスの型情報は、`IDispatch`の型情報と同じタイプライブラリに存在する必要があります。

### <a name="example"></a>例

次の例では、`IDispEventImpl` に渡すことができるテンプレート引数の数を最小限に抑えるために、`CEasySink`イベントシンククラスを定義する方法を示しています。 `EasyAdvise` および `EasyUnadvise`、 [Dispeventadvise](idispeventsimpleimpl-class.md#dispeventadvise)または[dispeventadvise](idispeventsimpleimpl-class.md#dispeventunadvise)を呼び出す前に、`AtlGetObjectSourceInterface` を使用して[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)メンバーを初期化します。

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>参照

[関数](../../atl/reference/atl-functions.md)<br/>
[複合コントロールに関するマクロ](../../atl/reference/composite-control-macros.md)
