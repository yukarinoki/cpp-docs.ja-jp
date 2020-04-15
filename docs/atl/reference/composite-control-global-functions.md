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
ms.openlocfilehash: 99ecd4cf04b3eb696f897d6ef5a5e3839d46ef17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331611"
---
# <a name="composite-control-global-functions"></a>複合コントロールのグローバル関数

これらの関数は、ダイアログ ボックスの作成、および ActiveX コントロールの作成、ホスト、およびライセンスの作成をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。 ダイアログ ボックスには ActiveX コントロールを含めることができます。|
|[AtlAxCreateDialog](#atlaxcreatedialog)|ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。 ダイアログ ボックスには ActiveX コントロールを含めることができます。|
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX コントロールを作成し、初期化し、指定したウィンドウでホストし、コントロールからインターフェイス ポインター (またはポインター) を取得します。|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|ライセンスを取得した ActiveX コントロールを作成し、初期化し、指定されたウィンドウでホストし、コントロールからインターフェイス ポインター (またはポインター) を取得します。|
|[AtlAxAttachControl](#atlaxattachcontrol)|事前に作成されたコントロールを指定されたウィンドウにアタッチします。|
|[AtlAxGetHost](#atlaxgethost)|ハンドルを指定して、指定されたウィンドウ (存在する場合) のコンテナーへの直接インターフェイス ポインターを取得するために使用します。|
|[AtlAxGetControl](#atlaxgetcontrol)|ハンドルを指定して、指定したウィンドウ内に含まれるコントロール (存在する場合) への直接インターフェイス ポインターを取得するために使用します。|
|[AtlSetChildSite](#atlsetchildsite)|子サイトの`IUnknown`を初期化します。|
|[AtlAxWinInit](#atlaxwininit)|AxWin オブジェクトのホスティング コードを初期化します。|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin オブジェクトのホスティング コードを初期化解除します。|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|オブジェクトの既定のソース インターフェイスに関する情報を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlhost.h

## <a name="atlaxdialogbox"></a><a name="atlaxdialogbox"></a>アトルアクスダイアログボックス

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
[in]実行可能ファイルにダイアログ ボックス テンプレートが含まれているモジュールのインスタンスを識別します。

*テンプレート名*<br/>
[in]ダイアログ ボックス テンプレートを識別します。 このパラメーターは、ダイアログ ボックス テンプレートの名前を指定する NULL で終わる文字列へのポインター、またはダイアログ ボックス テンプレートのリソース識別子を指定する整数値です。 パラメーターでリソース識別子を指定する場合、上位ワードはゼロでなければならず、下位ワードには識別子が含まれている必要があります。 この値を作成するには、[メイクイントリソース](/windows/win32/api/winuser/nf-winuser-makeintresourcew)・マクロを使用できます。

*スーンドペアレント*<br/>
[in]ダイアログ ボックスを所有するウィンドウを識別します。

*をクリックします。*<br/>
[in]ダイアログ ボックス プロシージャへのポイント。 ダイアログ ボックスの手順の詳細については、「 [DialogProc](/windows/win32/api/winuser/nc-winuser-dlgproc)」を参照してください。

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

ActiveX`AtlAxDialogBox`コントロールを含むダイアログ テンプレートを使用するには、有効な CLSID、APPID、または URL 文字列をダイアログ リソースの**CONTROL**セクションの*テキスト*フィールドとして指定し、同じセクションの*下のクラス名*フィールドとして "AtlAxWin80" を指定します。 有効な**CONTROL**セクションの例を次に示します。

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

リソース スクリプトの編集の詳細については、「[方法 : リソース スクリプト ファイルをテキスト形式で開く](../../windows/how-to-open-a-resource-script-file-in-text-format.md)」を参照してください。 制御リソース定義ステートメントの詳細については、「Windows SDK: SDK ツール」の[「共通コントロール パラメーター](/windows/win32/menurc/common-control-parameters) 」を参照してください。

ダイアログ ボックス全般の詳細については、Windows SDK の[ダイアログ ボックス](/windows/win32/api/winuser/nf-winuser-dialogboxw)および[ダイアログ パラムの作成](/windows/win32/api/winuser/nf-winuser-createdialogparamw)を参照してください。

## <a name="atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>アトルアクス作成ダイアログ

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
[in]実行可能ファイルにダイアログ ボックス テンプレートが含まれているモジュールのインスタンスを識別します。

*テンプレート名*<br/>
[in]ダイアログ ボックス テンプレートを識別します。 このパラメーターは、ダイアログ ボックス テンプレートの名前を指定する NULL で終わる文字列へのポインター、またはダイアログ ボックス テンプレートのリソース識別子を指定する整数値です。 パラメーターでリソース識別子を指定する場合、上位ワードはゼロでなければならず、下位ワードには識別子が含まれている必要があります。 この値を作成するには、[メイクイントリソース](/windows/win32/api/winuser/nf-winuser-makeintresourcew)・マクロを使用できます。

*スーンドペアレント*<br/>
[in]ダイアログ ボックスを所有するウィンドウを識別します。

*をクリックします。*<br/>
[in]ダイアログ ボックス プロシージャへのポイント。 ダイアログ ボックスの手順の詳細については、「 [DialogProc](/windows/win32/api/winuser/nc-winuser-dlgproc)」を参照してください。

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

ダイアログ ボックスには ActiveX コントロールを含めることができます。

Windows SDK[の「ダイアログの作成](/windows/win32/api/winuser/nf-winuser-createdialogw)」および「[ダイアログパラムの作成](/windows/win32/api/winuser/nf-winuser-createdialogparamw)」を参照してください。

## <a name="atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>アトルアクスコントロール

ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。

*hWnd*<br/>
[in]コントロールがアタッチされるウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
[アウト]コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

このグローバル関数は[、AtlAxCreateControlEx](#atlaxcreatecontrolex)*(lpszName* *、hWnd*、pStream、NULL、NULL、NULL、NULL)を呼び出すのと同じ結果を提供します。 *pStream*

ライセンスを取得した ActiveX コントロールを作成するには[、「AtlAxCreateControlLic](#atlaxcreatecontrollic)」を参照してください。

## <a name="atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>アトリアクスコントロールレックス

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

*名前を指定します。*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。

*hWnd*<br/>
[in]コントロールがアタッチされるウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
[アウト]コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*コントロールを実行します。*<br/>
[アウト]作成されたコントロールを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*iidシンク*<br/>
含まれているオブジェクトの発信インターフェイスのインターフェイス識別子。

*パンクシンク*<br/>
含まれるオブジェクトが`IUnknown`正常に作成された後に、iidSink によって指定された*iidSink*コネクション ポイントに接続されるシンク オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

`AtlAxCreateControlEx`[AtlAxCreateControl](#atlaxcreatecontrol)に似ていますが、新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクを設定することもできます。

ライセンスを取得した ActiveX コントロールを作成するには[、「AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)」を参照してください。

## <a name="atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>アトルアクスクリエイトコントロールコントロール

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

*名前を指定します。*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。

*hWnd*<br/>
コントロールがアタッチされるウィンドウへのハンドル。

*pストリーム*<br/>
コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*bstrLic*<br/>
コントロールのライセンスを含む BSTR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="example"></a>例

使用`AtlAxCreateControlLic`方法のサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照してください。

## <a name="atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>アトリアクスクリエイトコントロールレックス

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

*名前を指定します。*<br/>
コントロールに渡される文字列へのポインター。 次のいずれかの方法でフォーマットする必要があります。

- 次のような ProgID`"MSCAL.Calendar.7"`

- 次のような CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 次のような URL`"<https://www.microsoft.com>"`

- アクティブ ドキュメントへの参照。`"file://\\\Documents\MyDoc.doc"`

- HTML のフラグメント`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML ストリームとして指定されるように、HTML フラグメントの前に置く必要があります。

*hWnd*<br/>
コントロールがアタッチされるウィンドウへのハンドル。

*pストリーム*<br/>
コントロールのプロパティを初期化するために使用されるストリームへのポインター。 NULL にすることができます。

*コンテナを使用します。*<br/>
コンテナーを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*コントロールを実行します。*<br/>
[アウト]作成されたコントロールを受け取るポインター`IUnknown`のアドレス。 NULL にすることができます。

*iidシンク*<br/>
含まれているオブジェクトの発信インターフェイスのインターフェイス識別子。

*パンクシンク*<br/>
含まれるオブジェクトが`IUnknown`正常に作成された後に、iidSink によって指定された*iidSink*コネクション ポイントに接続されるシンク オブジェクトのインターフェイスへのポインター。

*bstrLic*<br/>
コントロールのライセンスを含む BSTR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

`AtlAxCreateControlLicEx`[AtlAxCreateControlLic](#atlaxcreatecontrollic)に似ていますが、新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクを設定することもできます。

### <a name="example"></a>例

使用`AtlAxCreateControlLicEx`方法のサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照してください。

## <a name="atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>アトルアクスアックスコントロール

事前に作成されたコントロールを指定されたウィンドウにアタッチします。

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
[in]コントロールの への`IUnknown`ポインター。

*hWnd*<br/>
[in]コントロールをホストするウィンドウへのハンドル。

*コンテナを使用します。*<br/>
[アウト]コンテナー オブジェクトへのポインターへの`IUnknown`ポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロールを同時に作成およびアタッチするには[、AtlAxCreateControlEx](#atlaxcreatecontrolex)と[AtlAxCreateControl](#atlaxcreatecontrol)を使用します。

> [!NOTE]
> を呼び出す`AtlAxAttachControl`前に、アタッチされるコントロール オブジェクトを正しく初期化する必要があります。

## <a name="atlaxgethost"></a><a name="atlaxgethost"></a>アトルアクスゲットホスト

ハンドルが与えられた指定のウィンドウに対するコンテナーへのダイレクト インターフェイス ポインターを取得します。

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]コントロールをホストしているウィンドウへのハンドル。

*頁*<br/>
[アウト]コントロール`IUnknown`のコンテナーの。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>アトルアクスゲットコントロール

ハンドルが与えられた指定のウィンドウ内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得します。

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]コントロールをホストしているウィンドウへのハンドル。

*頁*<br/>
[アウト]ホスト`IUnknown`されているコントロールの。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="atlsetchildsite"></a><a name="atlsetchildsite"></a>アトルセットチャイルドサイト

子オブジェクトのサイトを親オブジェクトの に`IUnknown`設定します。

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>パラメーター

*パンクチャイルド*<br/>
[in]子の`IUnknown`インターフェイスへのポインター。

*パンクペアレント*<br/>
[in]親の`IUnknown`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="atlaxwininit"></a><a name="atlaxwininit"></a>アトルアクスウィニット

この関数は **、"AtlAxWin80" ウィンドウ**クラスと**カスタム**ウィンドウ メッセージの 2 つの登録によって ATL のコントロール ホスティング コードを初期化します。

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>戻り値

コントロールをホストするコードの初期化が成功した場合は 0 以外の値を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、ATL コントロール ホスティング API を使用する前に呼び出す必要があります。 この関数を呼び出した後、Windows SDK で説明されているように[、CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww)または[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の呼び出しで **"AtlAxWin"** ウィンドウ クラスを使用できます。

## <a name="atlaxwinterm"></a><a name="atlaxwinterm"></a>アトリアクスウィンターム

この関数は **、"AtlAxWin80" ウィンドウ クラスと "AtlAxWinLic80"** ウィンドウ クラスの登録を解除することにより、ATL のコントロール ホスティング コード**を**初期化解除します。

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

この関数は、Windows SDK で説明されているように[、単に UnregisterClass](/windows/win32/api/winuser/nf-winuser-unregisterclassw)を呼び出します。

[AtlAxWinInit](#atlaxwininit)を呼び出してホスト ウィンドウを作成する必要がなくなった場合、既存のすべてのホスト ウィンドウが破棄された後にクリーンアップするには、この関数を呼び出します。 この関数を呼び出さないと、プロセスが終了するとウィンドウ クラスは自動的に登録解除されます。

## <a name="atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>インターフェイス

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

*パンクObj*<br/>
[in]情報を返すオブジェクトへのポインター。

*プリビッド*<br/>
[アウト]ソース インターフェイスの定義を含むタイプ ライブラリの LIBID へのポインター。

*ピッド*<br/>
[アウト]オブジェクトの既定のソース インターフェイスのインターフェイス ID へのポインター。

*pdwメジャー*<br/>
[アウト]ソース インターフェイスの定義を含むタイプ ライブラリのメジャー バージョン番号へのポインター。

*pdwマイナー*<br/>
[アウト]ソース インターフェイスの定義を含むタイプ ライブラリのマイナー バージョン番号へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`AtlGetObjectSourceInterface`では、デフォルトのソース インターフェイスのインターフェイス ID と、そのインターフェイスを記述するタイプ ライブラリの LIBID およびメジャー バージョン番号とマイナー バージョン番号を指定できます。

> [!NOTE]
> この関数が要求された情報を正常に取得するには *、punkObj*で表されるオブジェクト`IDispatch`が、 を実装し`IDispatch::GetTypeInfo`、 およびを通じて型`IProvideClassInfo2`情報`IPersist`を返す必要があります。 ソース インターフェイスの型情報は、 の型情報と同じタイプ ライブラリに`IDispatch`含まれる必要があります。

### <a name="example"></a>例

次の例では、`CEasySink`イベント シンク クラス を定義する方法を示しています。 `IDispEventImpl` `EasyAdvise`を`EasyUnadvise`使用`AtlGetObjectSourceInterface`して[、DIspEventAdvise または DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventadvise)を呼び出す前に[、IDispEventImpl](../../atl/reference/idispeventimpl-class.md)メンバーを初期化[するために](idispeventsimpleimpl-class.md#dispeventunadvise)使用します。

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[複合コントロール マクロ](../../atl/reference/composite-control-macros.md)
