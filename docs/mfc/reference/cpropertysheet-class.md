---
title: CPropertySheet クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d265b2547f35e0c8c25ee5e3aad1135945e346b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853205"
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
|[呼び出します](#cpropertysheet)|`CPropertySheet` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[が](#addpage)|プロパティ シートにページを追加します。|  
|[まず、](#construct)|`CPropertySheet` オブジェクトを構築します。|  
|[CPropertySheet::Create](#create)|モードレス プロパティ シートを表示します。|  
|[する](#domodal)|モーダル プロパティ シートを表示します。|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|プロパティ シートが積み上げまたはスクロール タブを使用するかどうかを示します。|  
|[CPropertySheet::EndDialog](#enddialog)|プロパティ シートを終了します。|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|プロパティ シートのアクティブなページのインデックスを取得します。|  
|[CPropertySheet::GetActivePage](#getactivepage)|アクティブなページ オブジェクトを返します。|  
|[CPropertySheet::GetPage](#getpage)|指定したページへのポインターを取得します。|  
|[CPropertySheet::GetPageCount](#getpagecount)|プロパティ シートのページ数を取得します。|  
|[CPropertySheet::GetPageIndex](#getpageindex)|プロパティ シートの指定したページのインデックスを取得します。|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|タブ コントロールへのポインターを取得します。|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|四角形の単位 ダイアログ ボックスを画面の単位に変換します。|  
|[Cpropertysheet::oninitdialog](#oninitdialog)|プロパティ シートの初期化処理の強化をオーバーライドします。|  
|[CPropertySheet::PressButton](#pressbutton)|プロパティ シートの指定したボタンの選択をシミュレートします。|  
|[CPropertySheet::RemovePage](#removepage)|プロパティ シートからページを削除します。|  
|[CPropertySheet::SetActivePage](#setactivepage)|アクティブ ページ オブジェクトをプログラムで設定します。|  
|[CPropertySheet::SetFinishText](#setfinishtext)|[完了] ボタンのテキストを設定します。|  
|[CPropertySheet::SetTitle](#settitle)|プロパティ シートのキャプションを設定します。|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|ウィザード ボタンを有効にします。|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|ウィザードのモードを有効にします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造体。 基本プロパティ シートのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>Remarks  
 プロパティ シートから成る、`CPropertySheet`オブジェクトと 1 つ以上[CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクト。 フレームワークは、一連のタブ インデックスと、現在選択されているページが表示される領域を持つウィンドウとして、プロパティ シートを表示します。 ユーザーは、適切なタブを使用して、特定のページに移動します。  
  
 `CPropertySheet` 展開のサポートを提供します。 [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造がで導入された[!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)]および Windows NT 2000 です。 構造体には、追加のフラグと「透かし」の背景ビットマップを使用をサポートするメンバーが含まれています。  
  
 プロパティ シート オブジェクトに自動的にこれらの新しいイメージを表示するへの呼び出しでビットマップとパレットのイメージの有効な値を渡す[まず、](#construct)または[呼び出します](#cpropertysheet).  
  
 でも`CPropertySheet`から派生していない[CDialog](../../mfc/reference/cdialog-class.md)、管理、`CPropertySheet`管理などのオブジェクトが、`CDialog`オブジェクト。 たとえば、プロパティ シートの作成には 2 つの部分の構築が必要です: コンス トラクターを呼び出します[DoModal](#domodal)モーダル プロパティ シートまたは[作成](#create)モードレス プロパティ シート。 `CPropertySheet` コンス トラクターの 2 つの種類があります:[まず、](#construct)と[呼び出します](#cpropertysheet)します。  
  
 構築する際に、`CPropertySheet`オブジェクトに、いくつか[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)が発生する初回例外が発生することができます。 これは、結果、シートを作成する前に、プロパティ シートのスタイルを変更しようとしました。 システムからです。 この例外を回避するために、作成するときに、次のスタイルを設定することを確認、 `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 次のスタイルはオプションであり、初回の例外は発生しません。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 その他の`Window Styles`することはできませんし、有効にしない必要があります。  
  
 間のデータ交換、`CPropertySheet`オブジェクトおよび外部のオブジェクトがデータを交換するような`CDialog`オブジェクト。 重要な違いは、プロパティ シートの設定がのメンバー変数では通常、`CPropertyPage`オブジェクトのではなく、`CPropertySheet`オブジェクト自体です。  
  
 一連のデバイスの設定やニュースレターを作成するなどの操作の手順を追ってプロパティ ページのプロパティ シートで構成される、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページのタブがないと、一度に 1 つのプロパティ ページが表示されます。 ではなく、また、 **ok**と**今すぐ適用**ボタン、ウィザードの種類 タブのダイアログ ボックスには、**戻る** ボタン、 **次へ**または**完了**  ボタン、**キャンセル**ボタンと**ヘルプ**ボタン。  
  
 ウィザードの種類 ダイアログ ボックスを作成する呼び出しが、標準のプロパティ シートを作成する場合に同じ手順に従います[SetWizardMode](#setwizardmode)を呼び出す前に[DoModal](#domodal)します。 ウィザード ボタンを有効にするには呼び出します[開か](#setwizardbuttons)フラグを使用して、それらの機能と外観をカスタマイズします。 有効にする、**完了** ボタンを呼び出す[SetFinishText](#setfinishtext)後、ユーザーは、ウィザードの最後のページに対してアクションを実行するがします。  
  
 使用する方法の詳細についての`CPropertySheet`オブジェクトは、記事をご覧ください。[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)します。 また、サポート技術情報記事 Q146916 を参照してください: HOWTO: 標準のボタンを持つモードレス CPropertySheet を作成し、Q300606 の記事: HOWTO: サイズ変更可能な MFC のプロパティ シートをデザインします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="addpage"></a>  が  
 プロパティ シートで指定した右端のタブ ページを追加します。  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPage*  
 プロパティ シートに追加するページへのポインター。 Nll は指定できません。  
  
### <a name="remarks"></a>Remarks  
 ページを表示する左から右の順序でプロパティ シートに追加します。  
  
 `AddPage` 追加、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)オブジェクトを`CPropertySheet`オブジェクトのページの一覧は、ページのウィンドウを実際には作成されません。 フレームワークは、ユーザーがそのページを選択するまで、ページのウィンドウの作成を延期します。  
  
 使用してプロパティ ページを追加すると`AddPage`、`CPropertySheet`の親である、`CPropertyPage`します。 プロパティ シートにプロパティ ページからアクセスを取得するには、呼び出す[CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)します。  
  
 ウィンドウの作成、プロパティ シートを呼び出すまで待機する必要はありません`AddPage`します。 呼び出すことは通常、`AddPage`呼び出す前に[DoModal](#domodal)または[作成](#create)です。  
  
 呼び出す場合`AddPage`プロパティ ページを表示した後、タブ行が新しく追加されたページを反映します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="construct"></a>  まず、  
 `CPropertySheet` オブジェクトを構築します。  
  
```  
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
 *nIDCaption*  
 プロパティ シートに使用されるキャプションの ID。  
  
 *pParentWnd*  
 プロパティ シートの親ウィンドウへのポインター。 NULL の場合、親ウィンドウは、アプリケーションのメイン ウィンドウになります。  
  
 *iSelectPage*  
 ページ上部になる最初のインデックス。 既定値は、最初のページのシートに追加します。  
  
 *pszCaption*  
 プロパティ シートに使用されるキャプションを表す文字列へのポインター。 Nll は指定できません。  
  
 *hbmWatermark*  
 プロパティ ページのウォーターマーク ビットマップへのハンドルします。  
  
 *hpalWatermark*  
 ウォーターマーク ビットマップおよびヘッダー ビットマップのパレットへのハンドルします。  
  
 *hbmHeader*  
 プロパティ ページのヘッダー ビットマップへのハンドルします。  
  
### <a name="remarks"></a>Remarks  
 クラスのコンス トラクターのいずれかが既に呼び出されていない場合は、このメンバー関数を呼び出します。 たとえば、呼び出す`Construct`と宣言するかの配列を割り当てます`CPropertySheet`オブジェクト。 呼び出す必要があります、配列の場合`Construct`配列内の各メンバーにします。  
  
 プロパティ シートを表示するには、呼び出す[DoModal](#domodal)または[作成](#create)です。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 自動的の 3 番目か 4 番目のプロトタイプを使用する場合、ウォーターマークやヘッダー イメージを表示することができます`Construct`や、上記の有効な値を渡して、 *hbmWatermark*、 *hpalWatermark*、または*hbmHeader*パラメーター。  
  
### <a name="example"></a>例  
 次の例は、下で呼び出しをどのような場合は`Construct`。  
  
 [!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="cpropertysheet"></a>  呼び出します  
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
 *nIDCaption*  
 プロパティ シートに使用されるキャプションの ID。  
  
 *pParentWnd*  
 プロパティ シートの親ウィンドウへのポインター。 NULL の場合、親ウィンドウは、アプリケーションのメイン ウィンドウになります。  
  
 *iSelectPage*  
 ページ上部になる最初のインデックス。 既定値は、最初のページのシートに追加します。  
  
 *pszCaption*  
 プロパティ シートに使用されるキャプションを表す文字列を指します。 Nll は指定できません。  
  
 *hbmWatermark*  
 プロパティ シートの背景ビットマップへのハンドル。  
  
 *hpalWatermark*  
 ウォーターマーク ビットマップおよびヘッダー ビットマップのパレットへのハンドル。  
  
 *hbmHeader*  
 プロパティ ページのヘッダー ビットマップへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 プロパティ シートを表示するには、呼び出す[DoModal](#domodal)または[作成](#create)です。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 使用して、複数のパラメーター (たとえば、配列を使用している場合) があれば、[構築](#construct)の代わりに`CPropertySheet`します。  
  
 自動的の 3 番目か 4 番目のプロトタイプを使用する場合、ウォーターマークやヘッダー イメージを表示することができます`CPropertySheet`、上記有効な値を渡すと、 *hbmWatermark*、 *hpalWatermark*、/または*hbmHeader*パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>  CPropertySheet::Create  
 モードレス プロパティ シートを表示します。  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 親ウィンドウへのポインター。 NULL の場合、親はデスクトップです。  
  
 *dwStyle*  
 プロパティ シートのウィンドウ スタイル。 使用可能なスタイルの完全な一覧を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。  
  
 *dwExStyle*  
 プロパティ シートの拡張ウィンドウ スタイル。 使用可能なスタイルの完全な一覧を参照してください[拡張ウィンドウ スタイル。](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常に作成された場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し`Create`コンス トラクター内で使用できますか、コンス トラクターが呼び出された後に呼び出すことができます。  
  
 既定のスタイル、として-1 を渡すことによって表される*dwStyle*、WS_SYSMENU 実際には、&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;WS_VISIBLE します。 既定の拡張ウィンドウ スタイル、として 0 を渡すことによって表される*dwExStyle*、WS_EX_DLGMODALFRAME 実際には、します。  
  
 `Create`プロパティ シートを作成した直後にメンバー関数を返します。 プロパティ シートを破棄するには、呼び出す[に](../../mfc/reference/cwnd-class.md#destroywindow)します。  
  
 呼び出しをモードレス プロパティ シート`Create`モーダル プロパティ シートと同様に [ok]、[キャンセル] を今すぐ適用、およびヘルプのボタンはありません。 必要なボタンは、ユーザーが作成する必要があります。  
  
 モーダル プロパティ シートを表示するには、呼び出す[DoModal](#domodal)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>  する  
 モーダル プロパティ シートを表示します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 IDOK や IDCANCEL 関数が成功した場合それ以外の場合 0 または-1。 ウィザードとしてプロパティ シートが確立されているかどうか (を参照してください[SetWizardMode](#setwizardmode))、 `DoModal` ID_WIZFINISH または IDCANCEL のいずれかを返します。  
  
### <a name="remarks"></a>Remarks  
 戻り値は、プロパティ シートを終了しているコントロールの ID に対応します。 この関数を返した後、プロパティ シートとすべてのページに対応する windows は破棄されます。 オブジェクト自体は残ります。 データを取得する、通常、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)後オブジェクト`DoModal`IDOK を返します。  
  
 モードレス プロパティ シートを表示するには、呼び出す[作成](#create)代わりにします。  
  
 プロパティ ページが対応するダイアログ リソースから作成されると、初回例外を発生することができます。 これは、ページを作成する前に、必要なスタイルにダイアログ リソースのスタイルを変更するプロパティ ページからの結果します。 リソースは通常読み取り専用であるために、例外が発生します。 システムは、例外を処理し、更新されたリソースのコピーを作成します。 したがって、初回例外は無視できます。  
  
> [!NOTE]
>  この例外は、非同期の例外処理モデルを使ってコンパイルする場合、オペレーティング システムで処理する必要があります。 例外処理モデルの詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)します。 この場合への呼び出しをラップしないでください`CPropertySheet::DoModal`C++ try catch ブロックと catch が処理するすべての例外では、たとえば、 `catch (...)`。 このブロックには、オペレーティング システム、および予期しない動作の原因は、例外を処理とします。 ただし、C++ 例外、アクセス違反例外が、オペレーティング システムに渡される特定の例外の種類または構造化例外処理で処理を安全に使用できます。  
  
 この初回の例外の生成を避けるため、手動で保証できるプロパティ シートに正しい[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。 次のプロパティ シートのスタイルを設定する必要があります。  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 初回例外を発生させることがなく、次の省略可能なスタイルを使用できます。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 プロパティ シートと互換性がないために、他のすべての Windows スタイルを無効にします。 このアドバイスは、拡張スタイルには適用されません。 これらの標準的なスタイルを適切に設定すると、プロパティ シートを変更する必要はありませんし、初回例外が生成されないようにが保証されます。  
  
### <a name="example"></a>例  
  例をご覧ください[が](#addpage)します。  
  
##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs  
 プロパティ シートのタブの行をスタックするかどうかを示します。  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>パラメーター  
 *bStacked*  
 プロパティ シートのタブ行の積み上げを有効かどうかを示します。 タグの積み上げられた行を設定して無効に*bStacked*を FALSE にします。  
  
### <a name="remarks"></a>Remarks  
 既定では、プロパティ シート、プロパティ シートの幅に 1 行に収まらないのタブがある場合、タブは複数の行に積み重ねられます。 タブではなくスクロールのタブを使用する`EnableStackedTabs`で*bStacked*呼び出す前に FALSE に設定[DoModal](#domodal)または[作成](#create)です。  
  
 呼び出す必要があります`EnableStackedTabs`モーダルまたはモードレス プロパティ シートを作成する場合。 このスタイルで、 `CPropertySheet`-派生クラスでの WM_CREATE メッセージ ハンドラーを記述します。 オーバーライドされたバージョンの[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、呼び出す`EnableStackedTabs( FALSE )`基本クラスの実装を呼び出す前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>  CPropertySheet::EndDialog  
 プロパティ シートを終了します。  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nEndID*  
 プロパティ シートの戻り値として使用する識別子です。  
  
### <a name="remarks"></a>Remarks  
 [Ok]、[キャンセル] または [閉じる] ボタンが押されたときに、このメンバー関数は、フレームワークによって呼び出されます。 呼び出しは、イベントが発生した場合は、このメンバー関数は、プロパティ シートを閉じる必要があります。  
  
 このメンバー関数は、モーダル ダイアログ ボックスでのみ使用されます。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertySheet::PressButton](#pressbutton)します。  
  
##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex  
 プロパティ シート ウィンドウのアクティブなページのインデックス番号を取得し、パラメーターとして返されるインデックス番号を使用し、`GetPage`します。  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブなページのインデックス番号。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage  
 プロパティ シート ウィンドウのアクティブなページを取得します。  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 作業中のページへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を使用すると、アクティブなページで何らかのアクションを実行できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>  CPropertySheet::GetPage  
 このプロパティ シートで指定したページへのポインターを返します。  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *n ページ レイアウト*  
 0 から始まる、目的のページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいの間である必要があります。  
  
### <a name="return-value"></a>戻り値  
 対応するページへのポインター、 *n ページ レイアウトの*パラメーター。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)します。  
  
##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount  
 プロパティ シートの現在のページの数を決定します。  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートにページの数。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)します。  
  
##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex  
 プロパティ シートで指定したページのインデックス番号を取得します。  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPage*  
 検索するインデックスを持つページへのポインター。 Nll は指定できません。  
  
### <a name="return-value"></a>戻り値  
 ページのインデックス番号。  
  
### <a name="remarks"></a>Remarks  
 たとえば、使用すると`GetPageIndex`使用するには、ページのインデックスを取得する[行ったとき](#setactivepage)または[GetPage](#getpage)します。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl  
 タブ コントロールに固有のものを実行するタブ コントロールへのポインターを取得します (つまり、Api のいずれかを使用する[CTabCtrl](../../mfc/reference/ctabctrl-class.md))。  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールへのポインター。  
  
### <a name="remarks"></a>Remarks  
 たとえば、初期化中に、それぞれのタブにビットマップを追加する場合は、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>  CPropertySheet::m_psh  
 メンバーの格納の特性構造[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)します。  
  
### <a name="remarks"></a>Remarks  
 表示される前に、構築した後、プロパティ シートの外観を初期化するためにこの構造体を使用して、 [DoModal](#domodal)メンバー関数。 たとえば、設定、 *dwSize*のメンバー`m_psh`がプロパティ シートのサイズにします。  
  
 詳細については、そのメンバーの一覧を含む、この構造では、PROPSHEETHEADER Windows sdk を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect  
 四角形の単位 ダイアログ ボックスを画面の単位に変換します。  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスのテキストに使用されるフォントの文字の高さと幅の平均から派生した現在のダイアログ ボックス ベース ユニットの観点からは、ダイアログ ボックスのユニットが記載されています。 水平方向の 1 つの単位がベースの幅の単位をダイアログ ボックスの 4 分の 1 と垂直方向の 1 つの単位が 8 分の 1 ダイアログ ボックスの高さの基本単位です。  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows 関数が、システム フォントのサイズ情報を返しますが、リソース定義ファイルで DS_SETFONT スタイルを使用する場合は、プロパティ シートごとに別のフォントを指定できます。 [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) Windows SDK で説明されている Windows 関数がこのダイアログ ボックスの適切なフォントを使用します。  
  
 `MapDialogRect`メンバー関数は、ダイアログ ボックスの単位*lpRect*で画面の単位 (ピクセル単位) ダイアログ ボックスを作成したり、ボックス内のコントロールの位置四角形を使用できるようにします。  
  
##  <a name="oninitdialog"></a>  Cpropertysheet::oninitdialog  
 プロパティ シートの初期化処理を強化するよりも優先されます。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがプロパティ シート内のコントロールのいずれかに入力フォーカスを設定するかどうかを指定します。 場合`OnInitDialog`戻り値は 0 以外の場合、Windows で、プロパティ シートの最初のコントロールに入力フォーカスが設定します。 アプリケーションは、入力のフォーカスをプロパティ シート内のコントロールのいずれかに明示的に設定した場合にのみ、0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は WM_INITDIALOG メッセージへの応答で呼び出されます。 中にプロパティ シートにこのメッセージが送信される、[作成](#create)または[DoModal](#domodal)呼び出しで、プロパティ シートを表示する直前に発生します。  
  
 プロパティ シートが初期化されるときに、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、基本クラスを呼び出す最初`OnInitDialog`が、その戻り値を無視します。 通常は、オーバーライドされたメンバー関数から TRUE を返します。  
  
 このメンバー関数のメッセージ マップ エントリを必要はありません。  
  
##  <a name="pressbutton"></a>  CPropertySheet::PressButton  
 プロパティ シートの指定したボタンの選択をシミュレートします。  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>パラメーター  
 *n ボタン*  
 n ボタン: ボタンが押されるを識別します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- PSBTN_BACK では、[戻る] ボタンを選択します。  
  
- PSBTN_NEXT では、[次へ] ボタンを選択します。  
  
- PSBTN_FINISH では、[完了] ボタンを選択します。  
  
- PSBTN_OK では、[ok] ボタンを選択します。  
  
- PSBTN_APPLYNOW では、今すぐ適用 ボタンを選択します。  
  
- PSBTN_CANCEL では、[キャンセル] ボタンを選択します。  
  
- PSBTN_HELP では、[ヘルプ] ボタンを選択します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) Windows SDK Pressbutton メッセージの詳細についてはします。  
  
 呼び出し`PressButton`は送信しません、 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)プロパティ ページから、フレームワークへの通知。 この通知を送信する呼び出し[送るに](../../mfc/reference/cpropertypage-class.md#onok)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>  CPropertySheet::RemovePage  
 プロパティ シートからページを削除し、関連するウィンドウを破棄します。  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPage*  
 プロパティ シートから削除するページへのポインター。 Nll は指定できません。  
  
 *n ページ レイアウト*  
 削除するページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいの間である必要があります。  
  
### <a name="remarks"></a>Remarks  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)までの所有者はオブジェクト自体は破棄されません、`CPropertySheet`ウィンドウが閉じられます。  
  
##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage  
 アクティブなページを変更します。  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *n ページ レイアウト*  
 設定するページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいかでなければなりません。  
  
 *pPage*  
 プロパティ シートに設定するページへのポインター。 NULL にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常にアクティブ化される場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 たとえば、使用して`SetActivePage`場合は 1 つのページで、ユーザーの操作になるアクティブなページの別のページが発生する必要があります。  
  
### <a name="example"></a>例  
  例をご覧ください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText  
 [完了] のコマンド ボタンのテキストを設定します。  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 [完了] のコマンド ボタンに表示されるテキストを指します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SetFinishText`完了 のコマンド ボタンのテキストを表示し、ユーザーが、ウィザードの最後のページ上のアクションが完了したら、次へと戻るボタンを非表示にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>  CPropertySheet::SetTitle  
 プロパティ シートのキャプション (フレーム ウィンドウのタイトル バーに表示されるテキスト) を指定します。  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStyle*  
 プロパティ シートのタイトルのスタイルを指定します。 0 または PSH_PROPTITLE、スタイルを指定する必要があります。 PSH_PROPTITLE としてスタイルを設定すると、キャプションとして指定されたテキストの後に"Properties"という単語が表示されます。 たとえば、呼び出し`SetTitle`「単純なプロパティです」のプロパティ シートのタイトルに ("Simple"、PSH_PROPTITLE) になります。  
  
 *lpszText*  
 プロパティ シートのタイトル バーのキャプションとして使用するテキストを指します。  
  
### <a name="remarks"></a>Remarks  
 既定では、プロパティ シートは、プロパティ シートのコンス トラクターでキャプション パラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons  
 有効または、ウィザードのプロパティ シートに戻し、Next、または [完了] ボタンを無効にします。  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 関数とウィザードのボタンの外観をカスタマイズするフラグのセット。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- PSWIZB_BACK 戻るボタン  
  
- PSWIZB_NEXT [次へ] ボタン  
  
- PSWIZB_FINISH [完了] ボタン  
  
- PSWIZB_DISABLEDFINISH 無効になっている [完了] ボタン  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SetWizardButtons`ダイアログが開いています。 後でのみ呼び出すことができません`SetWizardButtons`を呼び出す前に[DoModal](#domodal)します。 通常を呼び出す必要があります`SetWizardButtons`から[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)します。  
  
 [完了] ボタンのテキストを変更または、[次へ] を非表示にして、戻るボタンの 1 回、ユーザーの場合に、ウィザードでは、呼び出しが完了[SetFinishText](#setfinishtext)します。 [完了] と [次へ] の同じボタンが共有されることに注意してください。 [完了] または [次へ] ボタンを一度に 1 つが、両方を表示することができます。  
  
### <a name="example"></a>例  
 A`CPropertySheet`は 3 つのウィザードのプロパティ ページがあります: `CStylePage`、 `CColorPage`、および`CShapePage`します。  次のコード片は、有効または無効にする方法を示します、**戻る**と**次**ウィザードの [プロパティ] ページのボタン。  
  
 [!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode  
 ウィザードとしてのプロパティ ページを確立します。  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Remarks  
 ウィザードのプロパティ ページの重要な特性は、ユーザー次を使用して移動しますか [完了]、バックアップ、キャンセル ボタン タブの代わりにです。  
  
 呼び出す`SetWizardMode`呼び出す前に[DoModal](#domodal)します。 呼び出した後`SetWizardMode`、 `DoModal` ID_WIZFINISH (この場合、ユーザーは、[完了] ボタンが終了) または IDCANCEL のいずれかが返されます。  
  
 `SetWizardMode` PSH_WIZARD フラグを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



