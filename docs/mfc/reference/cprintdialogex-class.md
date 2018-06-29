---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e005d18b57a4ada2c1a3aad605b7724f17a62347
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079099"
---
# <a name="cprintdialogex-class"></a>メンバー クラス
Windows の 印刷のプロパティ シートによって提供されるサービスをカプセル化します。  
  
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
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|印刷 ダイアログ ボックスを表示することがなくプリンター デバイス コンテキストを作成します。|  
|[CPrintDialogEx::DoModal](#domodal)|ダイアログ ボックスを表示し、項目を選択することができます。|  
|[CPrintDialogEx::GetCopies](#getcopies)|要求されたコピーの数を取得します。|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|システム定義のプリンター デバイス ドライバーの名前を取得します。|  
|[CPrintDialogEx::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストへのハンドルを取得します。|  
|[CPrintDialogEx::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを判断します。|  
|[CPrintDialogEx::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを判断します。|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|ドキュメントの現在のページを印刷するかどうかを判断します。|  
|[CPrintDialogEx::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを判断します。|  
|[CPrintDialogEx::PrintSelection](#printselection)|現在選択されている項目のみを印刷するかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|カスタマイズに使用される構造体、`CPrintDialogEx`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーションの印刷プロセスの多くの側面を処理するためにフレームワークに依存することができます。 フレームワークを使用して印刷タスクを処理する方法の詳細については、記事を参照してください。[印刷](../../mfc/printing.md)です。  
  
 フレームワークの関与なし印刷処理を行うアプリケーションを実行する場合は、使用、`CPrintDialogEx`現状有姿を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialogEx`ニーズに合わせてコンス トラクターを記述するとします。 どちらの場合、これらのダイアログ ボックスと同様に標準の MFC ダイアログ ボックス クラスから派生しているため`CCommonDialog`です。  
  
 使用する、`CPrintDialogEx`オブジェクト、オブジェクトを使用して、最初に作成、`CPrintDialogEx`コンス トラクターです。 ダイアログ ボックスを構築すると、設定したり、任意の値を変更、 [m_pdex](#m_pdex)構造 ダイアログ ボックスのコントロールの値を初期化します。 `m_pdex`構造体は型[PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)です。 この構造体の詳細については、Windows SDK を参照してください。  
  
 独自のハンドルを指定しない場合`m_pdex`の**hDevMode**と**と**メンバー、Windows の関数を呼び出してください**GlobalFree**これらのハンドルを完了したら、ダイアログ ボックスでします。  
  
 ダイアログ ボックス コントロールを初期化した後、 `DoModal`  ダイアログ ボックスが表示され、印刷オプションを選択するユーザーを許可するメンバー関数。 ときに`DoModal`を返します、ユーザーが [ok]、適用、または [キャンセル] ボタンを選択するかどうかを判断できます。  
  
 使用することができる場合は、ユーザーは、[ok] を押す、`CPrintDialogEx`のユーザーが入力情報を取得するメンバー関数。  
  
 `CPrintDialogEx::GetDefaults`メンバー関数はダイアログ ボックスを表示せず、現在のプリンターの既定値を取得するために役立ちます。 このメソッドには、ユーザー操作は不要です。  
  
 Windows を使用する**情報を得る**関数およびエラーに関する詳細については、ダイアログ ボックスの初期化中にエラーが発生するかどうかを決定します。 この関数の詳細については、Windows SDK を参照してください。  
  
 使用する方法についての`CPrintDialogEx`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)です。  
  
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
 Windows の 印刷のプロパティ シートを構築します。  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 1 つまたは複数のフラグはビットごとの OR 演算子を使用して結合します ダイアログ ボックスの設定のカスタマイズに使用することができます。 たとえば、 **PD_ALLPAGES**フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)これらのフラグの詳細について、Windows SDK 内の構造。  
  
 *pParentWnd*  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数のみオブジェクトを構築します。 使用して、 `DoModal`  ダイアログ ボックスを表示するメンバー関数。  
  
##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキストへのハンドルします。  
  
### <a name="remarks"></a>Remarks  
 返されたドメイン コント ローラーにも格納、 **hDC**のメンバー [m_pdex](#m_pdex)です。  
  
 この DC は DC では、現在のプリンターと見なされ、以前取得したプリンター Dc を削除する必要があります。 この関数を呼び出すことができます、[印刷] ダイアログ ボックスを表示せず、結果として得られる DC を使用します。  
  
##  <a name="domodal"></a>  CPrintDialogEx::DoModal  
 Windows の 印刷のプロパティ シートを表示し、ユーザーがコピー、ページ範囲の数などのさまざまな印刷オプションを選択できるようにするには、この関数を呼び出してコピーを照合するかどうかとします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 INT_PTR では、値が実際に HRESULT を返します。 戻り値のセクションを参照して[PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) Windows SDK に含まれています。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定して、さまざまな印刷ダイアログ ボックスのオプションを初期化する場合、`m_pdex`構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバーは、ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数で呼び出すことができます。  
  
 場合、 **PD_RETURNDC**を呼び出すときに、フラグが使用される`DoModal`ではプリンター DC が返されます、 **hDC**のメンバー [m_pdex](#m_pdex)です。 この DC は、呼び出しを解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialogEx`です。  
  
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
 **TRUE**成功した場合、それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
 `GetDefaults` 印刷 プロパティ シートを表示しません。 代わりに、設定、**と**と**hDevMode**のメンバー [m_pdex](#m_pdex)へのハンドルへ、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)システムの既定のプリンターを初期化します。 両方**と**と**hDevMode**が NULL の場合または`GetDefaults`は失敗します。  
  
 場合、 **PD_RETURNDC**フラグを設定すると、この関数はしか返しません**と**と**hDevMode** (内にある**m_pdex.hDevNames**と**m_pdex.hDevMode**)、呼び出し元にはプリンター DC で返すことも**m_pdex.hDC**です。 プリンター DC を削除して、Windows を呼び出す呼び出し元の責任[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)関数が完了すると、ハンドルを`CPrintDialogEx`オブジェクト。  
  
##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName  
 この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンターの名前を取得する[ため](#getdefaults)を既定のプリンターの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンターの名前。  
  
### <a name="remarks"></a>Remarks  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)です。  
  
##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 Windows による構造体が使用されたメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)関数で、Windows SDK に記載されています。  
  
##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)システム定義のプリンター デバイス ドライバーの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>Remarks  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として*lpszDriverName*への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)です。  
  
##  <a name="getportname"></a>  CPrintDialogEx::GetPortName  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)を現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC  
 プリンター デバイス コンテキスト ハンドルを返します。  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プリンター デバイス コンテキストへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 Windows を呼び出す必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)が完了したら、デバイス コンテキストを削除する関数を使用します。  
  
##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex  
 メンバーのダイアログ オブジェクトの特性を保持する PRINTDLGEX 構造体。  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CPrintDialogEx`オブジェクトを使用する`m_pdex`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pdex`構造体は、「 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK に含まれています。  
  
 変更する場合、`m_pdex`データ メンバーを直接、既定の動作がオーバーライドされます。  
  
##  <a name="printall"></a>  CPrintDialogEx::PrintAll  
 この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、ドキュメント内のすべてのページは、それ以外の印刷に**FALSE**です。  
  
##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate  
 この関数を呼び出した後`DoModal`をプリンターが、ドキュメントの印刷したすべてのコピーを照合するかどうかを判断します。  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ユーザー ダイアログ ボックスで、部単位で印刷 チェック ボックスを選択した場合はそれ以外の場合**FALSE**です。  
  
##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage  
 この関数を呼び出した後`DoModal`をドキュメントの現在のページを印刷するかどうかを判断します。  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合**現在のページを印刷**それ以外の印刷ダイアログ ボックスで選択した**FALSE**です。  
  
##  <a name="printrange"></a>  CPrintDialogEx::PrintRange  
 この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合のみ、ドキュメント内のページの範囲はそれ以外の印刷**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 指定したページ範囲を決定できます[m_pdex](#m_pdex) (を参照してください**nPageRanges**、 **nMaxPageRanges**、および**lpPageRanges** で[PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK 内の構造) です。  
  
##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection  
 この関数を呼び出した後`DoModal`を現在選択されている項目のみを印刷するかどうかを判断します。  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合のみ、選択した項目はそれ以外の印刷**FALSE**です。  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)
