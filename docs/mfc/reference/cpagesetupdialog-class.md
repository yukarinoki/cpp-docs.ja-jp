---
title: コモン クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
dev_langs:
- C++
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd96f0240f8dd97fdda54fd2d00231db14ae3d47
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079184"
---
# <a name="cpagesetupdialog-class"></a>メンバー クラス
印刷マージンの設定や変更の追加サポートと共に [OLE ページの設定] ダイアログ ボックスにより提供されるサービスをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|`CPageSetupDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|印刷用のデバイス コンテキストを作成します。|  
|[CPageSetupDialog::DoModal](#domodal)|ダイアログ ボックスが表示され、ユーザーを選択できます。|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|プリンターのデバイス名を返します。|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|現在を返して`DEVMODE`プリンターのです。|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|プリンターで使用するドライバーを返します。|  
|[CPageSetupDialog::GetMargins](#getmargins)|プリンターの現在の余白の設定を返します。|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|プリンターの用紙サイズを返します。|  
|[CPageSetupDialog::GetPortName](#getportname)|出力ポートの名前を返します。|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|印刷ページの画面イメージを表示するためにフレームワークによって呼び出されます。|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|印刷ページの画面イメージを表示する前に、フレームワークによって呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|カスタマイズに使用される構造体、`CPageSetupDialog`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは、印刷のセットアップ ダイアログ ボックスの代わりに設計されています。  
  
 使用する、`CPageSetupDialog`オブジェクト、オブジェクトを使用して、最初に作成、`CPageSetupDialog`コンス トラクターです。 ダイアログ ボックスを構築すると、設定したり、任意の値を変更、`m_psd`データ メンバーは、ダイアログ ボックスのコントロールの値を初期化します。 [M_psd](#m_psd)構造体は型**PAGESETUPDLG**です。  
  
 ダイアログ ボックス コントロールを初期化した後、 `DoModal`  ダイアログ ボックスが表示され、印刷オプションを選択するユーザーを許可するメンバー関数。 `DoModal` ユーザーが、[ok] を選択するかどうかを返します ( **IDOK**) か、またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`を返します**IDOK**、いくつかの操作を使用することができます`CPageSetupDialog`のメンバー関数、またはアクセス、`m_psd`データ メンバーは、ユーザーが入力した情報を取得します。  
  
> [!NOTE]
>  共通の OLE ページの設定 ダイアログ ボックスが閉じられた後に、フレームワークによって、ユーザーによって行われた変更は保存されません。 このダイアログ ボックスから、アプリケーションのドキュメントまたはアプリケーションのクラスのメンバーなどの永続的な場所の任意の値を保存する、アプリケーション自体の責任です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog  
 構築するには、この関数を呼び出して、`CPageSetupDialog`オブジェクト。  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 1 つまたは複数のフラグがダイアログ ボックスの設定のカスタマイズに使用することができます。 値は、ビットごとの OR 演算子を使用して結合できます。 これらの値には、次の意味があります。  
  
- **PSD_DEFAULTMINMARGINS**プリンターの最小値と同じであるページの余白の許容される最小の幅を設定します。 場合、このフラグは無視されます、 **PSD_MARGINS**と**PSD_MINMARGINS**フラグも指定します。  
  
- **PSD_INWININIINTLMEASURE**実装されていません。  
  
- **PSD_MINMARGINS**により、システムで指定された値を使用して、**小幅**左、上、右、および上下の余白の許容される最小の幅としてメンバー。 システムでは、ユーザーが指定の最小値より小さく、幅を入力することを防ぎます。 場合**PSD_MINMARGINS**が指定されていない、システムは、プリンターによって許可されているものに許容される最小の幅を設定します。  
  
- **PSD_MARGINS**余白コントロール領域をアクティブにします。  
  
- **PSD_INTHOUSANDTHSOFINCHES**  ダイアログ ボックスの単位をインチの 1/1000 で測定されます。  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS**  ダイアログ ボックスの単位を 1/100 ミリ単位で測定されます。  
  
- **PSD_DISABLEMARGINS**余白 ダイアログ ボックス コントロールを無効にします。  
  
- **PSD_DISABLEPRINTER** [プリンター] ボタンを無効にします。  
  
- **PSD_NOWARNING**警告メッセージが既定のプリンターが存在しない場合に表示されないようにします。  
  
