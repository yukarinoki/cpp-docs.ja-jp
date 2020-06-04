---
title: CPrintDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: 6490e5488c5ab3b808a02e3608b75541e4063d8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364062"
---
# <a name="cprintdialog-class"></a>CPrintDialog クラス

Windows のコモン ダイアログ ボックスである [印刷] ダイアログで提供されるサービスをカプセル化したものです。

## <a name="syntax"></a>構文

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::C印刷ダイアログ](#cprintdialog)|`CPrintDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::プリンタDCの作成](#createprinterdc)|[印刷] ダイアログ ボックスを表示せずに、プリンター デバイス コンテキストを作成します。|
|[ダイアログ:Dモーダル](#domodal)|ダイアログ ボックスを表示し、ユーザーが選択できるようにします。|
|[をクリックします。](#getcopies)|要求されたコピーの数を取得します。|
|[をクリックします。](#getdefaults)|ダイアログ ボックスを表示せずにデバイスの既定値を取得します。|
|[をクリックします。](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|
|[ダイアログ::デヴモードを取得します。](#getdevmode)|構造体を取得`DEVMODE`します。|
|[をクリックします。](#getdrivername)|現在選択されているプリンタ ドライバの名前を取得します。|
|[ページから取得します。](#getfrompage)|印刷範囲の開始ページを取得します。|
|[をクリックします。](#getportname)|現在選択されているプリンタ ポートの名前を取得します。|
|[ダイアログ::ゲットプリンターDC](#getprinterdc)|プリンターデバイス コンテキストへのハンドルを取得します。|
|[ダイアログ::取得ページ](#gettopage)|印刷範囲の終了ページを取得します。|
|[を :Pクリックします。](#printall)|文書のすべてのページを印刷するかどうかを決定します。|
|[:Pリントコルレート](#printcollate)|照合されたコピーが要求されているかどうかを判断します。|
|[ダイアログ::Pリントレンジ](#printrange)|指定した範囲のページだけを印刷するかどうかを決定します。|
|[ダイアログボックス::Pリント選択](#printselection)|現在選択されている項目だけを印刷するかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_pd](#m_pd)|オブジェクトをカスタマイズするために使用する`CPrintDialog`構造体。|

## <a name="remarks"></a>解説

共通の印刷ダイアログ ボックスを使用すると、Windows 標準に合った方法で [印刷] ダイアログ ボックスと [印刷設定] ダイアログ ボックスを簡単に実装できます。

> [!NOTE]
> この`CPrintDialogEx`クラスは、Windows 印刷プロパティ シートによって提供されるサービスをカプセル化します。 詳細については[、CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)の概要を参照してください。

`CPrintDialog`の機能は、印刷設定とページ設定の両方に共通のダイアログ ボックスを提供するように設計された[CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)の機能に置き換えられました。

アプリケーションの印刷プロセスのさまざまな側面を処理するために、フレームワークに依存できます。 この場合、フレームワークは Windows コモン ダイアログ ボックスを自動的に表示して印刷します。 また、アプリケーションの印刷をフレームワークで処理することもできますが、共通の [印刷] ダイアログ ボックスを独自の印刷ダイアログ ボックスで上書きすることもできます。 フレームワークを使用して印刷タスクを処理する方法の詳細については、「[印刷](../../mfc/printing.md)」を参照してください。

フレームワークの関与なしにアプリケーションで印刷を処理する場合は、提供されているコンストラクタで`CPrintDialog`クラスを "as" にするか、独自のダイアログ クラスを派生`CPrintDialog`させ、必要に応じてコンストラクタを記述します。 どちらの場合も、これらのダイアログ ボックスは class`CCommonDialog`から派生しているため、標準の MFC ダイアログ ボックスのように動作します。

オブジェクトを`CPrintDialog`使用するには、まずコンストラクタを使用してオブジェクト`CPrintDialog`を作成します。 ダイアログ ボックスを作成したら[、m_pd](#m_pd)構造の値を設定または変更して、ダイアログ ボックスのコントロールの値を初期化できます。 構造`m_pd`のタイプは[、PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)です。 この構造体の詳細については、Windows SDK を参照してください。

メンバー`m_pd``hDevMode`に`hDevNames`独自のハンドルを指定しない場合は、ダイアログ ボックスの操作が完了したら、これらの`GlobalFree`ハンドルの Windows 関数を呼び出してください。 によって`CWinApp::OnFilePrintSetup`提供されるフレームワークの印刷設定の実装を使用する場合、これらのハンドルを解放する必要はありません。 ハンドルは'デストラクタ`CWinApp`によって保持され、'デストラクタで`CWinApp`解放されます。 スタンドアロンを使用`CPrintDialog`する場合にのみ、これらのハンドルを解放する必要があります。

ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数を呼び出してダイアログ ボックスを表示し、ユーザーが印刷オプションを選択できるようにします。 `DoModal`は、ユーザーが OK (IDOK) ボタンまたはキャンセル (IDCANCEL) ボタンを選択したかどうかを返します。

IDOK を返す場合`DoModal`は、メンバー`CPrintDialog`関数の 1 つを使用して、ユーザーが入力した情報を取得できます。

`CPrintDialog::GetDefaults`このメンバー関数は、ダイアログ ボックスを表示せずに現在のプリンタの既定値を取得する場合に便利です。 このメンバー関数は、ユーザーの操作を必要としません。

Windows`CommDlgExtendedError`関数を使用して、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーの詳細を確認できます。 この関数の詳細については、Windows SDK を参照してください。

`CPrintDialog`は、COMMDLG に依存します。Windows バージョン 3.1 以降に付属の DLL ファイル。

ダイアログ ボックスをカスタマイズするには、 から`CPrintDialog`クラスを派生し、カスタム ダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 未処理のメッセージは、基本クラスに渡す必要があります。 フック機能のカスタマイズは不要です。

ダイアログ ボックスが [印刷] または [印刷設定] のいずれであるかによって同じメッセージを処理するには、ダイアログ ボックスごとにクラスを派生させる必要があります。 また、[印刷] ダイアログ`AttachOnSetup`ボックスで [印刷設定] ボタンが選択されている場合に、新しいダイアログ ボックスの作成を処理する Windows 関数をオーバーライドする必要があります。

の詳細`CPrintDialog`については、「 コモン[ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cprintdialogcprintdialog"></a><a name="cprintdialog"></a>ダイアログボックス::C印刷ダイアログ

Windows の [印刷] ダイアログ オブジェクトまたは [印刷設定] ダイアログ オブジェクトを構築します。

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*設定のみ印刷*<br/>
標準の Windows の [印刷] ダイアログ ボックスまたは [印刷設定] ダイアログ ボックスを表示するかどうかを指定します。 このパラメータを TRUE に設定すると、標準の Windows の [印刷設定] ダイアログ ボックスが表示されます。 [Windows の印刷] ダイアログ ボックスを表示するには、FALSE に設定します。 *bPrintSetupOnly*が FALSE の場合は、[印刷] ダイアログ ボックスに [印刷設定] オプション ボタンが表示されます。

*dwFlags*<br/>
ダイアログ ボックスの設定をカスタマイズするために使用できる 1 つ以上のフラグを、ビットごとの OR 演算子を使用して組み合わせます。 たとえば、PD_ALLPAGES フラグは、既定の印刷範囲を文書のすべてのページに設定します。 これらのフラグの詳細については、Windows SDK の[PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)構造体を参照してください。

*pParentWnd*<br/>
ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトのみを構築します。 このメンバー`DoModal`関数を使用して、ダイアログ ボックスを表示します。

*bPrintSetupOnly*を FALSE に設定してコンストラクターを呼び出すと、PD_RETURNDC フラグが自動的に使用されることに注意してください。 を`DoModal``GetDefaults`呼び出すと`GetPrinterDC`、 、 プリンター DC`m_pd.hDC`が に戻されます。 この DC は、`CPrintDialog`の呼び出し元によって[DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc)への呼び出しで解放される必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

## <a name="cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a>ダイアログ::プリンタDCの作成

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体と[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンター デバイス コンテキスト (DC) を作成します。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンター デバイス コンテキストへのハンドル。

### <a name="remarks"></a>解説

この DC は現在のプリンター DC であると想定され、以前に取得した他のプリンター DC はユーザーが削除する必要があります。 この関数は、[印刷] ダイアログ ボックスを表示せずに、呼び出し可能で、結果として DC を使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

## <a name="cprintdialogdomodal"></a><a name="domodal"></a>ダイアログ:Dモーダル

Windows 共通の印刷ダイアログ ボックスを表示し、部数、ページ範囲、部数を照合するかどうかなど、さまざまな印刷オプションを選択できます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK または ID キャンセル。 IDCANCEL が返された場合は、エラーが発生したかどうかを判断するのには関数[を](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)呼び出します。

IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

### <a name="remarks"></a>解説

構造体のメンバーを設定してさまざまな印刷ダイアログ オプションを`m_pd`初期化する場合は、 を呼び出す`DoModal`前に、ダイアログ オブジェクトが構築された後に行う必要があります。

を呼`DoModal`び出した後、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得できます。

*bPrintSetupOnly*を FALSE に設定してコンストラクターを呼び出すと、PD_RETURNDC フラグが自動的に使用されることに注意してください。 を`DoModal``GetDefaults`呼び出すと`GetPrinterDC`、 、 プリンター DC`m_pd.hDC`が に戻されます。 この DC は、`CPrintDialog`の呼び出し元によって[DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc)への呼び出しで解放される必要があります。

### <a name="example"></a>例

  [「印刷ダイアログ::CreatePrinterDC」の例を](#createprinterdc)参照してください。

## <a name="cprintdialoggetcopies"></a><a name="getcopies"></a>をクリックします。

要求されたコピーの数を取得します。

```
int GetCopies() const;
```

### <a name="return-value"></a>戻り値

要求されたコピーの数。

### <a name="remarks"></a>解説

要求されたコピーの数`DoModal`を取得するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::PrintCollate](#printcollate)の例を参照してください。

## <a name="cprintdialoggetdefaults"></a><a name="getdefaults"></a>をクリックします。

ダイアログ ボックスを表示せずに、既定のプリンターのデバイスの既定値を取得します。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

取得した値は、構造体に`m_pd`配置されます。

場合によっては、この関数を呼び出すと *、bPrintSetupOnly*が FALSE に設定された`CPrintDialog`[場合に、コンストラクター](#cprintdialog)が呼び出されます。 このような場合、プリンター DC および`hDevNames``hDevMode`(`m_pd`データ・メンバーにある 2 つのハンドル) が自動的に割り振られます。

のコンストラクタ`CPrintDialog`が*bPrintSetupOnly*を FALSE に設定して呼び出された場合`hDevNames`、`hDevMode`この関数`m_pd.hDevNames`は`m_pd.hDevMode`呼び出し元に戻って 、 と`m_pd.hDC`) に配置されるだけでなく、 でプリンター DC も返します。 呼び出し元は、オブジェクトの終了後に、プリンタ DC を削除し、ハンドルの Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)関数を呼び出す必要`CPrintDialog`があります。

### <a name="example"></a>例

このコードは、既定のプリンターのデバイス コンテキストを取得し、プリンターの解像度をドット/インチでユーザーに報告します。 (プリンターの機能のこの属性は、多くの場合、DPI と呼ばれます)。

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

## <a name="cprintdialoggetdevicename"></a><a name="getdevicename"></a>をクリックします。

現在選択されているプリンター デバイスの名前を取得します。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンタの名前。

### <a name="remarks"></a>解説

現在選択されているプリンタの名前を取得するために[DoModal](#domodal)を呼び出した後、または[GetDefaults](#getdefaults)を呼び出した後、この関数を呼び出して、既定のプリンターの現在のデバイスの既定値を取得します。 によって返`CString`される`GetDeviceName`オブジェクトへのポインターを、 `lpszDeviceName` [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)の呼び出しの値として使用します。

### <a name="example"></a>例

このコードは、ユーザーのデフォルトのプリンター名と接続先のポートと、プリンターが使用するスプーラ名を示しています。 このコードには、「既定のプリンタは、winspool を使用して \server\share\\上の HP LaserJet IIIP です」というメッセージ ボックスが表示される場合があります。

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

## <a name="cprintdialoggetdevmode"></a><a name="getdevmode"></a>ダイアログ::デヴモードを取得します。

構造体を取得`DEVMODE`します。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)データ構造体には、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体で使用されるメモリのロックを解除するには、Windows SDK で説明されている Windows[グローバル ロック解除](/windows/win32/api/winbase/nf-winbase-globalunlock)機能を使用する必要があります。

### <a name="remarks"></a>解説

印刷デバイスに関する情報を取得するには[、DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後にこの関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::PrintCollate](#printcollate)の例を参照してください。

## <a name="cprintdialoggetdrivername"></a><a name="getdrivername"></a>をクリックします。

現在選択されているプリンタ ドライバの名前を取得します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

システム`CString`定義のドライバー名を指定します。

### <a name="remarks"></a>解説

[DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後、この関数を呼び出して、システム定義のプリンター デバイス ドライバーの名前を取得します。 によって返`CString`される`GetDriverName`オブジェクトへのポインターを、 `lpszDriverName` [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)の呼び出しの値として使用します。

### <a name="example"></a>例

  [次](#getdevicename)の例を参照してください。

## <a name="cprintdialoggetfrompage"></a><a name="getfrompage"></a>ページから取得します。

印刷範囲の開始ページを取得します。

```
int GetFromPage() const;
```

### <a name="return-value"></a>戻り値

印刷するページ範囲の開始ページ番号。

### <a name="remarks"></a>解説

印刷するページ範囲の`DoModal`開始ページ番号を取得するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::m_pd](#m_pd)の例」を参照してください。

## <a name="cprintdialoggetportname"></a><a name="getportname"></a>をクリックします。

現在選択されているプリンタ ポートの名前を取得します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンタ ポートの名前。

### <a name="remarks"></a>解説

[DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後、この関数を呼び出して、現在選択されているプリンター ポートの名前を取得します。

### <a name="example"></a>例

  [次](#getdevicename)の例を参照してください。

## <a name="cprintdialoggetprinterdc"></a><a name="getprinterdc"></a>ダイアログ::ゲットプリンターDC

プリンターデバイス コンテキストへのハンドルを取得します。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、プリンターデバイス コンテキストへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

コンストラクタの*bPrintSetupOnly*パラメータが FALSE ([印刷] ダイアログ ボックスが表示`GetPrinterDC`されることを示す) の場合は、プリンタデバイスコンテキストへのハンドルを返します。 `CPrintDialog` デバイス コンテキストを使用し終わったら、Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc)関数を呼び出して削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

## <a name="cprintdialoggettopage"></a><a name="gettopage"></a>ダイアログ::取得ページ

印刷範囲の終了ページを取得します。

```
int GetToPage() const;
```

### <a name="return-value"></a>戻り値

印刷するページ範囲の終了ページ番号。

### <a name="remarks"></a>解説

印刷するページ範囲の`DoModal`終了ページ番号を取得するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::m_pd](#m_pd)の例」を参照してください。

## <a name="cprintdialogm_pd"></a><a name="m_pd"></a>ダイアログ::m_pd

メンバがダイアログ オブジェクトの特性を格納する構造体。

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>解説

オブジェクトを`CPrintDialog`作成した後[、DoModal](#domodal) `m_pd`メンバー関数を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定できます。 構造の詳細については、Windows SDK の`m_pd`[印刷を](/windows/win32/api/commdlg/ns-commdlg-printdlga)参照してください。

データ メンバーを`m_pd`直接変更すると、既定の動作がオーバーライドされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

## <a name="cprintdialogprintall"></a><a name="printall"></a>を :Pクリックします。

文書のすべてのページを印刷するかどうかを決定します。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>戻り値

文書内のすべてのページを印刷する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ドキュメント内のすべてのページを`DoModal`印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::m_pd](#m_pd)の例」を参照してください。

## <a name="cprintdialogprintcollate"></a><a name="printcollate"></a>:Pリントコルレート

照合されたコピーが要求されているかどうかを判断します。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>戻り値

ユーザーがダイアログ ボックスで [照合] チェック ボックスをオンにした場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数を呼び`DoModal`出した後、印刷されたドキュメントのすべてのコピーを印刷するかどうかを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

## <a name="cprintdialogprintrange"></a><a name="printrange"></a>ダイアログ::Pリントレンジ

指定した範囲のページだけを印刷するかどうかを決定します。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>戻り値

文書内のページ範囲のみを印刷する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ドキュメント内のページ範囲`DoModal`のみを印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::m_pd](#m_pd)の例」を参照してください。

## <a name="cprintdialogprintselection"></a><a name="printselection"></a>ダイアログボックス::Pリント選択

現在選択されている項目だけを印刷するかどうかを決定します。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>戻り値

選択した項目だけを印刷する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

現在選択されている項目だけを`DoModal`印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

### <a name="example"></a>例

  [「CPrintDialog::m_pd](#m_pd)の例」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ディブルック](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
