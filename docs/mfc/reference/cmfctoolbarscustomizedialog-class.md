---
title: CMFCToolBarsCustomizeDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c12b23c2250f2b0d26b053410c864c8cf435469
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852875"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog クラス
モードレス タブ ダイアログ ボックス ( [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)) ユーザーがツールバー、メニューのキーボード ショートカット、ユーザー定義のツール、およびアプリケーションでの visual スタイルをカスタマイズできるようにします。 通常、このダイアログ ボックスを表示するには、 **[ツール]** メニューの **[ユーザー設定]** をクリックします。  
  
 **カスタマイズ**ダイアログ ボックスには 6 つのタブ:**コマンド**、**ツールバー**、**ツール**、**キーボード**、 **メニュー**、および**オプション**します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|`CMFCToolBarsCustomizeDialog` オブジェクトを構築します。|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|コマンドの一覧にツール バー ボタンを挿入、**コマンド**ページ|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|リソースの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)でコマンドの一覧にそのメニューを追加する、**コマンド**ページ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|リソースの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)でコマンドの一覧にそのメニューを追加する、**コマンド**ページ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|リソースからツールバーを読み込みます。 次に、各コマンド メニューの呼び出しで、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧で、ボタンを挿入する方法、**コマンド**指定したカテゴリのページ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|表示、**カスタマイズ** ダイアログ ボックス。|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|将来使用するために予約されています。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|有効またはを使用して新しいツールバーの作成を無効に、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|設定`CListBox`コマンドでは、オブジェクト、**すべてコマンド**カテゴリ。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|設定`CComboBox`で各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|設定`CListBox`で各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|指定されたコマンド ID に関連付けられている名前を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|ダイアログ ボックスの動作に影響するフラグのセットを取得します。|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|イメージ エディターを起動し、ユーザーがツール バー ボタンまたはメニュー項目のアイコンをカスタマイズできます。|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|プロパティ シートの初期化処理を強化するよりも優先されます。 (上書き[cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog))。|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|ウィンドウが破棄された後に、フレームワークによって呼び出されます。 (`CPropertySheet::PostNcDestroy` をオーバーライドします)。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|指定したカテゴリまたはすべてのカテゴリから、指定したコマンド ID を持つボタンを削除します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|カテゴリのリスト ボックス内にあるカテゴリの名前を変更、**コマンド**タブ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|上のコマンドの一覧で ボタンの代わり、**コマンド**新しいツール バー ボタン オブジェクトを持つタブ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|表示されるカテゴリの一覧にカテゴリを追加、**コマンド**タブ。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|ユーザー定義のツールの一覧が有効かどうかを判断するためにフレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|ユーザー定義のツールのプロパティを変更するときに、フレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|アクションに指定されたキーボード ショートカットを割り当てることがあるかどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|ユーザー定義のツールを変更できるかどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|ユーザーが選択したときに、フレームワークによって呼び出されます、**ツール** タブを要求します。|  
  