- **PSD_DISABLEORIENTATION**ページの向きのダイアログ コントロールを無効にします。  
  
- **PSD_RETURNDEFAULT**により`CPageSetupDialog`を返す[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)  ダイアログ ボックスを表示せずにシステムの既定のプリンターの初期化された構造体。 前提とする両方**と**と**hDevMode**は**NULL**、それ以外のエラーを返します。 システムの既定のプリンターが、古いプリンター ドライバー (Windows バージョン 3.0 より前) でサポートされている場合のみ**と**が返されます。**hDevMode**は**NULL**です。  
  
- **PSD_DISABLEPAPER**用紙の選択コントロールを無効にします。  
  
- **PSD_SHOWHELP**ダイアログ ボックスの [ヘルプ] ボタンを表示します。 **HwndOwner**メンバーにする必要がありますいない**NULL**このフラグが指定されている場合。  
  
- **PSD_ENABLEPAGESETUPHOOK**で指定したフック関数を有効に**lpfnSetupHook**です。  
  
- **PSD_ENABLEPAGESETUPTEMPLATE**により、オペレーティング システムで識別されるダイアログ テンプレートを使用して、ダイアログ ボックスを作成する**hInstance**と**されると**です。  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE**ことを示します**hInstance**プリロードされているダイアログ ボックスのテンプレートが含まれるデータ ブロックを指定します。 システムを無視**されると**このフラグが指定されている場合。  
  
- **PSD_ENABLEPAGEPAINTHOOK**で指定したフック関数を有効に**lpfnPagePaintHook**です。  
  
- **PSD_DISABLEPAGEPAINTING**  ダイアログ ボックスの描画領域を無効にします。  
  
 *pParentWnd*  
 ダイアログ ボックスの親または所有者へのポインター。  
  
