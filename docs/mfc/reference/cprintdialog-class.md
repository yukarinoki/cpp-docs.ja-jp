---
title: CPrintDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 842565b460ff88ae70d108bc1b1db71b22674eb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|印刷 ダイアログ ボックスを表示することがなくプリンター デバイス コンテキストを作成します。|  
|[CPrintDialog::DoModal](#domodal)|ダイアログ ボックスが表示され、選択を行うことができます。|  
|[CPrintDialog::GetCopies](#getcopies)|要求されたコピーの数を取得します。|  
|[CPrintDialog::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|  
|[CPrintDialog::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|  
|[CPrintDialog::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|  
|[CPrintDialog::GetDriverName](#getdrivername)|現在選択されているプリンタ ドライバの名前を取得します。|  
|[CPrintDialog::GetFromPage](#getfrompage)|印刷の範囲の開始ページを取得します。|  
|[CPrintDialog::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストへのハンドルを取得します。|  
|[CPrintDialog::GetToPage](#gettopage)|印刷範囲の終了ページを取得します。|  
|[CPrintDialog::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを判断します。|  
|[CPrintDialog::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを判断します。|  
|[CPrintDialog::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを判断します。|  
|[CPrintDialog::PrintSelection](#printselection)|現在選択されている項目のみを印刷するかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|カスタマイズに使用される構造体、`CPrintDialog`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 一般的な印刷ダイアログ ボックスでは、Windows の標準に準拠した形式で印刷および印刷のセットアップ ダイアログ ボックスを実装する簡単な方法を提供します。  
  
> [!NOTE]
>  `CPrintDialogEx`クラスは、Windows の 印刷のプロパティ シートによって提供されるサービスをカプセル化します。 詳細については、次を参照してください。、[メンバー](../../mfc/reference/cprintdialogex-class.md)の概要です。  
  
 `CPrintDialog`機能がのによって取り替えられて[コモン](../../mfc/reference/cpagesetupdialog-class.md)、両方の印刷設定、およびページ設定のコモン ダイアログ ボックスを提供するようになっています。  
  
 アプリケーションの印刷プロセスの多くの側面を処理するためにフレームワークに依存することができます。 この場合、フレームワークは自動的に印刷用の Windows コモン ダイアログ ボックスを表示します。 アプリケーションの印刷 framework ハンドルは、独自の印刷 ダイアログ ボックスで、一般的な印刷ダイアログ ボックスをオーバーライドすることもできます。 フレームワークを使用して印刷タスクを処理する方法の詳細については、記事を参照してください。[印刷](../../mfc/printing.md)です。  
  
 フレームワークの関与なし印刷処理を行うアプリケーションを実行する場合は、使用、`CPrintDialog`現状有姿を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialog`ニーズに合わせてコンス トラクターを記述するとします。 どちらの場合、これらのダイアログ ボックスと同様に標準の MFC ダイアログ ボックス クラスから派生しているため`CCommonDialog`です。  
  
 使用する、`CPrintDialog`オブジェクト、オブジェクトを使用して、最初に作成、`CPrintDialog`コンス トラクターです。 ダイアログ ボックスを構築すると、設定したり、任意の値を変更、 [m_pd](#m_pd)構造 ダイアログ ボックスのコントロールの値を初期化します。 `m_pd`構造体は型[PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)です。 この構造体の詳細については、Windows SDK を参照してください。  
  
 独自のハンドルを指定しない場合`m_pd`の**hDevMode**と**と**メンバー、Windows の関数を呼び出してください**GlobalFree**これらのハンドルを完了したら、ダイアログ ボックスでします。 によって提供されるフレームワークの印刷設定の実装を使用するときに`CWinApp::OnFilePrintSetup`、これらのハンドルを解放する必要はありません。 によって、ハンドルが保持されます`CWinApp`で解放されると`CWinApp`のデストラクターです。 のみを使用する場合は、これらのハンドルを解放する必要が`CPrintDialog`スタンドアロンです。  
  
 ダイアログ ボックス コントロールを初期化した後、 `DoModal`  ダイアログ ボックスが表示され、印刷オプションを選択するユーザーを許可するメンバー関数。 `DoModal` ユーザーが、[ok] を選択するかどうかを返します ( **IDOK**) か、またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**のいずれかを使用することができます`CPrintDialog`のユーザーが入力情報を取得するメンバー関数。  
  
 `CPrintDialog::GetDefaults`メンバー関数はダイアログ ボックスを表示せず、現在のプリンターの既定値を取得するために役立ちます。 このメンバー関数には、ユーザー操作は不要です。  
  
 Windows を使用する**情報を得る**関数およびエラーに関する詳細については、ダイアログ ボックスの初期化中にエラーが発生するかどうかを決定します。 この関数の詳細については、Windows SDK を参照してください。  
  
 `CPrintDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするからクラスを派生`CPrintDialog`拡張コントロールから通知メッセージを処理するメッセージ マップの追加を独自のダイアログ テンプレートを提供します。 処理されないメッセージは、基底クラスへ渡されます。 フック関数をカスタマイズする必要はありません。  
  
 印刷または印刷のセットアップ ダイアログ ボックスは、かどうかに応じて異なる方法で、同じメッセージを処理するには、各ダイアログ ボックスにクラスを派生する必要があります。 Windows を上書きすることも必要があります。**移るため**印刷 ダイアログ ボックス内で、印刷のセットアップ ボタンを選択すると、新しいダイアログ ボックスの作成を処理する関数。  
  
 使用する方法についての`CPrintDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>要件  
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
 `bPrintSetupOnly`  
 標準の Windows の [印刷] ダイアログ ボックスまたは [印刷設定] ダイアログ ボックスが表示されるかどうかを指定します。 このパラメーターに設定**TRUE**を標準の Windows プリンターの設定 ダイアログ ボックスを表示します。 設定**FALSE** Windows 印刷 ダイアログ ボックスを表示します。 場合`bPrintSetupOnly`は**FALSE**印刷のセットアップ オプション ボタンは [印刷] ダイアログ ボックスで引き続き表示されます。  
  
 `dwFlags`  
 1 つまたは複数のフラグはビットごとの OR 演算子を使用して結合します ダイアログ ボックスの設定のカスタマイズに使用することができます。 たとえば、 **PD_ALLPAGES**フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)これらのフラグの詳細について、Windows SDK 内の構造。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数のみオブジェクトを構築します。 使用して、 `DoModal`  ダイアログ ボックスを表示するメンバー関数。  
  
 持つコンス トラクターを呼び出すときに注意してください`bPrintSetupOnly`'éý' **FALSE**、 **PD_RETURNDC**フラグが自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`ではプリンター DC が返されます`m_pd.hDC`です。 この DC は、呼び出しを解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialog`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキストへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 この DC の DC では、現在のプリンターと見なされ、以前取得したプリンター、ユーザーがドメイン コント ローラーを削除する必要があります。 この関数を呼び出すことができます、[印刷] ダイアログ ボックスを表示せず、結果として得られる DC を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>  CPrintDialog::DoModal  
 Windows の一般的な印刷ダイアログ ボックスを表示でき、ユーザーをコピー、ページ範囲の数などのさまざまな印刷オプションを選択し、コピーを照合するかどうか。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**です。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断する関数。  
  
 **IDOK**と**IDCANCEL**ユーザーが、[ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまな印刷ダイアログ ボックスのオプションを初期化する場合、`m_pd`構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバーは、ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数で呼び出すことができます。  
  
 持つコンス トラクターを呼び出すときに注意してください`bPrintSetupOnly`'éý' **FALSE**、 **PD_RETURNDC**フラグが自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`ではプリンター DC が返されます`m_pd.hDC`です。 この DC は、呼び出しを解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialog`です。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::CreatePrinterDC](#createprinterdc)です。  
  
##  <a name="getcopies"></a>  CPrintDialog::GetCopies  
 要求されたコピーの数を取得します。  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要求されたコピーの数。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`コピー要求の数を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::PrintCollate](#printcollate)です。  
  
##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults  
 ダイアログ ボックスを表示せず、既定のプリンターの既定のデバイスを取得します。  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 取得した値を配置している、`m_pd`構造体。  
  
 場合によっては、この関数に対する呼び出しが呼び出す、[コンス トラクター](#cprintdialog)の`CPrintDialog`で`bPrintSetupOnly`'éý' **FALSE**です。 これらの場合はプリンター DC と**と**と**hDevMode** (に 2 つのハンドルがある、`m_pd`データ メンバー) は自動的に割り当てられます。  
  
 場合のコンス トラクター`CPrintDialog`で呼び出されました`bPrintSetupOnly`'éý' **FALSE**、この関数はしか返しません**と**と**hDevMode** (内にあります。**m_pd.hDevNames**と**m_pd.hDevMode**)、呼び出し元にはプリンター DC で返すことも**m_pd.hDC**です。 プリンター DC を削除して、Windows を呼び出す呼び出し元の責任[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)関数が完了すると、ハンドルを`CPrintDialog`オブジェクト。  
  
### <a name="example"></a>例  
 次のコード片では、既定のプリンター デバイス コンテキストを取得し、ユーザーにドット/インチで、プリンターの解像度を報告します。 (この属性と、プリンターの機能は多くの場合と呼びます DPI。)  
  
 [!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName  
 現在選択されているプリンター デバイスの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンターの名前。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンターの名前を取得する[ため](#getdefaults)既定のプリンターの現在のデバイスの既定値を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)です。  
  
### <a name="example"></a>例  
 このコードは、ユーザーの既定のプリンターの名前と、プリンターを使用して、スプーラー名と共に、接続されているポートを示します。 コードは、メッセージ ボックスを表示可能性があります"で、既定のプリンターは、HP LaserJet IIIP \\\server\share winspool。 を使用して"などです。  
  
 [!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode  
 取得、`DEVMODE`構造体。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 Windows による構造体が使用されたメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)関数で、Windows SDK に記載されています。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::PrintCollate](#printcollate)です。  
  
##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName  
 現在選択されているプリンタ ドライバの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)システム定義のプリンター デバイス ドライバーの名前を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)です。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::GetDeviceName](#getdevicename)です。  
  
##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage  
 印刷の範囲の開始ページを取得します。  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷するページの範囲の開始のページ番号。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`を印刷するページの範囲の開始ページ番号を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::m_pd](#m_pd)です。  
  
##  <a name="getportname"></a>  CPrintDialog::GetPortName  
 現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)を現在選択されているプリンター ポートの名前を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::GetDeviceName](#getdevicename)です。  
  
##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC  
 プリンター デバイス コンテキストへのハンドルを取得します。  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、プリンター デバイス コンテキストへのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 場合、`bPrintSetupOnly`のパラメーター、`CPrintDialog`コンス トラクターが**FALSE** (印刷 ダイアログ ボックスが表示されることを示す)、`GetPrinterDC`プリンター デバイス コンテキスト ハンドルを返します。 Windows を呼び出す必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)が完了したら、デバイス コンテキストを削除する関数を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>  CPrintDialog::GetToPage  
 印刷範囲の終了ページを取得します。  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷するページの範囲の終了のページ番号。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`を印刷するページの範囲の終了ページ番号を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::m_pd](#m_pd)です。  
  
##  <a name="m_pd"></a>  CPrintDialog::m_pd  
 メンバーのダイアログ オブジェクトの特性を格納する構造体。  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CPrintDialog`オブジェクトを使用する`m_pd`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pd`構造体は、「 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK に含まれています。  
  
 変更する場合、`m_pd`データ メンバーを直接、既定の動作がオーバーライドされます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>  CPrintDialog::PrintAll  
 ドキュメントのすべてのページを印刷するかどうかを判断します。  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント内のすべてのページを印刷する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::m_pd](#m_pd)です。  
  
##  <a name="printcollate"></a>  CPrintDialog::PrintCollate  
 コピーが要求された部単位で印刷するかどうかを判断します。  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザー ダイアログ ボックスで、部単位で印刷 チェック ボックスを選択した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`をプリンターが、ドキュメントの印刷したすべてのコピーを照合するかどうかを判断します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>  CPrintDialog::PrintRange  
 ページの指定した範囲のみを印刷するかどうかを判断します。  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>戻り値  
 だけを印刷するドキュメント内のページの範囲がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::m_pd](#m_pd)です。  
  
##  <a name="printselection"></a>  CPrintDialog::PrintSelection  
 現在選択されている項目のみを印刷するかどうかを判断します。  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 だけを印刷する選択した項目がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`を現在選択されている項目のみを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照して[CPrintDialog::m_pd](#m_pd)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