## <a name="remarks"></a>Remarks  
 表示する、**カスタマイズ** ダイアログ ボックスで、作成、`CMFCToolBarsCustomizeDialog`オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::Create](#create)メソッド。  
  
 中に、**カスタマイズ** ダイアログ ボックスがアクティブで、アプリケーションのカスタマイズのタスクにユーザーを制限する特殊なモードで動作します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarsCustomizeDialog`クラス。 例では、コマンドのリスト ボックスにツール バー ボタンを交換する方法を示しています、**コマンド** ページを使用して新しいツールバーの作成を有効にする、**カスタマイズ** ダイアログ ボックスで、表示、 **カスタマイズ** ダイアログ ボックス。 このコード スニペットの一部、 [IE デモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>  CMFCToolBarsCustomizeDialog::AddButton  
 コマンドの一覧にツール バー ボタンを挿入、**コマンド**ページ。  
  
```  
void AddButton(
    UINT uiCategoryId,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCategoryId*  
 ボタンを挿入するカテゴリの ID を指定します。  
  
 [in]*ボタン*  
 挿入するボタンを指定します。  
  
 [in]*iInsertBefore*  
 ボタンの挿入前にあるツール バー ボタンの 0 から始まるインデックスを指定します。  
  
 [in]*lpszCategory*  
 ボタンを挿入するカテゴリ文字列を指定します。  
  
### <a name="remarks"></a>Remarks  
 `AddButton`メソッド (ID_FILE_MRU_FILE1) などの標準コマンド Id を持つボタンは無視されます、コマンドは許可されていません (を参照してください[CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) ボタンをダミーとします。  
  
 このメソッドと同じ型の新しいオブジェクトを作成します`button`(通常、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)) ボタンのランタイム クラスを使用しています。 呼び出して[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)ボタンのデータ メンバーのコピーを指定したカテゴリに、コピーを挿入します。  
  
 新しいボタンが挿入されると、受信、`OnAddToCustomizePage`通知します。  
  
 場合`iInsertBefore`-1 で、カテゴリの一覧に、ボタンが追加されます。 それ以外の場合、指定したインデックス項目の前に挿入されます。  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`AddButton`のメソッド、`CMFCToolBarsCustomizeDialog`クラス。 このコード スニペットの一部、[スライダー サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu  
 リソースの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)でコマンドの一覧にそのメニューを追加する、**コマンド**ページ。  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiMenuResId*  
 読み込むメニューのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 メニューが正常に追加された場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 呼び出しで`AddMenuCommands`、 *bPopup*は FALSE です。 その結果、そのメソッドでは、コマンドの一覧にサブメニューが含まれているメニュー項目は追加されません。 このメソッドは、コマンドの一覧に、サブメニューのメニュー項目を追加は。  
  
##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands  
 コマンドの一覧に項目を追加、**コマンド**ページを指定したメニュー内のすべての項目を表します。  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMenu*  
 追加する CMenu オブジェクトへのポインター。  
  
 [in]*bPopup*  
 コマンドの一覧に、ポップアップ メニュー項目を挿入するかどうかを指定します。  
  
 [in]*lpszCategory*  
 メニューを挿入するカテゴリの名前。  
  
 [in]*lpszMenuPath*  
 コマンドが表示されるときに、名前に追加するプレフィックス、**すべてのカテゴリ**一覧。  
  
### <a name="remarks"></a>Remarks  
 `AddMenuCommands`メソッドのすべてのメニュー項目をループ*pMenu*します。 サブメニューを含まないメニュー項目ごとに、このメソッドを作成、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)ツールバーとメニュー項目を追加する方法コマンドの一覧にボタンを**コマンド**ページ。 このプロセスでは、区切り記号は無視されます。  
  
 場合*bPopup*が true の場合、このメソッドを作成、サブメニューを含むメニュー項目ごとに、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトし、呼び出すことによって、コマンドのリストに挿入します`AddButton`。 それ以外の場合を含むサブメニューのメニュー項目は、コマンドの一覧には表示されません。 どちらの場合と`AddMenuCommands`メニュー項目を検出するとサブメニュー呼び出し自体のポインターとしてサブメニューを渡して再帰的に、 *pMenu*パラメーターとサブメニューのラベルを追加*lpszMenuPath*.  
  
##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar  
 リソースからツールバーを読み込みます。 次に、各コマンド メニューの呼び出しで、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧で、ボタンを挿入する方法、**コマンド**指定したカテゴリのページ。  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCategoryId*  
 ツールバーを追加するカテゴリのリソース ID を指定します。  
  
 [in]*uiToolbarResId*  
 そのコマンドがコマンドの一覧に挿入されたツールバーのリソース ID を指定します。  
  
 [in]*lpszCategory*  
 ツールバーを追加するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`AddToolBar`メソッドで、`CMFCToolBarsCustomizeDialog`クラス。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>Remarks  
 各コマンドを表すために使用するコントロールが、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト。 ツールバーを追加した後、派生型のコントロールでのボタンを置き換えますを呼び出して[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)します。  
  
##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 ユーザー ツールの一覧の有効性を確認します。  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lstTools*  
 確認するユーザー定義のツールの一覧。  
  
### <a name="return-value"></a>戻り値  
 ユーザー定義のツールの一覧が有効なかどうかは TRUE を返しますそれ以外の場合は FALSE です。 既定の実装を常に TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 フレームワークによって返されるユーザー定義のツールを表すオブジェクトの有効性を確認するには、このメソッドを呼び出して[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)します。  
  
 上書き、`CheckToolsValidity`から派生したクラスのメソッドで`CMFCToolBarsCustomizeDialog`にユーザーがダイアログ ボックスを閉じる前に、ユーザー ツールを検証したいかどうか。 いずれかをクリックすると、このメソッドは FALSE を返した場合、**閉じる** ダイアログ ボックスまたはボタンの右上隅にあるボタン**閉じる** ダイアログ ボックス、ダイアログ ボックスの右上隅にあります。表示、**ツール**終了ではなくタブです。 ユーザーから移動しようとするタブをクリックしたときに、このメソッドは FALSE を返した場合、**ツール**] タブの [ナビゲーションは発生しません。 検証が失敗する原因となった問題をユーザーに通知する適切なメッセージ ボックスを表示する必要があります。  
  
##  <a name="cmfctoolbarscustomizedialog"></a>  CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 `CMFCToolBarsCustomizeDialog` オブジェクトを構築します。  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParentFrame*  
 親フレームへのポインター。 このパラメーターには、NULL は指定できません。  
  
 [in]*bAutoSetFromMenus*  
 すべてのメニューからメニュー コマンドをコマンドの一覧に追加するかどうかを指定するブール値、**コマンド**ページ。 このパラメーターが TRUE の場合は、メニュー コマンドが追加されます。 それ以外の場合、メニュー コマンドは追加されません。  
  
 [in]*uiFlags*  
 ダイアログ ボックスの動作に影響するフラグの組み合わせ。 このパラメーターには、次の値の 1 つ以上を指定できます。  
  
- AFX_CUSTOMIZE_MENU_SHADOWS  
  
- AFX_CUSTOMIZE_TEXT_LABELS  
  
- AFX_CUSTOMIZE_MENU_ANIMATIONS  
  
- AFX_CUSTOMIZE_NOHELP  
  
- AFX_CUSTOMIZE_CONTEXT_HELP  
  
- AFX_CUSTOMIZE_NOTOOLS  
  
- AFX_CUSTOMIZE_MENUAMPERS  
  
- AFX_CUSTOMIZE_NO_LARGE_ICONS  
  
 [in]*plistCustomPages*  
 一覧へのポインター`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 *PlistCustomPages*パラメーターの一覧を指す`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。 コンス トラクターの ダイアログ ボックスを使用してより多くのページを追加する、 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject)メソッド。 CustomPages のサンプルをより多くのページを追加する例を参照してください、**カスタマイズ** ダイアログ ボックス。  
  
 渡すことができる値の詳細については、 *uiFlags*パラメーターを参照してください[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)します。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCToolBarsCustomizeDialog`クラス。 このコード スニペットの一部、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create  
 表示、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>戻り値  
 カスタマイズのプロパティ シートが正常に作成された場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 呼び出す、`Create`メソッド、クラスを完全に初期化した後でのみです。  
  
##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 有効またはを使用して新しいツールバーの作成を無効に、**カスタマイズ** ダイアログ ボックス。  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 ユーザー定義のツールバーを有効にする場合は TRUEツールバーを無効にする場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 場合*bEnable* true で、**新規**、**の名前を変更**と**削除**でボタンが表示されます、**ツールバー**ページです。  
  
 既定では、場合*bEnable* false、これらのボタンは表示されず、ユーザーが新しいツールバーを定義できません。  
  
##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 設定`CListBox`コマンドでは、オブジェクト、**すべてコマンド**カテゴリ。  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndListOfCommands`  
 参照、`CListBox`を設定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 **すべてコマンド**カテゴリには、すべてのカテゴリのコマンドが含まれています。 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドに指定されたボタンに関連付けられているコマンドの追加、**のすべてのコマンド**のカテゴリ。  
  
 このメソッドが用意されている内容を消去`CListBox`オブジェクト内のコマンドを追加する前に、**すべてコマンド**カテゴリ。  
  
 `CMFCMousePropertyPage`クラスでは、このメソッドを使用して、ダブルクリック イベントのリスト ボックスに入力します。  
  
