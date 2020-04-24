---
title: CPropertySheet クラス
ms.date: 11/04/2016
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
ms.openlocfilehash: e8ab91b9a6fe76070d79ea2eee2e5765db2e99e3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750974"
---
# <a name="cpropertysheet-class"></a>CPropertySheet クラス

タブ ダイアログ ボックスとしても知られるプロパティ シートを表します。

## <a name="syntax"></a>構文

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティシート::Cプロパティシート](#cpropertysheet)|`CPropertySheet` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティシート:ページの追加](#addpage)|プロパティ シートにページを追加します。|
|[プロパティシート::コンストラクト](#construct)|`CPropertySheet` オブジェクトを構築します。|
|[プロパティシート::作成](#create)|モードレス プロパティ シートを表示します。|
|[プロパティシート::Doモーダル](#domodal)|モーダル プロパティ シートを表示します。|
|[プロパティシート::スタックタブを有効にする](#enablestackedtabs)|プロパティ シートで、タブの積み上げまたはスクロールのどちらを使用するかを示します。|
|[プロパティシート::エンドダイアログ](#enddialog)|プロパティ シートを終了します。|
|[プロパティシート::取得アクティブインデックス](#getactiveindex)|プロパティ シートのアクティブ なページのインデックスを取得します。|
|[プロパティシート::取得アクティブページ](#getactivepage)|アクティブなページ オブジェクトを返します。|
|[プロパティシート::取得ページ](#getpage)|指定したページへのポインターを取得します。|
|[プロパティシート::ページ数](#getpagecount)|プロパティ シートのページ数を取得します。|
|[プロパティシート::ページインデックスを取得します。](#getpageindex)|プロパティ シートの指定されたページのインデックスを取得します。|
|[プロパティシート::タブコントロールを取得します。](#gettabcontrol)|タブ コントロールへのポインターを取得します。|
|[プロパティシート::マップダイアログレック](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面単位に変換します。|
|[プロパティシート::オンイニトダイアログ](#oninitdialog)|プロパティ シートの初期化を拡張するためにオーバーライドします。|
|[プロパティシート::Pレスボタン](#pressbutton)|プロパティ シートで指定したボタンの選択をシミュレートします。|
|[プロパティシート::ページの削除](#removepage)|プロパティ シートからページを削除します。|
|[プロパティシート::アクティブページ](#setactivepage)|アクティブなページ オブジェクトをプログラムによって設定します。|
|[プロパティシート::セットフィニッシュテキスト](#setfinishtext)|[完了] ボタンのテキストを設定します。|
|[プロパティシート::セットタイトル](#settitle)|プロパティ シートのキャプションを設定します。|
|[プロパティシート::セットウィザードボタン](#setwizardbuttons)|ウィザードボタンを有効にします。|
|[プロパティシート::セットウィザードモード](#setwizardmode)|ウィザード モードを有効にします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[プロパティシート::m_psh](#m_psh)|構造体[をウィンドウのプロップシートヘッダー](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) 。 基本的なプロパティ シート パラメータへのアクセスを提供します。|

## <a name="remarks"></a>解説

プロパティ シートは、`CPropertySheet`オブジェクトと 1 つ以上の[CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクトで構成されます。 フレームワークは、タブインデックスのセットと現在選択されているページを含む領域を含むウィンドウとしてプロパティ シートを表示します。 ユーザーは、適切なタブを使用して特定のページに移動します。

`CPropertySheet`では、Windows 98 および Windows NT 2000 で導入された拡張[された PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)構造体のサポートを提供します。 この構造体には、"透かし" バックグラウンド ビットマップの使用をサポートする追加のフラグとメンバーが含まれています。

プロパティ シート オブジェクトにこれらの新しいイメージを自動的に表示するには、ビットマップイメージとパレット イメージの有効な値を[CPropertySheet::コンストラクト](#construct)または[CPropertySheet::CPropertySheet](#cpropertysheet)に渡します。

[CDialog](../../mfc/reference/cdialog-class.md)から派生していない場合でも`CPropertySheet``CDialog``CPropertySheet`、オブジェクトの管理はオブジェクトの管理に似ています。 たとえば、プロパティ シートを作成するには、コンストラクターを呼び出し、モーダル プロパティ シートの[DoModal](#domodal)を呼び出すか、モードレス プロパティ シートの[場合は Create](#create)を呼び出します。 `CPropertySheet`コンストラクターには[、2](#construct)種類のコンストラクター[があります。](#cpropertysheet)

オブジェクトを構築するときに`CPropertySheet`、一部[のウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)が原因で初回例外が発生する可能性があります。 この結果、シートを作成する前にプロパティ シートのスタイルを変更しようとしています。 この例外を回避するには、 を作成するときに次のスタイルを`CPropertySheet`設定してください。

- DS_3DLOOK

- DS_CONTROL

- Ws_child

- WS_TABSTOP

次のスタイルはオプションであり、初回例外は発生しません。

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

他の`Window Styles`人は禁止されており、有効にしないでください。

オブジェクトと外部オブジェクト間`CPropertySheet`でのデータ交換は、オブジェクトとデータを交換する場合`CDialog`と似ています。 重要な違いは、プロパティ シートの設定は、通常、`CPropertyPage`オブジェクト自体ではなく、オブジェクトのメンバー`CPropertySheet`変数です。

ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類のタブ ダイアログ ボックスでは、プロパティ ページにはタブが表示されず、一度に表示されるプロパティ ページは 1 つだけです。 また **、[OK]** ボタンと **[今すぐ適用]** ボタンを使用する代わりに、ウィザードの種類のタブ ダイアログ ボックスには、[**戻る**] ボタン、[**次へ**] または [**完了]** ボタン、[**キャンセル]** ボタン、[**ヘルプ**] ボタンがあります。

ウィザードの種類のダイアログ ボックスを作成するには、標準のプロパティ シートを作成する場合と同じ手順に従いますが[、DoModal](#domodal)を呼び出す前に[SetWizardMode](#setwizardmode)を呼び出します。 ウィザード ボタンを有効にするには、フラグを使用して[SetWizardButtons](#setwizardbuttons)を呼び出して、その機能と外観をカスタマイズします。 **[完了**] ボタンを有効にするには、ウィザードの最後のページでユーザーがアクションを実行した後に[SetFinishText](#setfinishtext)を呼び出します。

オブジェクトの使用方法`CPropertySheet`の詳細については、「[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cpropertysheetaddpage"></a><a name="addpage"></a>プロパティシート:ページの追加

指定されたページをプロパティ シートの右端のタブで追加します。

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
プロパティ シートに追加するページへのアクセスポイント。 Nll は指定できません。

### <a name="remarks"></a>解説

表示するページを左から右へ表示するプロパティ シートに追加します。

`AddPage`は、`CPropertySheet`オブジェクトのページのリストに[CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)オブジェクトを追加しますが、実際にはページのウィンドウを作成しません。 フレームワークは、ユーザーがそのページを選択するまで、ページのウィンドウの作成を延期します。

を使用して`AddPage`プロパティ ページを追加すると`CPropertySheet`、 は の`CPropertyPage`親になります。 プロパティ ページからプロパティ シートにアクセスするには[、CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)を呼び出します。

プロパティ シート ウィンドウを作成して を呼び出`AddPage`すまで待つ必要はありません。 通常は`AddPage`[、DoModal](#domodal)または[Create](#create)を呼び出す前に呼び出します。

プロパティ ページ`AddPage`を表示した後に呼び出すと、タブ行に新しく追加されたページが反映されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

## <a name="cpropertysheetconstruct"></a><a name="construct"></a>プロパティシート::コンストラクト

`CPropertySheet` オブジェクトを構築します。

```cpp
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>パラメーター

*nIDキャプション*<br/>
プロパティ シートに使用するキャプションの ID。

*pParentWnd*<br/>
プロパティ シートの親ウィンドウへのポインター。 NULL の場合、親ウィンドウはアプリケーションのメイン ウィンドウになります。

*ページを選択します。*<br/>
最初に先頭に表示されるページのインデックス。 既定は、シートに追加された最初のページです。

*キャプション*<br/>
プロパティ シートに使用するキャプションを含む文字列へのポインター。 Nll は指定できません。

*hbmウォーターマーク*<br/>
プロパティ ページのウォーターマーク ビットマップへのハンドル。

*hpalウォーターマーク*<br/>
透かしビットマップまたはヘッダー ビットマップのパレットへのハンドル。

*hbm ヘッダー*<br/>
プロパティ ページのヘッダー ビットマップへのハンドル。

### <a name="remarks"></a>解説

クラス コンストラクターのいずれかが呼び出されていない場合は、このメンバー関数を呼び出します。 たとえば、オブジェクトの`Construct``CPropertySheet`配列を宣言または割り当てるときに呼び出します。 配列の場合は、配列内の各メンバー`Construct`を呼び出す必要があります。

プロパティ シートを表示するには[、DoModal](#domodal)または[Create](#create)を呼び出します。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。

上に`Construct`示した 3 番目または 4 番目のプロトタイプを使用し *、hbmWatermark 、hpalWatermark*、および/または*hbmHeader*パラメーターに有効な値を渡すと、ウォーターマークやヘッダー イメージを自動的に表示できます。 *hpalWatermark*

### <a name="example"></a>例

次の例は、どのような状況で呼び出`Construct`す場合を示しています。

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

## <a name="cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>プロパティシート::Cプロパティシート

`CPropertySheet` オブジェクトを構築します。

```
CPropertySheet();

explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>パラメーター

*nIDキャプション*<br/>
プロパティ シートに使用するキャプションの ID。

*pParentWnd*<br/>
プロパティ シートの親ウィンドウへのアクセスをポイントします。 NULL の場合、親ウィンドウはアプリケーションのメイン ウィンドウになります。

*ページを選択します。*<br/>
最初に先頭に表示されるページのインデックス。 既定は、シートに追加された最初のページです。

*キャプション*<br/>
プロパティ シートに使用するキャプションを含む文字列へのアクセスをポイントします。 Nll は指定できません。

*hbmウォーターマーク*<br/>
プロパティ シートの背景ビットマップへのハンドル。

*hpalウォーターマーク*<br/>
透かしビットマップまたはヘッダー ビットマップのパレットへのハンドル。

*hbm ヘッダー*<br/>
プロパティ ページのヘッダー ビットマップへのハンドル。

### <a name="remarks"></a>解説

プロパティ シートを表示するには[、DoModal](#domodal)または[Create](#create)を呼び出します。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。

複数のパラメーターがある場合 (たとえば、配列を使用している場合) は[Construct](#construct)、 の`CPropertySheet`代わりに Construct を使用します。

`CPropertySheet`上述の 3 番目または 4 番目のプロトタイプを使用し *、hbmWatermark 、hpalWatermark*、および/または*hbmHeader*パラメーターに有効な値を渡すと、ウォーターマークやヘッダー イメージを自動的に表示できます。 *hpalWatermark*

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

## <a name="cpropertysheetcreate"></a><a name="create"></a>プロパティシート::作成

モードレス プロパティ シートを表示します。

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
親ウィンドウへのポイント。 NULL の場合、親はデスクトップです。

*Dwstyle*<br/>
プロパティ シートのウィンドウ スタイル。 使用可能なスタイルの完全な一覧については、「[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。

*ドウェエクススタイル*<br/>
プロパティ シートの拡張ウィンドウ スタイル。 使用可能なスタイルの完全な一覧については、「[拡張ウィンドウ スタイル」を](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)参照してください。

### <a name="return-value"></a>戻り値

プロパティ シートが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

呼`Create`び出しは、コンストラクター内に配置することも、コンストラクターが呼び出された後で呼び出すこともできます。

-1 を*dwStyle*として渡して表す既定&#124;&#124;WS_CAPTION WS_POPUP&#124;のスタイルは、実際には、DS_MODALFRAME DS_CONTEXTHELPの&#124;WS_VISIBLEをDS_MODALFRAME&#124;&#124;&#124;&#124;WS_SYSMENUWS_SYSMENU。 0 を*dwExStyle*として渡すことによって表される既定の拡張ウィンドウ スタイルは、実際にはWS_EX_DLGMODALFRAME。

この`Create`メンバー関数は、プロパティ シートを作成した直後に返されます。 プロパティ シートを破棄するには[、CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)を呼び出します。

モーダル プロパティ シートと同様に`Create`、[OK]、[キャンセル]、[今すぐ適用]、[ヘルプ] ボタンを呼び出して表示されるモードレス プロパティ シート。 必要なボタンは、ユーザーが作成する必要があります。

モーダル プロパティ シートを表示するには、代わりに[DoModal を](#domodal)呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

## <a name="cpropertysheetdomodal"></a><a name="domodal"></a>プロパティシート::Doモーダル

モーダル プロパティ シートを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は IDOK または IDCANCEL。それ以外の場合は 0 または -1。 プロパティ シートがウィザードとして設定されている場合は[(SetWizardMode](#setwizardmode)を`DoModal`参照)、ID_WIZFINISHまたは IDCANCEL を返します。

### <a name="remarks"></a>解説

戻り値は、プロパティ シートを閉じたコントロールの ID に対応します。 この関数が返された後、プロパティ シートに対応するウィンドウとすべてのページが破棄されます。 オブジェクト自体は、まだ存在します。 通常は、IDOK を返した後`DoModal`に[、CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクトからデータを取得します。

モードレス プロパティ シートを表示するには、代わりに[Create を](#create)呼び出します。

プロパティ ページが対応するダイアログ リソースから作成されると、初回例外が発生する可能性があります。 この結果、ページが作成される前に、ダイアログ リソースのスタイルが必要なスタイルに変更されます。 リソースは通常読み取り専用であるため、例外が発生します。 システムは例外を処理し、変更されたリソースのコピーを作成します。 したがって、最初の例外は無視できます。

> [!NOTE]
> 非同期例外処理モデルを使用してコンパイルする場合は、オペレーティング システムによってこの例外を処理する必要があります。 例外処理モデルの詳細については[、/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)を参照してください。 この場合、catch がすべての例外を`CPropertySheet::DoModal`処理する C++ try-catch ブロック (たとえば) での呼び`catch (...)`出しをラップしないでください。 このブロックは、オペレーティング システム用の例外を処理し、予期しない動作を引き起こします。 ただし、C++ 例外処理は、特定の例外の種類またはアクセス違反例外がオペレーティング システムに渡される構造化例外処理で安全に使用できます。

この初回例外が生成されないようにするには、プロパティ シートに正しい[Window Styles](../../mfc/reference/styles-used-by-mfc.md#window-styles)が設定されていることを手動で保証します。 プロパティ シートには、次のスタイルを設定する必要があります。

- DS_3DLOOK

- DS_CONTROL

- Ws_child

- WS_TABSTOP

最初の例外を発生させることなく、次のオプション のスタイルを使用できます。

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

その他の Windows スタイルはプロパティ シートと互換性がないため、無効にします。 このアドバイスは、拡張スタイルには適用されません。 これらの標準スタイルを適切に設定すると、プロパティ シートを変更する必要がなくなります。

### <a name="example"></a>例

[「プロパティ シート::AddPage」](#addpage)の例を参照してください。

## <a name="cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>プロパティシート::スタックタブを有効にする

プロパティ シートにタブの行をスタックするかどうかを示します。

```cpp
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>パラメーター

*bスタック*<br/>
プロパティ シートで、積み上げタブを有効にするかどうかを示します。 bStacked を FALSE に設定して、タグ*の積み重ね行を*無効にします。

### <a name="remarks"></a>解説

既定では、プロパティ シートの幅が 1 行に収まるよりも多くのタブがある場合、タブは複数行に重ねて表示されます。 タブをスタックするのではなくスクロールタブを使用するには`EnableStackedTabs`[、DoModal](#domodal)または[Create](#create)を呼び出す前に *、bStacked*を FALSE に設定して呼び出します。

モーダルまたは`EnableStackedTabs`モードレスプロパティ シートを作成するときに呼び出す必要があります。 派生クラスにこのスタイルを`CPropertySheet`組み込むには、WM_CREATEのメッセージ ハンドラーを記述します。 オーバーライドされたバージョンの[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)で、`EnableStackedTabs( FALSE )`基本クラスの実装を呼び出す前に呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

## <a name="cpropertysheetenddialog"></a><a name="enddialog"></a>プロパティシート::エンドダイアログ

プロパティ シートを終了します。

```cpp
void EndDialog(int nEndID);
```

### <a name="parameters"></a>パラメーター

*NEndID*<br/>
プロパティ シートの戻り値として使用される識別子。

### <a name="remarks"></a>解説

このメンバー関数は、OK、キャンセル、または閉じるボタンが押されたときにフレームワークによって呼び出されます。 プロパティ シートを閉じる必要があるイベントが発生した場合は、このメンバー関数を呼び出します。

このメンバー関数は、モーダル ダイアログ ボックスでのみ使用されます。

### <a name="example"></a>例

[「プロパティ シート::Pレスボタン」の例を](#pressbutton)参照してください。

## <a name="cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>プロパティシート::取得アクティブインデックス

プロパティ シート ウィンドウのアクティブ ページのインデックス番号を取得し、返されたインデックス番号を`GetPage`のパラメーターとして使用します。

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>戻り値

アクティブなページのインデックス番号。

### <a name="example"></a>例

次の例[を](#getactivepage)参照してください。

## <a name="cpropertysheetgetactivepage"></a><a name="getactivepage"></a>プロパティシート::取得アクティブページ

プロパティ シート ウィンドウのアクティブ なページを取得します。

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>戻り値

アクティブなページへのポインター。

### <a name="remarks"></a>解説

このメンバー関数を使用して、アクティブ ページで何らかのアクションを実行します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

## <a name="cpropertysheetgetpage"></a><a name="getpage"></a>プロパティシート::取得ページ

このプロパティ シート内の指定されたページへのポインターを返します。

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>パラメーター

*nページ*<br/>
0 から始まる、目的のページのインデックス。 プロパティ シートのページ数よりも 0 ~ 1 未満の範囲で指定してください。

### <a name="return-value"></a>戻り値

*nPage*パラメーターに対応するページへのポインター。

### <a name="example"></a>例

[「CPropertyPage::ウィザード完了」](../../mfc/reference/cpropertypage-class.md#onwizardfinish)の例を参照してください。

## <a name="cpropertysheetgetpagecount"></a><a name="getpagecount"></a>プロパティシート::ページ数

プロパティ シートに現在表示されているページ数を決定します。

```
int GetPageCount() const;
```

### <a name="return-value"></a>戻り値

プロパティ シートのページ数。

### <a name="example"></a>例

[「CPropertyPage::ウィザード完了」](../../mfc/reference/cpropertypage-class.md#onwizardfinish)の例を参照してください。

## <a name="cpropertysheetgetpageindex"></a><a name="getpageindex"></a>プロパティシート::ページインデックスを取得します。

プロパティ シート内の指定されたページのインデックス番号を取得します。

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
インデックスが見つかったページへのポイント。 Nll は指定できません。

### <a name="return-value"></a>戻り値

ページのインデックス番号。

### <a name="remarks"></a>解説

たとえば、ページ インデックス`GetPageIndex`を取得して[、SetActivePage](#setactivepage)または[GetPage](#getpage)を使用します。

### <a name="example"></a>例

次の例[を](#getactivepage)参照してください。

## <a name="cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>プロパティシート::タブコントロールを取得します。

タブ コントロールへのポインターを取得して、タブ コントロールに固有の処理を実行します ([つまり、CTabCtrl](../../mfc/reference/ctabctrl-class.md)の API を使用します)。

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>戻り値

タブ コントロールへのポインター。

### <a name="remarks"></a>解説

たとえば、初期化中に各タブにビットマップを追加する場合は、このメンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

## <a name="cpropertysheetm_psh"></a><a name="m_psh"></a>プロパティシート::m_psh

メンバーが[PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)の特性を格納する構造体。

### <a name="remarks"></a>解説

この構造体を使用して、プロパティ シートの外観を、構築後[、DoModal](#domodal)メンバー関数で表示する前に初期化します。 たとえば *、dwSize*メンバー`m_psh`をプロパティ シートに設定するサイズに設定します。

メンバーの一覧を含む、この構造体の詳細については、Windows SDK の PROPSHEET ヘッダーを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

## <a name="cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>プロパティシート::マップダイアログレック

四角形のダイアログ ボックスの単位を画面単位に変換します。

```cpp
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
変換するダイアログ ボックス座標を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

ダイアログ ボックスの単位は、ダイアログ ボックス テキストに使用されるフォントの文字の平均幅と高さから派生した、現在のダイアログ ボックスの基本単位を表します。 水平単位はダイアログ ボックスの基本幅単位の 4 分の 1 で、垂直単位はダイアログ ボックスの基本高さの単位の 8 分の 1 です。

[GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) Windows 関数は、システム フォントのサイズ情報を返しますが、リソース定義ファイルでDS_SETFONT スタイルを使用する場合は、プロパティ シートごとに異なるフォントを指定できます。 Windows SDK で説明されている[MapDialogRect](/windows/win32/api/winuser/nf-winuser-mapdialogrect) Windows 関数は、このダイアログ ボックスに適切なフォントを使用します。

この`MapDialogRect`メンバー関数は、ダイアログ ボックスを作成したり、ボックス内にコントロールを配置したりするために、この四角形を使用して *、lpRect*のダイアログ ボックス単位を画面単位 (ピクセル) に置き換えます。

## <a name="cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>プロパティシート::オンイニトダイアログ

プロパティ シートの初期化を強化するためにオーバーライドします。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

アプリケーションが入力フォーカスをプロパティ シートのコントロールのいずれかに設定したかどうかを指定します。 0`OnInitDialog`以外の値を返す場合、Windows は、入力フォーカスをプロパティ シートの最初のコントロールに設定します。 アプリケーションは、入力フォーカスをプロパティ シートのコントロールのいずれかに明示的に設定している場合にのみ 0 を返すことができます。

### <a name="remarks"></a>解説

このメンバー関数は、WM_INITDIALOG メッセージに応答して呼び出されます。 このメッセージは、プロパティ シートが表示される直前に発生する[Create](#create)または[DoModal](#domodal)呼び出し中にプロパティ シートに送信されます。

プロパティ シートの初期化時に特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、まず基本クラス`OnInitDialog`を呼び出しますが、戻り値は無視します。 通常、オーバーライドされたメンバー関数から TRUE を返します。

このメンバー関数にメッセージ マップ エントリは必要ありません。

## <a name="cpropertysheetpressbutton"></a><a name="pressbutton"></a>プロパティシート::Pレスボタン

プロパティ シートで指定したボタンの選択をシミュレートします。

```cpp
void PressButton(int nButton);
```

### <a name="parameters"></a>パラメーター

*nボタン*<br/>
nButton : 押すボタンを識別します。 このパラメーターには、次のいずれかの値を指定できます。

- PSBTN_BACK 戻るボタンを選択します。

- PSBTN_NEXT 次へボタンを選択します。

- PSBTN_FINISH [完了] ボタンを選択します。

- PSBTN_OK [OK] ボタンをクリックします。

- PSBTN_APPLYNOW 今すぐ適用ボタンを選択します。

- PSBTN_CANCEL [キャンセル] ボタンを選択します。

- PSBTN_HELP ヘルプ ボタンを選択します。

### <a name="remarks"></a>解説

Windows SDK プレス ボタン メッセージの詳細については[、「PSM_PRESSBUTTON」](/windows/win32/Controls/psm-pressbutton)を参照してください。

呼`PressButton`び出しでは、プロパティ ページからフレームワークに[PSN_APPLY](/windows/win32/Controls/psn-apply)通知は送信されません。 この通知を送信するには[、CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

## <a name="cpropertysheetremovepage"></a><a name="removepage"></a>プロパティシート::ページの削除

プロパティ シートからページを削除し、関連付けられているウィンドウを破棄します。

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
プロパティ シートから削除するページへのアクセスポイント。 Nll は指定できません。

*nページ*<br/>
削除するページのインデックス。 プロパティ シートのページ数よりも 0 ~ 1 未満の範囲で指定してください。

### <a name="remarks"></a>解説

`CPropertySheet` [CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクト自体は、ウィンドウの所有者が閉じられるまで破棄されません。

## <a name="cpropertysheetsetactivepage"></a><a name="setactivepage"></a>プロパティシート::アクティブページ

アクティブなページを変更します。

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*nページ*<br/>
設定するページのインデックス。 0 から 1 ページ未満の間にする必要があります。

*ページ*<br/>
プロパティ シートで設定するページへのアクセスポイント。 この式は NULL になることはできません。

### <a name="return-value"></a>戻り値

プロパティ シートが正常にアクティブ化された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

たとえば、あるページ`SetActivePage`でユーザーの操作によって別のページがアクティブなページになる場合に使用します。

### <a name="example"></a>例

次の例[を](#getactivepage)参照してください。

## <a name="cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>プロパティシート::セットフィニッシュテキスト

[完了] コマンド ボタンのテキストを設定します。

```cpp
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[完了] コマンド ボタンに表示されるテキストへのポイント。

### <a name="remarks"></a>解説

[`SetFinishText`完了] コマンド ボタンにテキストを表示し、ウィザードの最後のページでユーザーが操作を完了した後に [次へ] ボタンと [戻る] ボタンを非表示にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsettitle"></a><a name="settitle"></a>プロパティシート::セットタイトル

プロパティ シートのキャプション (フレーム ウィンドウのタイトル バーに表示されるテキスト) を指定します。

```cpp
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
プロパティ シートのタイトルのスタイルを指定します。 スタイルは 0 または PSH_PROPTITLE で指定する必要があります。 スタイルをPSH_PROPTITLEに設定すると、キャプションとして指定したテキストの後に「プロパティ」という単語が表示されます。 たとえば、呼び`SetTitle`出し (「シンプル」、PSH_PROPTITLE) を呼び出すと、プロパティ シートのキャプションは "シンプル プロパティ" になります。

*lpszText*<br/>
プロパティ シートのタイトル バーでキャプションとして使用するテキストへのポイント。

### <a name="remarks"></a>解説

既定では、プロパティ シートのコンストラクターで caption パラメーターが使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

## <a name="cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>プロパティシート::セットウィザードボタン

ウィザードのプロパティ シートの [戻る]、[次へ]、または [完了] ボタンを有効または無効にします。

```cpp
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ウィザード ボタンの機能と外観をカスタマイズするフラグのセット。 このパラメーターは、次の値の組み合わせにすることができます。

- PSWIZB_BACK戻るボタン

- PSWIZB_NEXT次へボタン

- [完了PSWIZB_FINISH] ボタン

- PSWIZB_DISABLEDFINISH無効な完了ボタン

### <a name="remarks"></a>解説

ダイアログ`SetWizardButtons`が開いた後にのみ呼び出し。[DoModal](#domodal)を呼`SetWizardButtons`び出す前に呼び出す必要があります。 通常は`SetWizardButtons`[、CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)から呼び出す必要があります。

ユーザーがウィザードを完了したら、[完了] ボタンのテキストを変更するか、[次へ] ボタンと [戻る] ボタンを非表示にする場合は[、SetFinishText](#setfinishtext)を呼び出します。 [完了] と [次へ] で同じボタンが共有されることに注意してください。 [完了] ボタンまたは [次へ] ボタンは一度に表示できますが、両方を表示することはできません。

### <a name="example"></a>例

には`CPropertySheet`、 、 、`CStylePage``CColorPage`および`CShapePage`の 3 つのウィザード プロパティ ページがあります。  次のコードは、ウィザードのプロパティ ページの **[戻る**] ボタンと [**次へ**] ボタンを有効または無効にする方法を示しています。

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>プロパティシート::セットウィザードモード

プロパティ ページをウィザードとして設定します。

```cpp
void SetWizardMode();
```

### <a name="remarks"></a>解説

ウィザードのプロパティ ページの重要な特徴は、ユーザーがタブではなく[次へ]ボタンまたは[完了]ボタン、[戻る]ボタン、および [キャンセル] ボタンを使用して移動することです。

`SetWizardMode` [DoModal を](#domodal)呼び出す前に呼び出します。 を`DoModal`呼び`SetWizardMode`出すと、ID_WIZFINISH (ユーザーが [完了] ボタンを使用して閉じた場合) または IDCANCEL が返されます。

`SetWizardMode`PSH_WIZARDフラグを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル のプロップル](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
