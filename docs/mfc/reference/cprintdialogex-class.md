---
description: '詳細情報: CPrintDialogEx クラス'
title: CPrintDialogEx クラス
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 2f0d124422efa641c3ace833a5970b364a5cbc48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301465"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx クラス

Windows の [印刷] プロパティシートによって提供されるサービスをカプセル化します。

## <a name="syntax"></a>構文

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|`CPrintDialogEx` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPrintDialogEx:: Createプリンター Dc](#createprinterdc)|[印刷] ダイアログボックスを表示せずに、プリンターデバイスコンテキストを作成します。|
|[CPrintDialogEx::D oModal](#domodal)|ダイアログボックスを表示し、ユーザーが選択できるようにします。|
|[CPrintDialogEx:: GetCopies](#getcopies)|要求されたコピーの数を取得します。|
|[CPrintDialogEx::GetDefaults](#getdefaults)|ダイアログボックスを表示せずに、デバイスの既定値を取得します。|
|[CPrintDialogEx:: GetDeviceName](#getdevicename)|現在選択されているプリンターデバイスの名前を取得します。|
|[CPrintDialogEx:: GetDevMode](#getdevmode)|`DEVMODE`構造体を取得します。|
|[CPrintDialogEx:: GetDriverName ドライバー](#getdrivername)|システム定義のプリンターデバイスドライバーの名前を取得します。|
|[CPrintDialogEx::GetPortName](#getportname)|現在選択されているプリンターポートの名前を取得します。|
|[CPrintDialogEx:: Getプリンター Dc](#getprinterdc)|プリンターデバイスコンテキストへのハンドルを取得します。|
|[CPrintDialogEx::P rintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを決定します。|
|[CPrintDialogEx::P rintCollate](#printcollate)|照合されたコピーが要求されるかどうかを決定します。|
|[CPrintDialogEx::P rintCurrentPage](#printcurrentpage)|ドキュメントの現在のページを印刷するかどうかを決定します。|
|[CPrintDialogEx::P Rの破壊](#printrange)|指定した範囲のページだけを印刷するかどうかを決定します。|
|[CPrintDialogEx::P rintSelection](#printselection)|現在選択されている項目だけを印刷するかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPrintDialogEx:: m_pdex](#m_pdex)|オブジェクトをカスタマイズするために使用される構造体 `CPrintDialogEx` 。|

## <a name="remarks"></a>解説

フレームワークに依存して、アプリケーションの印刷プロセスの多くの要素を処理できます。 フレームワークを使用して印刷タスクを処理する方法の詳細については、「 [印刷](../../mfc/printing.md)」を参照してください。

アプリケーションで、フレームワークの関与なしに印刷を処理する場合 `CPrintDialogEx` は、提供されたコンストラクターを使用して "そのまま" クラスを使用するか、から独自のダイアログクラスを派生させ、 `CPrintDialogEx` 必要に応じてコンストラクターを記述することができます。 どちらの場合も、これらのダイアログボックスはクラスから派生しているので、標準の MFC ダイアログボックスのように動作 `CCommonDialog` します。

オブジェクトを使用するには、 `CPrintDialogEx` 最初にコンストラクターを使用してオブジェクトを作成し `CPrintDialogEx` ます。 ダイアログボックスが構築されたら、 [m_pdex](#m_pdex) 構造体の任意の値を設定または変更して、ダイアログボックスのコントロールの値を初期化できます。 `m_pdex`構造体の型は[Printdlgex](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)です。 この構造の詳細については、Windows SDK を参照してください。

メンバーとメンバーに対して独自のハンドルを指定しない場合は、 `m_pdex` `hDevMode` `hDevNames` `GlobalFree` ダイアログボックスが終了したときに、これらのハンドルに対して Windows の関数を呼び出す必要があります。

ダイアログボックスコントロールを初期化した後、 `DoModal` メンバー関数を呼び出してダイアログボックスを表示し、ユーザーが印刷オプションを選択できるようにします。 から `DoModal` 制御が戻ったときに、ユーザーが [OK]、[適用]、または [キャンセル] ボタンを選択したかどうかを確認できます。

ユーザーが [OK] を押した場合は、 `CPrintDialogEx` のメンバー関数を使用して、ユーザーが入力した情報を取得できます。

この `CPrintDialogEx::GetDefaults` メンバー関数は、ダイアログボックスを表示せずに現在のプリンターの既定値を取得する場合に便利です。 このメソッドでは、ユーザーの操作は必要ありません。

Windows の関数を使用する `CommDlgExtendedError` と、ダイアログボックスの初期化中にエラーが発生したかどうかを判断し、エラーの詳細を確認できます。 この関数の詳細については、Windows SDK を参照してください。

の使用方法の詳細につい `CPrintDialogEx` ては、「 [コモンダイアログクラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>要件

**ヘッダー:** afxdlgs

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a> CPrintDialogEx::CPrintDialogEx

Windows 印刷プロパティシートを構築します。

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ダイアログボックスの設定をカスタマイズするために使用できる1つ以上のフラグ。ビットごとの OR 演算子を使用して結合します。 たとえば、PD_ALLPAGES フラグは、既定の印刷範囲をドキュメントのすべてのページに設定します。 これらのフラグの詳細については、Windows SDK の [Printdlgex](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 構造体を参照してください。

*pParentWnd*<br/>
ダイアログボックスの親またはオーナーウィンドウへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトを構築するだけです。 この `DoModal` ダイアログボックスを表示するには、メンバー関数を使用します。

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a> CPrintDialogEx:: Createプリンター Dc

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)および[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンターデバイスコンテキスト (DC) を作成します。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンターデバイスコンテキストを処理します。

### <a name="remarks"></a>解説

返された DC は、m_pdex のメンバーにも格納され `hDC` ます。 [](#m_pdex)

この DC は現在のプリンタ DC であると想定されており、以前に取得した他のすべてのプリンタ dc を削除する必要があります。 この関数は、[印刷] ダイアログボックスを表示せずに、結果として使用される DC を呼び出すことができます。

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a> CPrintDialogEx::D oModal

この関数を呼び出すと、Windows の印刷プロパティシートが表示され、ユーザーはさまざまな印刷オプション (コピー数、ページ範囲、およびコピーを照合するかどうかなど) を選択できます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

戻り値 INT_PTR は実際には HRESULT です。 Windows SDK の「 [Printdlgex](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) 」の「戻り値」セクションを参照してください。

### <a name="remarks"></a>解説

構造体のメンバーを設定することによって、さまざまな印刷ダイアログオプションを初期化する場合は `m_pdex` 、を呼び出す前に `DoModal` 、ダイアログオブジェクトが構築された後にこの操作を行う必要があります。

を呼び出した後 `DoModal` 、他のメンバー関数を呼び出して、ユーザーがダイアログボックスに入力した設定または情報を取得できます。

を呼び出すときに PD_RETURNDC フラグが使用されている場合は `DoModal` 、m_pdex のメンバーにプリンター DC が返され `hDC` ます。 [](#m_pdex) この DC は、の呼び出し元によって [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) への呼び出しを使用して解放する必要があり `CPrintDialogEx` ます。

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a> CPrintDialogEx:: GetCopies

を呼び出した後 `DoModal` に、要求されたコピーの数を取得するために、この関数を呼び出します。

```
int GetCopies() const;
```

### <a name="return-value"></a>戻り値

要求されたコピーの数。

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a> CPrintDialogEx::GetDefaults

ダイアログボックスを表示せずに、既定のプリンターのデバイスの既定値を取得するには、この関数を呼び出します。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)および[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンターデバイスコンテキスト (DC) を作成します。

`GetDefaults` [印刷] プロパティシートは表示されません。 代わりに、 `hDevNames` `hDevMode` [m_pdex](#m_pdex) のメンバーとメンバーを、システムの既定のプリンター用に初期化された [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) および [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 構造体に処理するように設定します。 `hDevNames`とはどちらも `hDevMode` NULL であるか、 `GetDefaults` 失敗します。

PD_RETURNDC フラグが設定されている場合、この関数は `hDevNames` 、 `hDevMode` 呼び出し元に対してと (およびにあります) のみを返し `m_pdex.hDevNames` `m_pdex.hDevMode` ますが、ではプリンター DC も返し `m_pdex.hDC` ます。 オブジェクトの操作が完了したら、プリンター DC を削除して、ハンドルに対して Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) 関数を呼び出す必要があり `CPrintDialogEx` ます。

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a> CPrintDialogEx:: GetDeviceName

この関数は、 [DoModal](#domodal) を呼び出して現在選択されているプリンターの名前を取得した後、または [GetDefaults](#getdefaults) を呼び出して既定のプリンターの名前を取得した後に呼び出されます。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンターの名前。

### <a name="remarks"></a>解説

`CString` `GetDeviceName` `lpszDeviceName` [CDC:: createdc](../../mfc/reference/cdc-class.md#createdc)への呼び出しで、によって返されるオブジェクトへのポインターを、の値として使用します。

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a> CPrintDialogEx:: GetDevMode

[DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後に、この関数を呼び出して、印刷デバイスに関する情報を取得します。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)データ構造体。これには、印刷ドライバーのデバイスの初期化と環境に関する情報が含まれます。 この構造体によって取得されるメモリは、Windows [globalunlock](/windows/win32/api/winbase/nf-winbase-globalunlock) 関数を使用してロック解除する必要があります。これについては、Windows SDK を参照してください。

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a> CPrintDialogEx:: GetDriverName ドライバー

システム定義のプリンターデバイスドライバーの名前を取得するには、 [DoModal](#domodal) または [GetDefaults](#getdefaults) を呼び出した後にこの関数を呼び出します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

`CString`システム定義のドライバー名を指定する。

### <a name="remarks"></a>解説

`CString`によって返されたオブジェクトへのポインターを、 `GetDriverName` [CDC:: createdc](../../mfc/reference/cdc-class.md#createdc)への呼び出しで *lpszdrivername* の値として使用します。

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a> CPrintDialogEx::GetPortName

現在選択されているプリンターポートの名前を取得するために、 [DoModal](#domodal) または [GetDefaults](#getdefaults) を呼び出した後に、この関数を呼び出します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンターポートの名前。

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a> CPrintDialogEx:: Getプリンター Dc

プリンターデバイスコンテキストへのハンドルを返します。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>戻り値

プリンターデバイスコンテキストを処理するハンドル。

### <a name="remarks"></a>解説

使用が完了したら、Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) 関数を呼び出して、デバイスコンテキストを削除する必要があります。

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a> CPrintDialogEx:: m_pdex

Dialog オブジェクトの特性を格納するメンバーを持つ PRINTDLGEX 構造体。

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>解説

オブジェクトを構築した後 `CPrintDialogEx` 、を使用し `m_pdex` て、ダイアログボックスのさまざまな側面を設定してから、 [DoModal](#domodal) メンバー関数を呼び出すことができます。 構造の詳細につい `m_pdex` ては、Windows SDK の「 [Printdlgex](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 」を参照してください。

データメンバーを直接変更すると `m_pdex` 、すべての既定の動作がオーバーライドされます。

## <a name="cprintdialogexprintall"></a><a name="printall"></a> CPrintDialogEx::P rintAll

を呼び出した後に `DoModal` 、ドキュメント内のすべてのページを印刷するかどうかを判断するために、この関数を呼び出します。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>戻り値

ドキュメント内のすべてのページを印刷する場合は TRUE。それ以外の場合は FALSE。

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a> CPrintDialogEx::P rintCollate

を呼び出した後に、この関数を呼び出し `DoModal` て、プリンターがドキュメントのすべての印刷コピーを照合する必要があるかどうかを判断します。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>戻り値

ユーザーがダイアログボックスの [部単位で印刷] チェックボックスをオンにする場合は TRUE。それ以外の場合は FALSE。

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a> CPrintDialogEx::P rintCurrentPage

を呼び出した後に、 `DoModal` ドキュメント内の現在のページを印刷するかどうかを判断するために、この関数を呼び出します。

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>戻り値

[印刷] ダイアログボックスで [ **現在のページを印刷** する] が選択されている場合は TRUE です。それ以外の場合は FALSE。

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a> CPrintDialogEx::P Rの破壊

を呼び出した後に、この関数を呼び出し `DoModal` て、文書内のページの範囲だけを印刷するかどうかを決定します。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>戻り値

ドキュメント内のページの範囲だけを印刷する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定されたページ範囲は [m_pdex](#m_pdex) から判別でき `nPageRanges` `nMaxPageRanges` ます ( `lpPageRanges` Windows SDK の [printdlgex](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 構造体で、、およびを参照してください)。

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a> CPrintDialogEx::P rintSelection

を呼び出した後に `DoModal` 、現在選択されている項目だけを印刷するかどうかを判断するために、この関数を呼び出します。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>戻り値

選択した項目のみを印刷する場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
