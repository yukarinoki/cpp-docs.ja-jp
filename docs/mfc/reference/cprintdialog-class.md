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
ms.openlocfilehash: 3e86ce3e0179ff7c7a47a7083b6c168fea91ccbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662437"
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
|[CPrintDialog::CPrintDialog](#cprintdialog)|`CPrintDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|印刷ダイアログ ボックスを表示せず、プリンター デバイス コンテキストを作成します。|
|[CPrintDialog::DoModal](#domodal)|ダイアログ ボックスを表示しを選択できます。|
|[CPrintDialog::GetCopies](#getcopies)|要求されたコピーの数を取得します。|
|[CPrintDialog::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|
|[CPrintDialog::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|
|[CPrintDialog::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|
|[CPrintDialog::GetDriverName](#getdrivername)|現在選択されているプリンター ドライバーの名前を取得します。|
|[CPrintDialog::GetFromPage](#getfrompage)|印刷範囲の開始ページを取得します。|
|[CPrintDialog::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストを識別するハンドルを取得します。|
|[CPrintDialog::GetToPage](#gettopage)|印刷範囲の終了 ページを取得します。|
|[CPrintDialog::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを決定します。|
|[CPrintDialog::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを決定します。|
|[CPrintDialog::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを決定します。|
|[CPrintDialog::PrintSelection](#printselection)|現在選択されている項目のみを印刷するかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|構造体をカスタマイズするために使用する`CPrintDialog`オブジェクト。|

## <a name="remarks"></a>Remarks

一般的な印刷ダイアログ ボックスでは、Windows の標準に準拠した方法で印刷および印刷のセットアップ ダイアログ ボックスを実装する簡単な方法を提供します。

> [!NOTE]
>  `CPrintDialogEx`クラスは、Windows 印刷のプロパティ シートによって提供されるサービスをカプセル化します。 詳細については、次を参照してください。、 [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)の概要。

`CPrintDialog`機能は、のによって置き換え[CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)、両方の印刷設定、および ページ設定のコモン ダイアログ ボックスを提供するがいます。

アプリケーションの印刷プロセスの多くの側面を処理するために、フレームワークに依存することができます。 ここでは、フレームワークには、印刷用の Windows コモン ダイアログ ボックスに自動的に表示されます。 Framework ハンドルが、アプリケーションの印刷機能を持つも、独自の印刷 ダイアログ ボックスで、一般的な印刷 ダイアログ ボックスをオーバーライドできます。 印刷タスクを処理するために、フレームワークの使用に関する詳細については、記事を参照してください。[印刷](../../mfc/printing.md)します。

フレームワークの関与なし印刷を処理するために、アプリケーションを実行する場合は、使用、`CPrintDialog`現状有姿を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialog`と、ニーズに合わせてコンス トラクターを記述します。 いずれの場合も、これらのダイアログ ボックスと同様に標準の MFC ダイアログ ボックス クラスから派生しているため`CCommonDialog`します。

使用する、`CPrintDialog`オブジェクトは、まずを使用してオブジェクトを作成、`CPrintDialog`コンス トラクター。 ダイアログ ボックスが構築されると、設定または任意の値を変更、 [m_pd](#m_pd)構造 ダイアログ ボックスのコントロールの値を初期化します。 `m_pd`型の構造は、 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda)します。 この構造体の詳細については、Windows SDK を参照してください。

ハンドルを指定しない場合`m_pd`の`hDevMode`と`hDevNames`メンバー、Windows 関数を呼び出すことを確認する`GlobalFree`の ダイアログ ボックスが済んだら、これらのハンドル。 によって提供されるフレームワークの印刷のセットアップの実装を使用する場合`CWinApp::OnFilePrintSetup`、これらのハンドルを解放する必要はありません。 ハンドルがによって管理される`CWinApp`で解放されると`CWinApp`のデストラクター。 使用する場合は、これらのハンドルを解放する必要がのみ`CPrintDialog`スタンドアロンです。

ダイアログ ボックスのコントロールを初期化した後に呼び出し、 `DoModal`  ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにするメンバー関数。 `DoModal` ユーザーが [ok] \(IDOK) またはキャンセル (IDCANCEL) ボタンを選択するかどうかを返します。

場合`DoModal`IDOK を返しますのいずれかを使用することができます`CPrintDialog`のユーザーによって入力された情報を取得するメンバー関数。

`CPrintDialog::GetDefaults`メンバー関数は、ダイアログ ボックスを表示せず、現在のプリンターの既定値を取得するために役立ちます。 このメンバー関数には、ユーザーの介入は不要です。

Windows を使用する`CommDlgExtendedError` ダイアログ ボックスの初期化中にエラーが発生したかどうかを判断して、エラーに関する詳細については、関数。 この関数の詳細については、Windows SDK を参照してください。

`CPrintDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属する DLL ファイルです。

ダイアログ ボックスをカスタマイズするには、派生クラスを`CPrintDialog`独自のダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 すべて未処理のメッセージは、基本クラス渡す必要があります。 フック関数をカスタマイズする必要はありません。

印刷または印刷のセットアップ ダイアログ ボックスは、かどうかに応じて異なる方法で同じメッセージを処理するには、各ダイアログ ボックス クラスを派生する必要があります。 Windows を上書きすることも必要があります。`AttachOnSetup`関数で、、印刷 ダイアログ ボックス内で印刷のセットアップ ボタンを選択すると、新しいダイアログ ボックスの作成を処理します。

使用しての詳細については`CPrintDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog

Windows 印刷または印刷のセットアップのダイアログ オブジェクトを構築します。

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*呼び出すと*<br/>
標準の Windows 印刷 ダイアログ ボックスまたは印刷のセットアップ ダイアログ ボックスが表示されるかどうかを指定します。 このパラメーターは、標準の Windows プリンターの設定 ダイアログ ボックスを表示する場合は true に設定します。 Windows 印刷ダイアログ ボックスを表示する場合は FALSE に設定します。 場合*呼び出すと*false で、印刷のセットアップが、[印刷] ダイアログ ボックスに、オプション ボタンが引き続き表示されます。

*dwFlags*<br/>
1 つまたは複数のフラグがダイアログ ボックスで、ビットごとの OR 演算子を使用して結合の設定のカスタマイズに使用することができます。 たとえば、PD_ALLPAGES フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda)これらのフラグの詳細については、Windows SDK で構造体。

*pParentWnd*<br/>
ウィンドウ、ダイアログ ボックスの親またはオーナー ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、のみ、オブジェクトを構築します。 使用して、`DoModal`メンバー関数は、ダイアログ ボックスを表示します。

コンス トラクターを呼び出すときに注意して*呼び出すと*を FALSE に設定すると、PD_RETURNDC フラグは自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`ではプリンター DC が返されます`m_pd.hDC`します。 この DC を呼び出して解放する必要があります[とき](/windows/desktop/api/wingdi/nf-wingdi-deletedc)の呼び出し元によって`CPrintDialog`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC

プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンター デバイス コンテキストへのハンドルします。

### <a name="remarks"></a>Remarks

この DC は DC では、現在のプリンターと見なされ、以前に取得したその他のプリンターのユーザーはドメイン コント ローラーを削除する必要があります。 この関数を呼び出すことができ、[印刷] ダイアログ ボックスを表示せず、結果として得られる DC を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>  CPrintDialog::DoModal

Windows のコモン印刷ダイアログ ボックスを表示でき、ユーザーをコピー、ページの範囲の数などのさまざまな印刷オプションを選択し、コピーが照合されるかどうか。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK や IDCANCEL。 IDCANCEL が返された場合は、Windows を呼び出す[情報を得る](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror)エラーが発生したかどうかを判断する関数。

IDOK や IDCANCEL は、ユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまな印刷ダイアログ ボックスのオプションを初期化する場合、`m_pd`構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

呼び出した後`DoModal`、他のメンバー、ダイアログ ボックスに、設定やユーザーによって入力された情報を取得する関数を呼び出すことができます。

コンス トラクターを呼び出すときに注意して*呼び出すと*を FALSE に設定すると、PD_RETURNDC フラグは自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`ではプリンター DC が返されます`m_pd.hDC`します。 この DC を呼び出して解放する必要があります[とき](/windows/desktop/api/wingdi/nf-wingdi-deletedc)の呼び出し元によって`CPrintDialog`します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::CreatePrinterDC](#createprinterdc)します。

##  <a name="getcopies"></a>  CPrintDialog::GetCopies

要求されたコピーの数を取得します。

```
int GetCopies() const;
```

### <a name="return-value"></a>戻り値

要求されたコピーの数。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`コピー要求の数を取得します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::PrintCollate](#printcollate)します。

##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults

ダイアログ ボックスを表示せず、既定のプリンターの既定のデバイスを取得します。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

取得した値に配置、`m_pd`構造体。

場合によっては、この関数の呼び出しは呼び出します、[コンス トラクター](#cprintdialog)の`CPrintDialog`で*呼び出すと*を FALSE に設定します。 これらの場合、プリンター DC と`hDevNames`と`hDevMode`(内にある 2 つのハンドル、`m_pd`データ メンバー) は自動的に割り当てられます。

場合のコンス トラクター`CPrintDialog`で呼び出されました*呼び出すと*を FALSE に設定すると、この関数はしか返されません`hDevNames`と`hDevMode`内にある`m_pd.hDevNames`と`m_pd.hDevMode`)、呼び出し元にはプリンター DC で返すことも`m_pd.hDC`します。 プリンター DC を削除して、Windows の呼び出しの呼び出し元の責任[GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree)関数が終了したら、ハンドルを`CPrintDialog`オブジェクト。

### <a name="example"></a>例

このコード フラグメントでは、既定のプリンター デバイス コンテキストを取得し、ユーザーにレポートをインチあたりのドットでプリンターの解像度。 (この属性をプリンターの機能の多くの場合と呼びます DPI。)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName

現在選択されているプリンター デバイスの名前を取得します。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンターの名前。

### <a name="remarks"></a>Remarks

この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンターの名前を取得する[ため](#getdefaults)を既定のプリンターの現在のデバイスの既定値を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。

### <a name="example"></a>例

このコードは、ユーザーの既定のプリンター名とプリンターを使用して、スプーラー名と共に、接続されたポートを示します。 コードがメッセージ ボックスをオンにすると、表示する可能性があります"既定のプリンターが HP LaserJet IIIP \\\server\share winspool。 を使用して"など。

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode

取得、`DEVMODE`構造体。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)データ構造は、デバイスの初期化と印刷ドライバーの環境に関する情報が含まれています。 この構造体で、Windows によって使用されたメモリのロックを解除する必要があります[GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock)関数は、Windows SDK で説明します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::PrintCollate](#printcollate)します。

##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName

現在選択されているプリンター ドライバーの名前を取得します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

A `CString` driver のシステム定義の名前を指定します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)プリンターのシステム定義のデバイス ドライバーの名前を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::GetDeviceName](#getdevicename)します。

##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage

印刷範囲の開始ページを取得します。

```
int GetFromPage() const;
```

### <a name="return-value"></a>戻り値

印刷するページの範囲の開始のページ番号。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`を印刷するページの範囲の開始ページ番号を取得します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::m_pd](#m_pd)します。

##  <a name="getportname"></a>  CPrintDialog::GetPortName

現在選択されているプリンター ポートの名前を取得します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンター ポートの名前。

### <a name="remarks"></a>Remarks

この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)現在選択されているプリンター ポートの名前を取得します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::GetDeviceName](#getdevicename)します。

##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC

プリンター デバイス コンテキストを識別するハンドルを取得します。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>戻り値

成功した場合、プリンター デバイス コンテキストを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

場合、*呼び出すと*のパラメーター、`CPrintDialog`コンス トラクターが FALSE (印刷 ダイアログ ボックスが表示されることを示す)、`GetPrinterDC`プリンター デバイス コンテキストへのハンドルを返します。 Windows を呼び出す必要があります[とき](/windows/desktop/api/wingdi/nf-wingdi-deletedc)が終わったら、デバイス コンテキストを削除する関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>  CPrintDialog::GetToPage

印刷範囲の終了 ページを取得します。

```
int GetToPage() const;
```

### <a name="return-value"></a>戻り値

印刷するページ範囲の終了ページ番号をします。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`を印刷するページの範囲の終了ページ番号を取得します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::m_pd](#m_pd)します。

##  <a name="m_pd"></a>  CPrintDialog::m_pd

メンバーを持つダイアログ オブジェクトの特性を格納する構造体。

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Remarks

構築した後、`CPrintDialog`オブジェクトを使用することができます`m_pd`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pd`構造体は、「 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Windows SDK に含まれています。

変更する場合、`m_pd`データ メンバーを直接、既定の動作をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>  CPrintDialog::PrintAll

ドキュメントのすべてのページを印刷するかどうかを決定します。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>戻り値

ドキュメント内のすべてのページを印刷する場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::m_pd](#m_pd)します。

##  <a name="printcollate"></a>  CPrintDialog::PrintCollate

コピーが要求された部単位で印刷するかどうかを決定します。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>戻り値

ユーザーが、ダイアログ ボックスで、部単位で印刷 チェック ボックスを選択する場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`をプリンターにドキュメントの印刷したすべてのコピーを照合する必要があるかどうかを判断します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>  CPrintDialog::PrintRange

ページの指定した範囲のみを印刷するかどうかを決定します。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>戻り値

印刷するドキュメントのページの範囲がの場合のみ、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::m_pd](#m_pd)します。

##  <a name="printselection"></a>  CPrintDialog::PrintSelection

現在選択されている項目のみを印刷するかどうかを決定します。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>戻り値

選択した項目を印刷する場合のみ、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出した後`DoModal`を現在選択されている項目のみを印刷するかどうかを判断します。

### <a name="example"></a>例

  例をご覧ください[CPrintDialog::m_pd](#m_pd)します。

## <a name="see-also"></a>関連項目

[MFC サンプル DIBLOOK](../../visual-cpp-samples.md)<br/>
[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
