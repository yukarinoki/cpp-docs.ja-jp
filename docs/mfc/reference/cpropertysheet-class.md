---
title: CPropertySheet クラス |Microsoft ドキュメント
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
ms.openlocfilehash: e7b49aba6ea5d2397baa0dc72f36b2693810fbeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377463"
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
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|プロパティ シートが積み上げまたはスクロールのタブを使用するかどうかを示します。|  
|[CPropertySheet::EndDialog](#enddialog)|プロパティ シートを終了します。|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|プロパティ シートのアクティブなページのインデックスを取得します。|  
|[CPropertySheet::GetActivePage](#getactivepage)|アクティブなページ オブジェクトを返します。|  
|[CPropertySheet::GetPage](#getpage)|指定したページへのポインターを取得します。|  
|[CPropertySheet::GetPageCount](#getpagecount)|プロパティ シートのページ数を取得します。|  
|[CPropertySheet::GetPageIndex](#getpageindex)|プロパティ シートの指定したページのインデックスを取得します。|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|タブ コントロールへのポインターを取得します。|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面の単位に変換します。|  
|[Cpropertysheet::oninitdialog](#oninitdialog)|プロパティ シートの初期化処理を拡張するためにオーバーライドします。|  
|[CPropertySheet::PressButton](#pressbutton)|プロパティ シートで指定されたボタンの選択肢をシミュレートします。|  
|[CPropertySheet::RemovePage](#removepage)|プロパティ シートからページを削除します。|  
|[CPropertySheet::SetActivePage](#setactivepage)|アクティブ ページ オブジェクトをプログラムで設定します。|  
|[CPropertySheet::SetFinishText](#setfinishtext)|[完了] ボタンのテキストを設定します。|  
|[CPropertySheet::SetTitle](#settitle)|プロパティ シートのキャプションを設定します。|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|ウィザードのボタンを有効にします。|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|ウィザード モードを有効にします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造体。 基本的なプロパティ シートのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 プロパティ シートから成る、`CPropertySheet`オブジェクトと 1 つ以上[CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクト。 フレームワークは、一連のタブ インデックスを持ち、現在選択されているページが含まれる領域でのウィンドウとして、プロパティ シートを表示します。 ユーザーは、適切なタブを使用して、特定のページに移動します。  
  
 `CPropertySheet` 展開のサポートを提供[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造がで導入された[!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)]および Windows NT 2000 です。 構造体には、追加のフラグと"watermark"背景ビットマップの使用をサポートするメンバーが含まれています。  
  
 プロパティ シート オブジェクトに自動的にこれらの新しいイメージを表示するには、呼び出しでは、パレットとビットマップ イメージの有効な値を渡す[まず、](#construct)または[呼び出します](#cpropertysheet).  
  
 にもかかわらず`CPropertySheet`から派生していない[CDialog](../../mfc/reference/cdialog-class.md)、管理、`CPropertySheet`オブジェクトは管理と同様、`CDialog`オブジェクト。 たとえば、プロパティ シートの作成には 2 つの部分の構築が必要です: コンス トラクターを呼び出します[DoModal](#domodal) 、モーダル プロパティ シートまたは[作成](#create)モードレス プロパティ シートのです。 `CPropertySheet` コンス トラクターの 2 つの種類があります:[まず、](#construct)と[呼び出します](#cpropertysheet)です。  
  
 構築する場合、`CPropertySheet`オブジェクト一部[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)初回例外が発生する可能性があります。 これは、シートを作成する前に、プロパティ シートのスタイルを変更しようとしました。 システムに起因します。 この例外を回避するのには、作成するときに、次のスタイルを設定することを確認してください、 `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 次のスタイルはオプションであり、初回例外は発生しません。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 その他の`Window Styles`は禁止する必要がありますいないを有効にすることです。  
  
 間のデータ交換、`CPropertySheet`オブジェクトおよび外部のオブジェクトがデータを交換に似ていますが、`CDialog`オブジェクト。 重要な相違点は、プロパティ シートの設定は、通常のメンバー変数を`CPropertyPage`オブジェクトのではなく、`CPropertySheet`オブジェクト自体です。  
  
 デバイスのセットアップやニュースレターを作成するなど、操作の手順を追ってプロパティ ページのシーケンスを持つプロパティ シートで構成される、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページには、タブはありません。 と、一度に 1 つのプロパティ ページが表示されます。 しなくても、 **OK**と**今すぐ適用**ボタン、ウィザードの種類 タブ ダイアログ ボックスには、**戻る**ボタン、 **次へ**または**完了**ボタン、**キャンセル**ボタン、および**ヘルプ**ボタンをクリックします。  
  
 ウィザードの種類 ダイアログ ボックスを作成する手順は同じ呼び出しが、標準のプロパティ シートを作成した後に続きます[SetWizardMode](#setwizardmode)を呼び出す前に[DoModal](#domodal)です。 ウィザードのボタンを有効にするを呼び出す[開か](#setwizardbuttons)フラグを使用して、機能と外観をカスタマイズします。 有効にする、**完了** ボタンを呼び出す[SetFinishText](#setfinishtext)ユーザーは、ウィザードの最後のページの処置を行って後です。  
  
 使用する方法の詳細についての`CPropertySheet`、オブジェクトが、記事を参照して[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)です。 また、サポート技術情報の記事 Q146916 を参照して: HOWTO: 標準のボタンを持つモードレス CPropertySheet を作成し、記事 Q300606: HOWTO: サイズ変更可能な MFC プロパティ シートをデザインします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="addpage"></a>  が  
 プロパティ シートで指定した右端のタブ ページを追加します。  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 プロパティ シートに追加するページへのポインター。 ことはできません**NULL**です。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを表示したい左から右へ順番にページを追加します。  
  
 `AddPage` 追加、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)オブジェクトを`CPropertySheet`オブジェクトのページの一覧は、ページは、ウィンドウを実際には作成されません。 フレームワークは、ユーザーがそのページを選択するまで、ページは、ウィンドウの作成を延期します。  
  
 使用してプロパティ ページを追加すると`AddPage`、`CPropertySheet`の親である、`CPropertyPage`です。 アクセスするために、プロパティ シートに プロパティ ページで、呼び出す[CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)です。  
  
 ウィンドウの作成、プロパティ シートを呼び出すまで待機する必要はありません`AddPage`です。 通常が呼び出す`AddPage`呼び出す前に[DoModal](#domodal)または[作成](#create)です。  
  
 呼び出す場合`AddPage`タブ行プロパティ ページを表示するには、後に新しく追加されたページが反映されます。  
  
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
 `nIDCaption`  
 プロパティ シートをするためのキャプションの ID です。  
  
 `pParentWnd`  
 プロパティ シートの親ウィンドウへのポインター。 場合**NULL**、親ウィンドウが、アプリケーションのメイン ウィンドウになります。  
  
 `iSelectPage`  
 一番上になる最初に、ページのインデックス。 既定値は、最初のページがシートに追加します。  
  
 `pszCaption`  
 プロパティ シートに使用されるキャプションを表す文字列へのポインター。 ことはできません**NULL**です。  
  
 `hbmWatermark`  
 プロパティ ページの透かしビットマップへのハンドルします。  
  
 `hpalWatermark`  
 透かしビットマップやヘッダー ビットマップのパレットへのハンドルします。  
  
 `hbmHeader`  
 プロパティ ページのヘッダー ビットマップへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 クラスのコンス トラクターのいずれかが既に呼び出されていない場合は、このメンバー関数を呼び出します。 たとえば、呼び出す`Construct`ときに、宣言するかの配列を割り当てます`CPropertySheet`オブジェクト。 場合は、配列を呼び出す必要があります`Construct`配列内の各メンバーにします。  
  
 プロパティ シートを表示するには、呼び出す[DoModal](#domodal)または[作成](#create)です。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 自動的に、4 番目または 3 のプロトタイプを使用する場合、ウォーターマークやヘッダー イメージを表示することができます`Construct`上記の有効な値を渡す、 `hbmWatermark`、 `hpalWatermark`、や`hbmHeader`パラメーター。  
  
### <a name="example"></a>例  
 下にある次の例を呼び出します。 どのような場合、 `Construct`。  
  
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
 `nIDCaption`  
 プロパティ シートをするためのキャプションの ID です。  
  
 `pParentWnd`  
 プロパティ シートの親ウィンドウへのポインター。 場合**NULL**、親ウィンドウが、アプリケーションのメイン ウィンドウになります。  
  
 `iSelectPage`  
 一番上になる最初に、ページのインデックス。 既定値は、最初のページがシートに追加します。  
  
 `pszCaption`  
 プロパティ シートに使用されるキャプションを表す文字列へのポインター。 ことはできません**NULL**です。  
  
 `hbmWatermark`  
 プロパティ シートの背景ビットマップへのハンドル。  
  
 `hpalWatermark`  
 透かしビットマップやヘッダー ビットマップのパレットへのハンドル。  
  
 `hbmHeader`  
 プロパティ ページのヘッダー ビットマップへのハンドル。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを表示するには、呼び出す[DoModal](#domodal)または[作成](#create)です。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 複数のパラメーター (たとえば、配列を使用している場合) があればを使用して[構築](#construct)の代わりに`CPropertySheet`です。  
  
 自動的に、4 番目または 3 のプロトタイプを使用する場合、ウォーターマークやヘッダー イメージを表示することができます`CPropertySheet`、上記の有効な値を渡すと、 `hbmWatermark`、 `hpalWatermark`、や`hbmHeader`パラメーター。  
  
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
 `pParentWnd`  
 親ウィンドウへのポインター。 場合**NULL**親は、デスクトップです。  
  
 `dwStyle`  
 プロパティ シートのウィンドウ スタイル。 使用可能なスタイルの一覧については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 `dwExStyle`  
 プロパティ シートの拡張ウィンドウ スタイル。 使用可能なスタイルの一覧については、次を参照してください[拡張ウィンドウ スタイル。](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し**作成**コンス トラクター内に含めることができますか、コンス トラクターが呼び出された後に呼び出すことができます。  
  
 既定のスタイル、として-1 を渡すことによって表される`dwStyle`、実際には、 **WS_SYSMENU&#124;**`WS_POPUP`**&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;ws _表示されている**です。 既定の拡張ウィンドウ スタイル、として 0 を渡すことによって表される`dwExStyle`、実際には、 **WS_EX_DLGMODALFRAME**です。  
  
 **作成**プロパティ シートの作成後すぐにメンバー関数を返します。 プロパティ シートを破棄するには、呼び出す[に](../../mfc/reference/cwnd-class.md#destroywindow)です。  
  
 呼び出して表示されるモードレス プロパティ シート**作成**モーダル プロパティ シートのように ok、キャンセル、今すぐ適用およびヘルプ ボタンはありません。 目的のボタンは、ユーザーによって作成する必要があります。  
  
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
 `IDOK` または`IDCANCEL`関数が成功以外の場合はそれ以外の場合 0 または-1 の場合。 ウィザードとして、プロパティ シートが確立されたかどうか (を参照してください[SetWizardMode](#setwizardmode))、`DoModal`どちらかを返します`ID_WIZFINISH`または`IDCANCEL`です。  
  
### <a name="remarks"></a>コメント  
 戻り値は、プロパティ シートを閉じ、コントロールの ID に対応します。 この関数が返されると、プロパティ シートとすべてのページに対応する、windows は破棄されます。 オブジェクト自体が残っています。 通常からデータを取得する、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)後オブジェクト`DoModal`を返します`IDOK`です。  
  
 モードレス プロパティ シートを表示するには、呼び出す[作成](#create)代わりにします。  
  
 対応するダイアログ リソースからプロパティ ページが作成されると、初回例外を発生することができます。 これは、結果、プロパティ ページで、ページが作成される前に、必要なスタイルにダイアログ リソースのスタイルを変更します。 リソースは通常読み取り専用であるために、例外が発生します。 システムは、例外を処理し、更新されたリソースのコピーを作成します。 そのため、初回例外は無視できます。  
  
> [!NOTE]
>  非同期の例外処理モデルを使ってコンパイルする場合は、オペレーティング システムによってこの例外を処理する必要があります。 例外処理モデルの詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)です。 ここへの呼び出しをラップしないでください`CPropertySheet::DoModal`C++ try catch ブロックと catch が処理するすべての例外では、たとえば、`catch (...)`です。 このブロックでは、オペレーティング システム、および予期しない動作の原因のためのものでは、例外を処理します。 ただし、C++ 例外処理の特定の例外の型または構造化例外処理アクセス違反は、例外が、オペレーティング システムに渡されるを安全に使用できます。  
  
 この初回例外を生成するためには、手動でを保証できる場合、プロパティ シートが正しいこと[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。 次のプロパティ シートのスタイルを設定する必要があります。  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 初回例外を発生させることがなく、次の省略可能なスタイルを使用できます。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 プロパティ シートと互換性がないために、他のすべてのウィンドウ スタイルを無効にします。 このアドバイスは、拡張スタイルには適用されません。 これらの標準のスタイルを適切に設定すると、プロパティ シートを変更する必要はありませんし、初回例外が生成されないようにが保証されます。  
  
### <a name="example"></a>例  
  例を参照して[が](#addpage)です。  
  
##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs  
 プロパティ シートのタブの行をスタックするかどうかを示します。  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStacked`  
 プロパティ シートに積み上げられたタブを有効にするかどうかを示します。 積み上げ行タグの設定を無効に`bStacked`に**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ シート、プロパティ シートの幅内の単一行に収まらないのタブがある場合、タブは複数の行に積み重ねられます。 スクロールのタブを使用して、タブではなくを呼び出す`EnableStackedTabs`で`bStacked`に設定**FALSE**呼び出す前に[DoModal](#domodal)または[作成](#create)です。  
  
 呼び出す必要があります`EnableStackedTabs`モーダルまたはモードレス プロパティ シートを作成する場合。 このスタイルで、 `CPropertySheet`-派生クラスでは、メッセージ ハンドラーの記述の`WM_CREATE`します。 オーバーライドのバージョンので[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、呼び出す**は、(FALSE)** 基底クラスの実装を呼び出す前にします。  
  
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
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[ok]、[キャンセル] または [閉じる] ボタンが押されたときにフレームワークによって呼び出されます。 呼び出しは、イベントが発生した場合、このメンバー関数は、プロパティ シートを閉じる必要があります。  
  
 このメンバー関数はモーダル ダイアログ ボックスでのみ使用します。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::PressButton](#pressbutton)です。  
  
##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex  
 プロパティ シート ウィンドウのアクティブ ページのインデックス番号を取得し、パラメーターとして返されるインデックス番号を使用して`GetPage`です。  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブ ページのインデックス番号します。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetActivePage](#getactivepage)です。  
  
##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage  
 プロパティ シート ウィンドウのアクティブ ページを取得します。  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 作業中のページへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、アクティブなページに対してアクションを実行します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>  CPropertySheet::GetPage  
 このプロパティ シートで指定したページへのポインターを返します。  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPage`  
 0 から始まる、目的のページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいとの間でなければなりません。  
  
### <a name="return-value"></a>戻り値  
 対応するページへのポインター、`nPage`パラメーター。  
  
### <a name="example"></a>例  
  例を参照して[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)です。  
  
##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount  
 プロパティ シートの現在のページの数を決定します。  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シート内のページの数。  
  
### <a name="example"></a>例  
  例を参照して[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)です。  
  
##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex  
 プロパティ シートで指定したページのインデックス番号を取得します。  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 検索するインデックスを使用してページへのポインター。 ことはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 ページのインデックス番号します。  
  
### <a name="remarks"></a>コメント  
 たとえば、使用するよう`GetPageIndex`を使用するために ページのインデックスを取得する[行ったとき](#setactivepage)または[GetPage](#getpage)です。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetActivePage](#getactivepage)です。  
  
##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl  
 タブ コントロールに固有の処理を行うタブ コントロールへのポインターを取得します (つまりの Api を使用する[CTabCtrl](../../mfc/reference/ctabctrl-class.md))。  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールへのポインター。  
  
### <a name="remarks"></a>コメント  
 たとえば、初期化中に、それぞれのタブにビットマップを追加する場合は、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>  CPropertySheet::m_psh  
 構造体のメンバーの特性を保持する[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)です。  
  
### <a name="remarks"></a>コメント  
 表示されるまでは、構築された後に、プロパティ シートの外観を初期化するためにこの構造体を使用して、 [DoModal](#domodal)メンバー関数。 たとえば、設定、`dwSize`のメンバー`m_psh`がプロパティ シートのサイズにします。  
  
 そのメンバーの一覧を含めて、この構造の詳細についてを参照してください。 **PROPSHEETHEADER** Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect  
 四角形のダイアログ ボックスの単位を画面の単位に変換します。  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ単位は、に関して、平均の幅と高さの使用 ダイアログ ボックスのテキストのフォントの文字から派生した現在のダイアログ ボックス基本単位です。 水平方向に 1 つのユニットのダイアログ ボックスのベースの幅単位の 4 分の 1、垂直方向の 1 つの単位 ダイアログ ボックスの高さの基本単位の 8 分の 1。  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows 関数はシステム フォントのサイズ情報を返しますを使用する場合は、プロパティ シートごとに別のフォントを指定することができます、 **DS_SETFONT**のスタイルを設定しますリソース定義ファイルです。 [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) Windows SDK で説明されている Windows の機能は、このダイアログ ボックスの適切なフォントを使用します。  
  
 `MapDialogRect`メンバー関数は、ダイアログ ボックスの単位を置き換えます`lpRect`で画面の作成 ダイアログ ボックスをボックス内のコントロールの位置四角形を使用できるようにする単位 (ピクセル単位)。  
  
##  <a name="oninitdialog"></a>  Cpropertysheet::oninitdialog  
 プロパティ シートの初期化処理を拡張するためにオーバーライドします。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションが、プロパティ シート内のコントロールのいずれかに入力フォーカスを設定するかどうかを指定します。 場合**OnInitDialog** 0 以外を返します、Windows、入力フォーカスを設定、プロパティ シートの最初のコントロールです。 アプリケーションは、プロパティ シート内のコントロールのいずれかに入力のフォーカスを明示的に設定した場合にのみ、0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数への応答、 **WM_INITDIALOG**メッセージ。 中にプロパティ シートにこのメッセージは送信、[作成](#create)または[DoModal](#domodal)呼び出しで、プロパティ シートを表示する直前に発生します。  
  
 プロパティ シートが初期化されたときに、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、基底クラスを呼び出して最初`OnInitDialog`が、その戻り値を無視します。 通常戻ります**TRUE**オーバーライドされたメンバー関数から。  
  
 このメンバー関数用のメッセージ マップ エントリが不要です。  
  
##  <a name="pressbutton"></a>  CPropertySheet::PressButton  
 プロパティ シートで指定されたボタンの選択肢をシミュレートします。  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nButton`  
 nButton: ボタンを押すことを識別します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **PSBTN_BACK**戻る ボタンを選択します。  
  
- **PSBTN_NEXT** [次へ] ボタンを選択します。  
  
- **PSBTN_FINISH** [完了] を選択します。  
  
- **PSBTN_OK** [ok] ボタンを選択します。  
  
- **PSBTN_APPLYNOW**今すぐ適用 ボタンを選択します。  
  
- **PSBTN_CANCEL** [キャンセル] ボタンを選択します。  
  
- **PSBTN_HELP**ヘルプ ボタンを選択します。  
  
### <a name="remarks"></a>コメント  
 参照してください[PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) Windows SDK Pressbutton メッセージの詳細についてはします。  
  
 呼び出し`PressButton`は送信しません、 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)プロパティ ページからの通知フレームワークをします。 この通知を送信する呼び出し[送るに](../../mfc/reference/cpropertypage-class.md#onok)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>  CPropertySheet::RemovePage  
 プロパティ シートからページを削除し、関連付けられたウィンドウを破棄します。  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 プロパティ シートから削除するページへのポインター。 ことはできません`NULL`です。  
  
 `nPage`  
 削除するページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいとの間でなければなりません。  
  
### <a name="remarks"></a>コメント  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクト自体は、所有者のまで破棄されません、`CPropertySheet`ウィンドウが閉じられます。  
  
##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage  
 アクティブなページを変更します。  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPage`  
 設定するページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいかである必要がある必要があります。  
  
 `pPage`  
 プロパティ シートに設定するページへのポインター。 できません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常に有効な場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、使用して`SetActivePage`場合は、アクティブなページが別のページの原因には 1 つのページで、ユーザーのアクション。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetActivePage](#getactivepage)です。  
  
##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText  
 [完了] コマンド ボタンのテキストを設定します。  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 [完了] コマンド ボタンに表示されるテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetFinishText`完了コマンド ボタンのテキストを表示し、ユーザーがウィザードの最後のページでアクションが完了した後、[次へ] ボタンと戻るボタンを非表示にします。  
  
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
 `nStyle`  
 プロパティ シートのタイトルのスタイルを指定します。 0、またはスタイルを指定する必要があります**PSH_PROPTITLE**です。 として設定されているスタイル場合**PSH_PROPTITLE**、キャプションとして指定されたテキストの後に「プロパティ」という単語が表示されます。 たとえば、呼び出し`SetTitle`(「簡易」 **PSH_PROPTITLE**)「単純なプロパティです」のプロパティ シートのタイトルになります。  
  
 `lpszText`  
 プロパティ シートのタイトル バーのキャプションとして使用するテキストを指します。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ シートは、プロパティ シートのコンス トラクターでキャプション パラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons  
 有効またはウィザードのプロパティ シートに戻る、Next、または [完了] ボタンを無効にします。  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 関数と、ウィザードのボタンの外観をカスタマイズするフラグのセット。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- **PSWIZB_BACK** [戻る] ボタン  
  
- **PSWIZB_NEXT**次へ ボタン  
  
- **PSWIZB_FINISH** [完了] ボタン  
  
- **PSWIZB_DISABLEDFINISH**無効になっている [完了] ボタン  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetWizardButtons`ダイアログが開いています。 後でのみ呼び出すことができません`SetWizardButtons`を呼び出す前に[DoModal](#domodal)です。 通常、呼び出す必要は`SetWizardButtons`から[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)です。  
  
 [完了] ボタンのテキストを変更または、[次へ] を非表示にするし、戻るボタンに 1 回、ユーザーが、ウィザードでは、呼び出しを完了[SetFinishText](#setfinishtext)です。 完了 と 次への同じボタンを共有することに注意してください。 [完了] または [次へ] ボタンを同時に、両方ではなくを表示することができます。  
  
### <a name="example"></a>例  
 A`CPropertySheet`は 3 つのウィザードのプロパティ ページがあります: `CStylePage`、 `CColorPage`、および`CShapePage`です。  次のコード片は、有効および無効にする方法を示します、**戻る**と**次**ウィザードのプロパティ ページのボタンです。  
  
 [!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode  
 ウィザードとしてのプロパティ ページを設定します。  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>コメント  
 ウィザードのプロパティ ページの主な特性は、こと、ユーザーを使用して次に移動または [完了]、バックアップ、およびキャンセル ボタンのタブではなくです。  
  
 呼び出す`SetWizardMode`呼び出す前に[DoModal](#domodal)です。 呼び出した後`SetWizardMode`、`DoModal`いずれかを返す**ID_WIZFINISH** (場合、ユーザーが閉じると、[完了]) または**IDCANCEL**です。  
  
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