##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 設定`CComboBox`で各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*wndCategory*  
 参照、`CComboBox`を設定するオブジェクト。  
  
 [in]*bAddEmpty*  
 コマンドがないコンボ ボックスにカテゴリを追加するかどうかを示すブール値。 このパラメーターがある場合は TRUE、空のカテゴリは、コンボ ボックスに追加されます。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは似ています、 [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)メソッドでこのメソッドが機能する点を除いて、`CComboBox`オブジェクト。  
  
 このメソッドの内容をクリアしません、`CComboBox`値を設定する前にオブジェクト。 保証されます、**すべてコマンド**カテゴリは、コンボ ボックス内の最後の項目。  
  
 使用して新しいコマンドのカテゴリを追加することができます、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッド。 使用して既存のカテゴリの名前を変更することができます、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッド。  
  
 `CMFCToolBarsKeyboardPropertyPage`と`CMFCKeyMapDialog`クラスでは、このメソッドを使用して、キーボード マップを分類します。  
  
##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 設定`CListBox`で各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*wndCategory*  
 参照、`CListBox`を設定するオブジェクト。  
  
 [in]*bAddEmpty*  
 コマンドがないリスト ボックスにカテゴリを追加するかどうかを示すブール値。 このパラメーターがある場合は TRUE、空のカテゴリは、リスト ボックスに追加されます。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは似ています、 [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)メソッドでこのメソッドが機能する点を除いて、`CListBox`オブジェクト。  
  
 このメソッドの内容をクリアしません、`CListBox`値を設定する前にオブジェクト。 保証されます、**すべてコマンド**カテゴリは、リスト ボックス内の最後の項目。  
  
 使用して新しいコマンドのカテゴリを追加することができます、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッド。 使用して既存のカテゴリの名前を変更することができます、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッド。  
  
 `CMFCToolBarsCommandsPropertyPage`クラスでは、このメソッドを使用して、各コマンドのカテゴリに関連付けられているコマンドの一覧を表示します。  
  