### <a name="remarks"></a>Remarks  
 使用して、 [DoModal](../../mfc/reference/cdialog-class.md#domodal)  ダイアログ ボックスを表示する関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC  
 プリンター デバイス コンテキストを作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキスト (DC) へのハンドルします。  
  
##  <a name="domodal"></a>  CPageSetupDialog::DoModal  
 この関数では、Windows に共通の [OLE ページの設定] ダイアログ ボックスを表示し、ユーザーが印刷の余白、サイズ、用紙とプリンターの移行先の向きなどの各種の印刷のセットアップ オプションを選択できるようにします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**です。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断する関数。  
  
 **IDOK**と**IDCANCEL**ユーザーが、[ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>Remarks  
 さらに、ネットワークの場所と、選択したプリンターに固有のプロパティなど、プリンター設定オプションをユーザーにアクセスできます。  
  
 メンバーを設定して、さまざまなページ セットアップ ダイアログ オプションを初期化する場合、`m_psd`構造体、呼び出す前に行う必要があります`DoModal`、前後ダイアログ オブジェクトを構築します。 呼び出した後`DoModal`、他のメンバー、ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出します。  
  
 呼び出しを行う、ユーザーが入力した現在の設定が反映される場合は、[通知](../../mfc/reference/cwinapp-class.md#selectprinter)です。 この関数からの情報には、`CPageSetupDialog`オブジェクトしを初期化し、適切な属性を持つ新しいプリンター DC を選択します。  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>例  
  例を参照して[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)です。  
  
##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName  
 後にこの関数を呼び出す`DoModal`現在選択されているプリンターの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって使用されるデバイス名、`CPageSetupDialog`オブジェクト。  
  
##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode  
 この関数を呼び出した後`DoModal`のプリンター デバイス コンテキストに関する情報を取得、`CPageSetupDialog`オブジェクト。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 Windows による構造体が使用されたメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)関数で、Windows SDK に記載されています。  
  
##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName  
 この関数を呼び出した後[DoModal](../../mfc/reference/cprintdialog-class.md#domodal)システム定義のプリンター デバイス ドライバーの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>Remarks  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)です。  
  
##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins  
 呼び出しの後にこの関数を呼び出す`DoModal`プリンター デバイス ドライバーの余白を取得します。  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectMargins*  
 ポインター、 [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md) (1/1000 インチまたは 1/100 mm) で、現在選択されているプリンターの印刷の余白を記述するオブジェクト。 渡す**NULL**この四角形に関心がいない場合は、このパラメーターにします。  
  
 *lpRectMinMargins*  
 ポインター、`RECT`構造または`CRect`現在選択されているプリンターの印刷の余白の最小値 (1/1000 インチまたは 1/100 mm) で記述するオブジェクト。 渡す**NULL**この四角形に関心がいない場合は、このパラメーターにします。  
  
##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize  
 この関数では、印刷用に選択、用紙のサイズを取得します。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)印刷用に選択 (1/1000 インチまたは 1/100 mm) で、用紙のサイズを含むオブジェクト。  
  
##  <a name="getportname"></a>  CPageSetupDialog::GetPortName  
 この関数を呼び出した後`DoModal`を現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
##  <a name="m_psd"></a>  CPageSetupDialog::m_psd  
 型の構造体**PAGESETUPDLG**メンバーのダイアログ オブジェクトの特性を格納します。  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CPageSetupDialog`オブジェクトを使用する`m_psd`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、`DoModal`メンバー関数。  
  
 変更する場合、`m_psd`データ メンバーを直接、既定の動作がオーバーライドされます。  
  
 詳細については、 [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)構造体、Windows SDK を参照してください。  
  
 例を参照して[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)です。  
  
##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage  
 印刷ページの画面イメージを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 プリンター デバイス コンテキストへのポインター。  
  
 *%n メッセージ*  
 現在描画されるページの領域を示すメッセージを指定します。 次のいずれかの値を指定します。  
  
- **WM_PSD_FULLPAGERECT**全体のページの領域。  
  
- **WM_PSD_MINMARGINRECT**現在余白の最小値。  
  
- **WM_PSD_MARGINRECT**現在余白。  
  
- **WM_PSD_GREEKTEXTRECT**ページの内容。  
  
- **WM_PSD_ENVSTAMPRECT**切手表現用に予約する領域です。  
  
- **WM_PSD_YAFULLPAGERECT**リターン アドレス表現の領域。 この領域は、サンプルのページ領域の端に拡張します。  
  
 *lpRect*  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)描画領域の座標を持つオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 処理された場合は 0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このイメージは、共通の OLE ページの設定 ダイアログ ボックスの一部として表示されます。 既定の実装では、テキストのページのイメージを描画します。  
  
 イメージ、またはイメージ全体の特定の領域の描画をカスタマイズするには、この関数をオーバーライドします。 使用してこれを行う、**切り替える**ステートメントと**ケース**の値をチェックするステートメント *%n*です。 たとえば、ページのイメージの内容の表示をカスタマイズするには、次のコード例を使用する可能性があります。  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 すべてのケースを処理する必要はありません *%n*です。 イメージ、イメージ、または領域全体のいくつかのコンポーネントの 1 つのコンポーネントを処理することができます。  
  
##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage  
 印刷ページの画面イメージを描画する前に、フレームワークによって呼び出されます。  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>パラメーター  
 *wPaper*  
 用紙サイズを示す値を指定します。 この値には、いずれかを指定できます、 **DMPAPER_** 値の説明に一覧表示、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)構造体。  
  
 *wFlags*  
 用紙または封筒の印刷の向きを示す、およびプリンターがドット マトリックスか HPPCL (Hewlett Packard Printer Control Language) デバイス。 このパラメーターには、次のいずれかの値を指定できます。  
  
-   0x001 用紙横モード (ドット マトリックス)  
  
-   0x003 用紙横モード (HPPCL)  
  
-   0x005 用紙の縦モード (ドット マトリックス)  
  
-   0x007 用紙の縦モード (HPPCL)  
  
-   0x00b 横向きモード (HPPCL) エンベロープ  
  
-   0x00d 縦向きモード (ドット マトリックス) エンベロープ  
  
-   0x019 横向きモード (ドット マトリックス) エンベロープ  
  
-   0x01f 縦向きモード (ドット マトリックス) エンベロープ  
  
 *pPSD*  
 ポインター、 **PAGESETUPDLG**構造体。 詳細については[PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)、Windows SDK を参照してください。  
  
### <a name="return-value"></a>戻り値  
 処理された場合は 0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 イメージの描画をカスタマイズするには、この関数をオーバーライドします。 この関数をオーバーライドして返す**TRUE**、全体のイメージを描画する必要があります。 この関数をオーバーライドして返す**FALSE**、フレームワークによって、全体の既定のイメージを描画します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル ワードパッド](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



