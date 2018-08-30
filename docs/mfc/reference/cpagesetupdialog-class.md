---
title: CPageSetupDialog クラス |Microsoft Docs
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
ms.openlocfilehash: c134d2e1dc6f3782446afc57b8384279a615e86f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197458"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog クラス
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
|[CPageSetupDialog::DoModal](#domodal)|ダイアログ ボックスを表示し、ユーザーを選択できます。|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|プリンターのデバイス名を返します。|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|現在の DEVMODE、プリンターを返します。|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|プリンターで使用するドライバーを返します。|  
|[CPageSetupDialog::GetMargins](#getmargins)|プリンターの現在の余白の設定を返します。|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|プリンターの用紙サイズを返します。|  
|[CPageSetupDialog::GetPortName](#getportname)|出力ポートの名前を返します。|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|印刷ページの画面イメージを表示するためにフレームワークによって呼び出されます。|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|印刷ページの画面イメージを表示する前に、フレームワークによって呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|構造体をカスタマイズするために使用する`CPageSetupDialog`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは、印刷のセットアップ ダイアログ ボックスの代わりに設計されています。  
  
 使用する、`CPageSetupDialog`オブジェクトは、まずを使用してオブジェクトを作成、`CPageSetupDialog`コンス トラクター。 ダイアログ ボックスが構築されると、設定または任意の値を変更、 `m_psd`  ダイアログ ボックスのコントロールの値を初期化するためにデータ メンバー。 [M_psd](#m_psd)型 PAGESETUPDLG 構造です。  
  
 ダイアログ ボックスのコントロールを初期化した後に呼び出し、 `DoModal`  ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにするメンバー関数。 `DoModal` ユーザーが [ok] \(IDOK) またはキャンセル (IDCANCEL) ボタンを選択するかどうかを返します。  
  
 場合`DoModal`IDOK を返しますのいくつかを使用することができます`CPageSetupDialog`のメンバー関数、またはアクセス、`m_psd`データ メンバーは、ユーザーが入力した情報を取得します。  
  
> [!NOTE]
>  共通の OLE ページ設定ダイアログ ボックスを閉じると、後に、フレームワークによって、ユーザーによって加えられた変更は保存されません。 このダイアログ ボックスから、アプリケーションのドキュメントまたはアプリケーションのクラスのメンバーなどの永続的な場所の任意の値を保存するにはアプリケーション自体の責任です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>要件  
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
 1 つまたは複数のフラグが ダイアログ ボックスの設定のカスタマイズに使用することができます。 値は、ビットごとの OR 演算子を使用して結合できます。 これらの値には、次の意味があります。  
  
- PSD_DEFAULTMINMARGINS では、プリンターの最小値と同じにするページの余白の最小幅の許容を設定します。 PSD_MARGINS と PSD_MINMARGINS フラグが指定されてもこのフラグは無視されます。  
  
- PSD_INWININIINTLMEASURE 実装されていません。  
  
- PSD_MINMARGINS が原因でシステムで指定された値を使用する、`rtMinMargin`左、上、右、下の余白の許容される最小の幅としてメンバー。 システムでは、ユーザーが指定の最小値より小さい、幅を入力することを防ぎます。 PSD_MINMARGINS が指定されていない場合、システムは、プリンターで許可されているものに許容される最小の幅を設定します。  
  
- PSD_MARGINS には、コントロールの余白の領域がアクティブにします。  
  
- PSD_INTHOUSANDTHSOFINCHES により、ダイアログ ボックスのユニットを 1/1000 インチ単位で測定されます。  
  
- PSD_INHUNDREDTHSOFMILLIMETERS により、ダイアログ ボックスの単位を 1/100 ミリメートル単位にします。  
  
- PSD_DISABLEMARGINS 余白 ダイアログ ボックスのコントロールを無効にします。  
  
- PSD_DISABLEPRINTER には、[プリンター] ボタンが無効にします。  
  
- PSD_NOWARNING では、警告メッセージが既定のプリンターが存在しない場合に表示されていることを防ぎます。  
  
- PSD_DISABLEORIENTATION には、ページの向き ダイアログのコントロールが無効にします。  
  
- PSD_RETURNDEFAULT により`CPageSetupDialog`を返す[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)  ダイアログ ボックスを表示せずにシステムの既定のプリンターの初期化されている構造体。 ように仮定両方`hDevNames`と`hDevMode`エラーを返しますそれ以外の場合は NULL です。 古いプリンター ドライバー (Windows バージョン 3.0 より前)、システムの既定のプリンターがサポートされている場合のみ`hDevNames`が返されます。`hDevMode`は NULL です。  
  
- PSD_DISABLEPAPER には、用紙の選択コントロールが無効にします。  
  
- PSD_SHOWHELP により、ダイアログ ボックスの [ヘルプ] ボタンを表示します。 `hwndOwner`このフラグが指定されている場合、メンバーは NULL を指定できません必要があります。  
  
- PSD_ENABLEPAGESETUPHOOK によりフック関数がで指定された`lpfnSetupHook`します。  
  
- PSD_ENABLEPAGESETUPTEMPLATE により、オペレーティング システムで識別される テンプレートを使用して、ダイアログ ボックスを作成する`hInstance`と`lpSetupTemplateName`します。  
  
- PSD_ENABLEPAGESETUPTEMPLATEHANDLE が示す`hInstance`プリロード済みのダイアログ ボックスのテンプレートが含まれるデータ ブロックを識別します。 無視されます`lpSetupTemplateName`このフラグが指定されている場合。  
  
- PSD_ENABLEPAGEPAINTHOOK によりフック関数がで指定された`lpfnPagePaintHook`します。  
  
- PSD_DISABLEPAGEPAINTING ダイアログ ボックスの描画領域を無効にします。  
  
 *pParentWnd*  
 ダイアログ ボックスの親または所有者へのポインター。  
  
### <a name="remarks"></a>Remarks  
 使用して、 [DoModal](../../mfc/reference/cdialog-class.md#domodal)  ダイアログ ボックスを表示する関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC  
 プリンター デバイス コンテキストを作成、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキスト (DC) へのハンドルします。  
  
##  <a name="domodal"></a>  CPageSetupDialog::DoModal  
 Windows 共通 OLE ページの設定 ダイアログ ボックスが表示され、印刷の余白、サイズと出力先プリンター、用紙の向きなどのさまざまな印刷のセットアップ オプションを選択できるようにするには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 IDOK や IDCANCEL。 IDCANCEL が返された場合は、Windows を呼び出す[情報を得る](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror)エラーが発生したかどうかを判断する関数。  
  
 IDOK や IDCANCEL は、ユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>Remarks  
 さらに、ネットワークの場所と、選択したプリンターに固有のプロパティなどのプリンター セットアップのオプションをユーザーにアクセスできます。  
  
 メンバーを設定して、さまざまなページ設定ダイアログ オプションを初期化する場合、`m_psd`構造、呼び出す前に行う必要があります`DoModal`、ダイアログ オブジェクトを構築後するとします。 呼び出した後`DoModal`、他のメンバー、ダイアログ ボックスに、設定やユーザーによって入力された情報を取得する関数を呼び出します。  
  
 呼び出しを行う場合は、ユーザーが入力した現在の設定を反映するには、[通知](../../mfc/reference/cwinapp-class.md#selectprinter)します。 この関数からの情報には、`CPageSetupDialog`オブジェクトしを初期化し、適切な属性を持つ新しいプリンター DC を選択します。  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>例  
  例をご覧ください[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)します。  
  
##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName  
 後は、この関数を呼び出す`DoModal`現在選択されているプリンターの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 使用されるデバイス名、`CPageSetupDialog`オブジェクト。  
  
##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode  
 この関数を呼び出した後`DoModal`のプリンター デバイス コンテキストに関する情報を取得、`CPageSetupDialog`オブジェクト。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)データ構造は、デバイスの初期化と印刷ドライバーの環境に関する情報が含まれています。 この構造体で、Windows によって使用されたメモリのロックを解除する必要があります[GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock)関数は、Windows SDK で説明します。  
  
##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName  
 この関数を呼び出した後[DoModal](../../mfc/reference/cprintdialog-class.md#domodal)プリンターのシステム定義のデバイス ドライバーの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `CString` driver のシステム定義の名前を指定します。  
  
### <a name="remarks"></a>Remarks  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins  
 呼び出しの後にこの関数を呼び出す`DoModal`プリンター デバイス ドライバーの余白を取得します。  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectMargins*  
 ポインターを[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)現在選択されているプリンターの印刷の余白 (1/1000 インチまたは 1/100 mm) で記述するオブジェクト。 この四角形に興味がない場合は、このパラメーターは、NULL を渡します。  
  
 *lpRectMinMargins*  
 ポインターを`RECT`構造または`CRect`現在選択されているプリンターの印刷の余白の最小値 (1/1000 インチまたは 1/100 mm) で記述するオブジェクト。 この四角形に興味がない場合は、このパラメーターは、NULL を渡します。  
  
##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize  
 印刷用に選択された用紙のサイズを取得するには、この関数を呼び出します。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)印刷用に選択 (1/1000 インチまたは 1/100 mm) で、用紙のサイズを含むオブジェクト。  
  
##  <a name="getportname"></a>  CPageSetupDialog::GetPortName  
 この関数を呼び出した後`DoModal`現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
##  <a name="m_psd"></a>  CPageSetupDialog::m_psd  
 型メンバーを持つダイアログ オブジェクトの特性を格納する PAGESETUPDLG の構造体。  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CPageSetupDialog`オブジェクトを使用する`m_psd`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、`DoModal`メンバー関数。  
  
 変更する場合、`m_psd`データ メンバーを直接、既定の動作をオーバーライドします。  
  
 詳細については、 [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda)構造体を Windows SDK を参照してください。  
  
 例をご覧ください[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)します。  
  
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
 描画されている現在のページの領域を示すメッセージを指定します。 次のいずれかの値を指定します。  
  
- WM_PSD_FULLPAGERECT ページ全体の領域。  
  
- 現在 WM_PSD_MINMARGINRECT 余白の最小値。  
  
- 現在 WM_PSD_MARGINRECT 余白。  
  
- ページの内容を WM_PSD_GREEKTEXTRECT です。  
  
- WM_PSD_ENVSTAMPRECT 領域が切手表現用に予約されています。  
  
- 戻り値のアドレス形式の WM_PSD_YAFULLPAGERECT 領域。 この領域は、サンプル ページ領域の端に拡張されます。  
  
 *lpRect*  
 ポインターを[CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)描画領域の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 処理された場合、0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このイメージは、共通の OLE ページの設定 ダイアログ ボックスの一部として表示されます。 既定の実装は、テキストのページのイメージを描画します。  
  
 イメージまたはイメージ全体の特定の領域の描画をカスタマイズするには、この関数をオーバーライドします。 使用してこれを行う、**切り替える**ステートメントを**ケース**の値をチェックするステートメント *%n メッセージ*します。 など、ページのイメージの内容の表示をカスタマイズするには、次のコード例を使用する可能性があります。  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 すべてのケースを処理する必要がないことに注意してください。 *%n*します。 イメージ、イメージ、または領域全体のいくつかのコンポーネントの 1 つのコンポーネントを処理するために選択できます。  
  
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
 用紙サイズを示す値を指定します。 この値は、のいずれかを指定できます、 **DMPAPER_** 値の説明に一覧表示、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)構造体。  
  
 *wflags が*  
 用紙または封筒の印刷の向きを示すかどうかは、プリンター、ドット マトリックスまたは HPPCL (Hewlett Packard Printer Control Language) デバイスとします。 このパラメーターには、次のいずれかの値を指定できます。  
  
-   0x001 用紙横モード (ドット マトリックス)  
  
-   0x003 用紙横モード (HPPCL)  
  
-   0x005 用紙の縦モード (ドット マトリックス)  
  
-   0x007 用紙の縦モード (HPPCL)  
  
-   0x00b 封筒横モード (HPPCL)  
  
-   0x00d (ドット マトリックス) の縦長表示モードの封筒  
  
-   0x019 封筒横モード (ドット マトリックス) で  
  
-   0x01f (ドット マトリックス) の縦長表示モードの封筒  
  
 *pPSD*  
 `PAGESETUPDLG` 構造体へのポインター。 詳細については[PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda)、Windows SDK を参照してください。  
  
### <a name="return-value"></a>戻り値  
 処理された場合、0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 イメージの描画をカスタマイズするには、この関数をオーバーライドします。 この関数をオーバーライドして TRUE を返す場合、イメージ全体を描画する必要があります。 この関数をオーバーライドして FALSE を返す場合、フレームワークによって全体の既定のイメージが描画されます。  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