##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName  
 指定されたコマンド ID に関連付けられている名前を取得します。  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 取得するコマンドの ID。  
  
### <a name="return-value"></a>戻り値  
 コマンドが存在しない場合に、指定したコマンド ID、または NULL に関連付けられている名前です。  
  
##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory  
 指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszItemName*  
 一致するようにテキスト ラベル。  
  
 [in]*lstCommands*  
 含むリストへの参照を`CMFCToolBarButton`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 指定した項目の数の一覧をテキスト ラベル equals *lpszItemName*します。  
  
### <a name="remarks"></a>Remarks  
 指定されたオブジェクトの一覧内の各要素は型でなければなりません`CMFCToolBarButton`します。 このメソッドは比較*lpszItemName*で、 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)データ メンバー。  
  
##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags  
 ダイアログ ボックスの動作に影響するフラグのセットを取得します。  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの動作に影響するフラグのセット。  
  
### <a name="remarks"></a>Remarks  
 このメソッドの値を取得、 *uiFlags*コンス トラクターに渡されるパラメーター。 戻り値には、次の値の 1 つ以上を指定できます。  
  
 AFX_CUSTOMIZE_MENU_SHADOWS  
 メニューの シャドウ表示形式を指定できます。  
  
 AFX_CUSTOMIZE_TEXT_LABELS  
 ツール バー ボタンのイメージの下にあるテキスト ラベルが表示されるかどうかを指定できます。  
  
 AFX_CUSTOMIZE_MENU_ANIMATIONS  
 メニューのアニメーションのスタイルを指定できます。  
  
 AFX_CUSTOMIZE_NOHELP  
 カスタマイズ ダイアログ ボックスから [ヘルプ] ボタンを削除します。  
  
 AFX_CUSTOMIZE_CONTEXT_HELP  
 WS_EX_CONTEXTHELP visual スタイルを有効にします。  
  
 AFX_CUSTOMIZE_NOTOOLS  
 削除、**ツール**、[カスタマイズ] ダイアログ ボックスからのページ。 このフラグがアプリケーションで使用する場合は、有効では、`CUserToolsManager`クラス。  
  
 AFX_CUSTOMIZE_MENUAMPERS  
 ボタンのキャプションに、アンパサンドを含めることができます ( **&**) 文字。  
  
 AFX_CUSTOMIZE_NO_LARGE_ICONS  
 削除、**大きいアイコン**カスタマイズ ダイアログ ボックスからオプション。  
  
 WS_EX_CONTEXTHELP visual スタイルの詳細については、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)します。  
  
##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 発生後すぐには、ユーザー ツールでの変更に応答します。  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力]*pSelTool*  
 変更されているユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 ユーザー定義のツールのプロパティを変更するとき、このメソッドは、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 このメソッドから派生したクラスでオーバーライド`CMFCToolBarsCustomizeDialog`ユーザー ツールの変更が発生した後、処理を実行します。  
  
