---
title: クラス
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
ms.openlocfilehash: 52e992cf021a592198daeddf0a4321fcea487f72
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364042"
---
# <a name="cprintdialogex-class"></a>クラス

Windows 印刷プロパティ シートによって提供されるサービスをカプセル化します。

## <a name="syntax"></a>構文

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#cprintdialogex)|`CPrintDialogEx` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の処理を行います。](#createprinterdc)|[印刷] ダイアログ ボックスを表示せずに、プリンター デバイス コンテキストを作成します。|
|[:Dモーダル](#domodal)|ダイアログ ボックスを表示し、ユーザーが選択できるようにします。|
|[を取得します。](#getcopies)|要求されたコピーの数を取得します。|
|[を取得します。](#getdefaults)|ダイアログ ボックスを表示せずにデバイスの既定値を取得します。|
|[を使用します。](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|
|[をクリックします。](#getdevmode)|構造体を取得`DEVMODE`します。|
|[を取得します。](#getdrivername)|システム定義のプリンター デバイス ドライバーの名前を取得します。|
|[をクリックします。](#getportname)|現在選択されているプリンタ ポートの名前を取得します。|
|[をクリックします。](#getprinterdc)|プリンターデバイス コンテキストへのハンドルを取得します。|
|[:Pリントすべて](#printall)|文書のすべてのページを印刷するかどうかを決定します。|
|[:Pリントコルレート](#printcollate)|照合されたコピーが要求されているかどうかを判断します。|
|[:Pリントカレントページ](#printcurrentpage)|文書の現在のページを印刷するかどうかを決定します。|
|[:Pリントレンジ](#printrange)|指定した範囲のページだけを印刷するかどうかを決定します。|
|[:P](#printselection)|現在選択されている項目だけを印刷するかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[m_pdex](#m_pdex)|オブジェクトをカスタマイズするために使用する`CPrintDialogEx`構造体。|

## <a name="remarks"></a>解説

アプリケーションの印刷プロセスのさまざまな側面を処理するために、フレームワークに依存できます。 フレームワークを使用して印刷タスクを処理する方法の詳細については、「[印刷](../../mfc/printing.md)」を参照してください。

フレームワークの関与なしにアプリケーションで印刷を処理する場合は、提供されているコンストラクタで`CPrintDialogEx`クラスを "as" にするか、独自のダイアログ クラスを派生`CPrintDialogEx`させ、必要に応じてコンストラクタを記述します。 どちらの場合も、これらのダイアログ ボックスは class`CCommonDialog`から派生しているため、標準の MFC ダイアログ ボックスのように動作します。

オブジェクトを`CPrintDialogEx`使用するには、まずコンストラクタを使用してオブジェクト`CPrintDialogEx`を作成します。 ダイアログ ボックスを作成したら[、m_pdex](#m_pdex)構造体の値を設定または変更して、ダイアログ ボックスのコントロールの値を初期化できます。 構造体`m_pdex`の型は[、PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)です。 この構造体の詳細については、Windows SDK を参照してください。

メンバー`m_pdex``hDevMode`に`hDevNames`独自のハンドルを指定しない場合は、ダイアログ ボックスの操作が完了したら、これらの`GlobalFree`ハンドルの Windows 関数を呼び出してください。

ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数を呼び出してダイアログ ボックスを表示し、ユーザーが印刷オプションを選択できるようにします。 戻`DoModal`り値が返された場合、ユーザーが [OK]、[適用]、または [キャンセル] ボタンを選択したかどうかを確認できます。

ユーザーが [OK] をクリック`CPrintDialogEx`した場合は、メンバー関数を使用して、ユーザーが入力した情報を取得できます。

`CPrintDialogEx::GetDefaults`このメンバー関数は、ダイアログ ボックスを表示せずに現在のプリンタの既定値を取得する場合に便利です。 このメソッドは、ユーザーの操作を必要としません。

Windows`CommDlgExtendedError`関数を使用して、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーの詳細を確認できます。 この関数の詳細については、Windows SDK を参照してください。

の詳細`CPrintDialogEx`については、「 コモン[ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>をクリックします。

Windows 印刷プロパティ シートを作成します。

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ダイアログ ボックスの設定をカスタマイズするために使用できる 1 つ以上のフラグを、ビットごとの OR 演算子を使用して組み合わせます。 たとえば、PD_ALLPAGES フラグは、既定の印刷範囲を文書のすべてのページに設定します。 これらのフラグの詳細については、Windows SDK の[PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)構造体を参照してください。

*pParentWnd*<br/>
ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトのみを構築します。 このメンバー`DoModal`関数を使用して、ダイアログ ボックスを表示します。

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>次の処理を行います。

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体と[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンター デバイス コンテキスト (DC) を作成します。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンター デバイス コンテキストへのハンドル。

### <a name="remarks"></a>解説

返された DC も`hDC`[m_pdex](#m_pdex)のメンバーに格納されます。

この DC は現在のプリンター DC であると想定され、以前に取得した他のプリンター DC は削除する必要があります。 この関数は、[印刷] ダイアログ ボックスを表示せずに、呼び出し可能で、結果として DC を使用できます。

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a>:Dモーダル

この関数を呼び出すと、Windows Print プロパティ シートが表示され、ユーザーは部数、ページ範囲、部単位の印刷を行うかどうかなど、さまざまな印刷オプションを選択できます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

INT_PTR戻り値は、実際には HRESULT です。 Windows SDK の[PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\))の戻り値セクションを参照してください。

### <a name="remarks"></a>解説

構造体のメンバーを設定してさまざまな印刷ダイアログ オプションを`m_pdex`初期化する場合は、 を呼び出す`DoModal`前に、ダイアログ オブジェクトが構築された後に行う必要があります。

を呼`DoModal`び出した後、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得できます。

PD_RETURNDC フラグが呼び出し`DoModal`時に使用されている場合は、 `hDC` [m_pdex](#m_pdex)のメンバーにプリンター DC が返されます。 この DC は、`CPrintDialogEx`の呼び出し元によって[DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc)への呼び出しで解放される必要があります。

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a>を取得します。

要求されたコピーの数`DoModal`を取得するために呼び出した後、この関数を呼び出します。

```
int GetCopies() const;
```

### <a name="return-value"></a>戻り値

要求されたコピーの数。

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a>を取得します。

ダイアログ ボックスを表示せずに、既定のプリンターのデバイスの既定値を取得します。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>戻り値

TRUE が成功した場合は FALSE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体と[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンター デバイス コンテキスト (DC) を作成します。

`GetDefaults`では、印刷プロパティ シートは表示されません。 代わりに[、m_pdex](#m_pdex)の`hDevNames`メンバー`hDevMode`と、 および をシステムのデフォルト・プリンター用に初期化される[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体および[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体にハンドルするように設定します。 両方`hDevNames`とも`hDevMode`NULL`GetDefaults`にする必要があります。

PD_RETURNDC フラグが設定されている場合、この関数は呼び`hDevNames`出`hDevMode`し元に`m_pdex.hDevNames`返`m_pdex.hDevMode`すだけでなく、 ( に指定されている ) を`m_pdex.hDC`呼び出し元に返すだけでなく、 でプリンタ DC も返します。 呼び出し元は、オブジェクトの終了後に、プリンタ DC を削除し、ハンドルの Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)関数を呼び出す必要`CPrintDialogEx`があります。

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a>を使用します。

現在選択されているプリンタの名前を取得するために[DoModal](#domodal)を呼び出した後、または[GetDefaults](#getdefaults)を呼び出して既定のプリンタの名前を取得した後、この関数を呼び出します。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンタの名前。

### <a name="remarks"></a>解説

によって返`CString`される`GetDeviceName`オブジェクトへのポインターを、 `lpszDeviceName` [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)の呼び出しの値として使用します。

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a>をクリックします。

印刷デバイスに関する情報を取得するには[、DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後にこの関数を呼び出します。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)データ構造体には、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体で使用されるメモリのロックを解除するには、Windows SDK で説明されている Windows[グローバル ロック解除](/windows/win32/api/winbase/nf-winbase-globalunlock)機能を使用する必要があります。

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a>を取得します。

[DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後、この関数を呼び出して、システム定義のプリンター デバイス ドライバーの名前を取得します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

システム`CString`定義のドライバー名を指定します。

### <a name="remarks"></a>解説

`CString`によって返された`GetDriverName`オブジェクトへのポインターを[、CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)の呼び出しで*lpszDriverName*の値として使用します。

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a>をクリックします。

[DoModal](#domodal)または[GetDefaults](#getdefaults)を呼び出した後、この関数を呼び出して、現在選択されているプリンター ポートの名前を取得します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンタ ポートの名前。

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>をクリックします。

プリンターデバイス コンテキストへのハンドルを返します。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>戻り値

プリンターデバイス コンテキストへのハンドル。

### <a name="remarks"></a>解説

デバイス コンテキストを使用し終わったら、Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc)関数を呼び出して削除する必要があります。

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a>m_pdex

メンバがダイアログ オブジェクトの特性を格納する PRINTDLGEX 構造体。

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>解説

オブジェクトを`CPrintDialogEx`作成した後[、DoModal](#domodal) `m_pdex`メンバー関数を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定できます。 構造の詳細については、Windows SDK の`m_pdex`[印刷を](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)参照してください。

データ メンバーを`m_pdex`直接変更すると、既定の動作がオーバーライドされます。

## <a name="cprintdialogexprintall"></a><a name="printall"></a>:Pリントすべて

ドキュメント内のすべてのページを`DoModal`印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>戻り値

文書内のすべてのページを印刷する場合は TRUE。それ以外の場合は FALSE。

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a>:Pリントコルレート

この関数を呼び`DoModal`出した後、印刷されたドキュメントのすべてのコピーを印刷するかどうかを確認します。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>戻り値

ユーザーがダイアログ ボックスで [照合] チェック ボックスをオンにした場合は TRUE。それ以外の場合は FALSE。

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>:Pリントカレントページ

ドキュメント内の現在の`DoModal`ページを印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>戻り値

印刷ダイアログで **[現在のページを印刷**] が選択されている場合は TRUE。それ以外の場合は FALSE。

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a>:Pリントレンジ

ドキュメント内のページ範囲`DoModal`のみを印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>戻り値

文書内のページ範囲のみを印刷する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定されたページ範囲は[、m_pdex](#m_pdex)から決定できます`nPageRanges`(Windows `lpPageRanges` SDK の[PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)構造体`nMaxPageRanges`、 、および を参照してください)。

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a>:P

現在選択されている項目だけを`DoModal`印刷するかどうかを確認するために呼び出した後、この関数を呼び出します。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>戻り値

選択した項目だけを印刷する場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
