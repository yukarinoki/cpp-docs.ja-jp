---
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
ms.openlocfilehash: 79d696f89ca7474220559abbf5464f32b6e684c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543326"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx クラス

Windows 印刷のプロパティ シートによって提供されるサービスをカプセル化します。

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
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|印刷ダイアログ ボックスを表示せず、プリンター デバイス コンテキストを作成します。|
|[CPrintDialogEx::DoModal](#domodal)|ダイアログ ボックスを表示でき、項目を選択するユーザー。|
|[CPrintDialogEx::GetCopies](#getcopies)|要求されたコピーの数を取得します。|
|[CPrintDialogEx::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|
|[CPrintDialogEx::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|
|[CPrintDialogEx::GetDriverName](#getdrivername)|プリンターのシステム定義のデバイス ドライバーの名前を取得します。|
|[CPrintDialogEx::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストを識別するハンドルを取得します。|
|[CPrintDialogEx::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを決定します。|
|[CPrintDialogEx::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを決定します。|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|ドキュメントの現在のページを印刷するかどうかを決定します。|
|[CPrintDialogEx::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを決定します。|
|[CPrintDialogEx::PrintSelection](#printselection)|現在選択されている項目のみを印刷するかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|構造体をカスタマイズするために使用する`CPrintDialogEx`オブジェクト。|

## <a name="remarks"></a>Remarks

アプリケーションの印刷プロセスの多くの側面を処理するために、フレームワークに依存することができます。 印刷タスクを処理するために、フレームワークの使用に関する詳細については、記事を参照してください。[印刷](../../mfc/printing.md)します。

フレームワークの関与なし印刷を処理するために、アプリケーションを実行する場合は、使用、`CPrintDialogEx`現状有姿を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialogEx`と、ニーズに合わせてコンス トラクターを記述します。 いずれの場合も、これらのダイアログ ボックスと同様に標準の MFC ダイアログ ボックス クラスから派生しているため`CCommonDialog`します。

使用する、`CPrintDialogEx`オブジェクトは、まずを使用してオブジェクトを作成、`CPrintDialogEx`コンス トラクター。 ダイアログ ボックスが構築されると、設定または任意の値を変更、 [m_pdex](#m_pdex)構造 ダイアログ ボックスのコントロールの値を初期化します。 `m_pdex`型の構造は、 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa)します。 この構造体の詳細については、Windows SDK を参照してください。

ハンドルを指定しない場合`m_pdex`の`hDevMode`と`hDevNames`メンバー、Windows 関数を呼び出すことを確認する`GlobalFree`の ダイアログ ボックスが済んだら、これらのハンドル。

ダイアログ ボックスのコントロールを初期化した後に呼び出し、 `DoModal`  ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにするメンバー関数。 ときに`DoModal`返します、ユーザーが [ok]、適用、または [キャンセル] ボタンを選択するかどうかを指定できます。

使用することができる場合、ユーザーが [ok] を押す`CPrintDialogEx`のユーザーによって入力された情報を取得するメンバー関数。

`CPrintDialogEx::GetDefaults`メンバー関数は、ダイアログ ボックスを表示せず、現在のプリンターの既定値を取得するために役立ちます。 このメソッドには、ユーザーの介入は不要です。

Windows を使用する`CommDlgExtendedError` ダイアログ ボックスの初期化中にエラーが発生したかどうかを判断して、エラーに関する詳細については、関数。 この関数の詳細については、Windows SDK を参照してください。

使用しての詳細については`CPrintDialogEx`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。

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

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Windows 印刷のプロパティ シートを構築します。

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
1 つまたは複数のフラグがダイアログ ボックスで、ビットごとの OR 演算子を使用して結合の設定のカスタマイズに使用することができます。 たとえば、PD_ALLPAGES フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa)これらのフラグの詳細については、Windows SDK で構造体。

*pParentWnd*<br/>
ウィンドウ、ダイアログ ボックスの親またはオーナー ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、のみ、オブジェクトを構築します。 使用して、`DoModal`メンバー関数は、ダイアログ ボックスを表示します。

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンター デバイス コンテキストへのハンドルします。

### <a name="remarks"></a>Remarks

返された DC にも格納されて、`hDC`のメンバー [m_pdex](#m_pdex)します。

この DC は DC では、現在のプリンターと見なされ、以前に取得したその他のプリンターの Dc を削除する必要があります。 この関数を呼び出すことができ、[印刷] ダイアログ ボックスを表示せず、結果として得られる DC を使用します。

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Windows 印刷のプロパティ シートを表示し、ユーザーがページの範囲のコピーの数などのさまざまな印刷オプションを選択できるようにするには、この関数を呼び出してコピーが照合されるかどうかとします。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

INT_PTR では、値が実際には、HRESULT を返します。 戻り値を参照してください[PrintDlgEx](https://msdn.microsoft.com/library/windows/desktop/ms646942) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまな印刷ダイアログ ボックスのオプションを初期化する場合、`m_pdex`構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

呼び出した後`DoModal`、他のメンバー、ダイアログ ボックスに、設定やユーザーによって入力された情報を取得する関数を呼び出すことができます。

呼び出すときに、PD_RETURNDC フラグを使用する場合`DoModal`ではプリンター DC が返されます、`hDC`のメンバー [m_pdex](#m_pdex)します。 この DC を呼び出して解放する必要があります[とき](/windows/desktop/api/wingdi/nf-wingdi-deletedc)の呼び出し元によって`CPrintDialogEx`します。

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

この関数を呼び出した後`DoModal`コピー要求の数を取得します。

```
int GetCopies() const;
```

### <a name="return-value"></a>戻り値

要求されたコピーの数。

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

ダイアログ ボックスを表示せず、既定のプリンターの既定のデバイスを取得するには、この関数を呼び出します。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>戻り値

TRUE の場合は成功しましたが、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。

`GetDefaults` 印刷のプロパティ シートに表示されません。 代わりに、設定、`hDevNames`と`hDevMode`のメンバー [m_pdex](#m_pdex)へのハンドルを[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体の初期化されている、システムの既定のプリンターです。 両方`hDevNames`と`hDevMode`が NULL の場合、または`GetDefaults`は失敗します。

PD_RETURNDC フラグが設定になっているかどうかはこの関数はしか返しません`hDevNames`と`hDevMode`(である`m_pdex.hDevNames`と`m_pdex.hDevMode`)、呼び出し元にはプリンター DC で返すことも`m_pdex.hDC`します。 プリンター DC を削除して、Windows の呼び出しの呼び出し元の責任[GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree)関数が終了したら、ハンドルを`CPrintDialogEx`オブジェクト。

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンターの名前を取得する[ため](#getdefaults)既定のプリンターの名前を取得します。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンターの名前。

### <a name="remarks"></a>Remarks

ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)データ構造は、デバイスの初期化と印刷ドライバーの環境に関する情報が含まれています。 この構造体で、Windows によって使用されたメモリのロックを解除する必要があります[GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock)関数は、Windows SDK で説明します。

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)プリンターのシステム定義のデバイス ドライバーの名前を取得します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

A `CString` driver のシステム定義の名前を指定します。

### <a name="remarks"></a>Remarks

ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として*lpszDriverName*への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)現在選択されているプリンター ポートの名前を取得します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンター ポートの名前。

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

プリンター デバイス コンテキストへのハンドルを返します。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>戻り値

プリンター デバイス コンテキストへのハンドル。

### <a name="remarks"></a>Remarks

Windows を呼び出す必要があります[とき](/windows/desktop/api/wingdi/nf-wingdi-deletedc)が終わったら、デバイス コンテキストを削除する関数を使用します。

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

メンバーを持つダイアログ オブジェクトの特性を格納する PRINTDLGEX 構造体。

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Remarks

構築した後、`CPrintDialogEx`オブジェクトを使用することができます`m_pdex`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pdex`構造体は、「 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK に含まれています。

変更する場合、`m_pdex`データ メンバーを直接、既定の動作をオーバーライドします。

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>戻り値

ドキュメント内のすべてのページを印刷する場合は TRUEそれ以外の場合は FALSE です。

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

この関数を呼び出した後`DoModal`をプリンターにドキュメントの印刷したすべてのコピーを照合する必要があるかどうかを判断します。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>戻り値

ユーザーが、ダイアログ ボックスで、部単位で印刷 チェック ボックスを選択する場合は TRUE。それ以外の場合は FALSE です。

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

この関数を呼び出した後`DoModal`をドキュメント内の現在のページを印刷するかどうかを判断します。

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合**現在のページを印刷**される印刷ダイアログ ボックスで選択した場合は FALSE です。

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>戻り値

印刷するドキュメントのページの範囲のみ場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

指定したページ範囲を決定できます[m_pdex](#m_pdex) (を参照してください`nPageRanges`、 `nMaxPageRanges`、および`lpPageRanges`で、 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK の構造)。

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

この関数を呼び出した後`DoModal`を現在選択されている項目のみを印刷するかどうかを判断します。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>戻り値

選択した項目が印刷するのには専用場合は TRUE。それ以外の場合は FALSE です。

## <a name="see-also"></a>関連項目

[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