##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey  
 ユーザーが定義には、キーボード ショートカットを検証します。  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力]*pAccel*  
 として表される候補キーの割り当てへのポインター、[アクセル](http://msdn.microsoft.com/library/windows/desktop/ms646340)構造体。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は、キーを割り当てることができない場合に、キーが割り当てられている、または FALSE を指定できます。 既定の実装を常に TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが新しいショートカット キー、またはユーザーとしてのキーボード ショートカットを検証するには、それを定義するときに、余分な処理を実行する派生クラスでこのメソッドをオーバーライドします。 ショートカットが割り当てられていることを防ぐために FALSE が返されます。 またメッセージ ボックスを表示または、キーボード ショートカットが拒否された理由のためのユーザーに通知する必要があります。  
  
##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 カスタムの処理を実行ユーザー ツールに変更されたときに、ユーザーが変更を適用しようとします。  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力]*pSelTool*  
 置き換えられますユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 ユーザー定義のツールのプロパティを変更する場合、このメソッドは、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 上書き、`OnBeforeChangeTool`から派生したクラスのメソッドで`CMFCToolBarsCustomizeDialog`リソースを解放するなど、ユーザー ツールの変更が発生する前に、処理を実行する場合を*pSelTool*を使用します。  
  
##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 イメージ エディターを起動し、ユーザーがツール バー ボタンまたはメニュー項目のアイコンをカスタマイズできます。  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 親ウィンドウへのポインター。  
  
 [in]*ビットマップ*  
 編集するビットマップ オブジェクトへの参照。  
  
 [in]*nBitsPerPixel*  
 ビットマップのビット/ピクセルの色の解像度。  
  
### <a name="return-value"></a>戻り値  
 変更がコミットされている場合は TRUE。それ以外の場合は FALSE です。 既定の実装がダイアログ ボックスを表示し、ユーザーがクリックした場合は TRUE を返します**OK**、または、ユーザーがクリックした場合は FALSE**キャンセル**または**閉じる**ボタン。  
  
### <a name="remarks"></a>Remarks  
 ユーザー イメージ エディターの実行時に、このメソッドは、フレームワークによって呼び出されます。 既定の実装が表示されます[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md) ダイアログ ボックス。 オーバーライド`OnEditToolbarMenuImage`カスタム イメージ エディターを使用して派生クラスでします。  
  
##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog  
 プロパティ シートの初期化処理を強化するよりも優先されます。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出しの結果、 [cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)メソッド。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装によって拡張[cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)、表示することによって、**閉じる**ボタン、ダイアログ ボックスが現在の画面サイズに収まることを確認することで、移動することによって、**ヘルプ** ダイアログ ボックスの左下隅にボタンをクリックします。  
  
##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Framework から通知を処理する、**ツール**ページが初期化されます。  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、何も行われません。 この通知を処理するための派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy  
 ウィンドウが破棄された後に、フレームワークによって呼び出されます。  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装によって拡張`CPropertySheet::PostNcDestroy`、前のモードにアプリケーションを復元することで。  
  
 [CMFCToolBarsCustomizeDialog::Create](#create)メソッドは、カスタマイズのタスクにユーザーを制限する特殊なモードでアプリケーションを配置します。  
  
##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton  
 指定したカテゴリまたはすべてのカテゴリから、指定したコマンド ID を持つボタンを削除します。  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCategoryId*  
 ボタンを削除するカテゴリの ID を指定します。  
  
 [in]*uiCmdId*  
 ボタンのコマンド ID を指定します。  
  
 [in]*lpszCategory*  
 ボタンを削除するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 削除ボタン、または指定したコマンド ID が指定したカテゴリで見つからなかった場合は-1 の 0 から始まるインデックス。 場合*uiCategoryId* -1 で、戻り値は 0。  
  
### <a name="remarks"></a>Remarks  
 ボタンすべてのカテゴリからを削除するには、このメソッドとセットの最初のオーバー ロードを呼び出す*uiCategoryId*を-1 にします。  
  
##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory  
 カテゴリのリスト ボックス内にあるカテゴリの名前を変更、**コマンド**ページ。  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszCategoryOld*  
 変更するカテゴリ名。  
  
 [in]*lpszCategoryNew*  
 新しいカテゴリの名前。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 カテゴリ名は一意である必要があります。  
  
##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton  
 コマンドのリスト ボックスにツール バー ボタンが置き換えられます、**コマンド**ページ。  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 置き換えられる ボタンのコマンドを指定します。  
  
 [in]*ボタン*  
 A **const**古い ボタンの代わりをツール バー ボタン オブジェクトへの参照。  
  
### <a name="remarks"></a>Remarks  
 ときに[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)、 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)、または[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)を追加します。コマンドを**コマンド**] ページの [コマンドの形式である、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト (または[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)メニュー オブジェクトによって追加されたサブメニューを含む項目`AddMenuCommands`)。 フレームワークでは、これら 3 つのコマンドを自動的に追加するメソッドも呼び出します。 代わりに派生型で表されるコマンドを実行する場合に、呼び出す`ReplaceButton`を派生型のボタンを渡します。  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`ReplaceButton`メソッドで、`CMFCToolBarsCustomizeDialog`クラス。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory  
 カテゴリの一覧でカテゴリを指定します、**コマンド**ページは、ユーザーのカテゴリ。 呼び出す前に、この関数を呼び出す必要があります[CMFCToolBarsCustomizeDialog::Create](#create)します。  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszCategory*  
 カテゴリの名前。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 現在、ユーザーのカテゴリの設定は、フレームワークによって使用されていません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)
