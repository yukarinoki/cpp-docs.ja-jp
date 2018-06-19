---
title: CMFCToolBarsCustomizeDialog クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 7015e3be189bce8745777ef7353e1f2788a6f6be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378182"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog クラス
モードレス タブ ダイアログ ボックス ( [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)) を使用して、ツールバー、メニューのキーボード ショートカット、ユーザー定義のツールおよびアプリケーションで visual スタイルをカスタマイズします。 通常、このダイアログ ボックスを表示するには、 **[ツール]** メニューの **[ユーザー設定]** をクリックします。  
  
 **カスタマイズ** ダイアログ ボックスが 6 つのタブ:**コマンド**、**ツールバー**、**ツール**、**キーボード**、 **メニュー**、および**オプション**です。  
  
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
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|リソースと呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を追加するメニュー コマンドの一覧、**コマンド**ページ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|リソースと呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を追加するメニュー コマンドの一覧、**コマンド**ページ。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|リソースからツールバーを読み込みます。 その後、メニューの呼び出しで各コマンドについて、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧で、ボタンを挿入する方法、**コマンド**指定されたカテゴリ内のページです。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|表示、**カスタマイズ** ダイアログ ボックス。|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|将来使用するために予約されています。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|有効または無効を使用して新しいツールバーの作成、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|指定された設定`CListBox`オブジェクト内のコマンドを**すべてコマンド**カテゴリ。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|指定された設定`CComboBox`内の各コマンド カテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|指定された設定`CListBox`内の各コマンド カテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|指定されたコマンド ID に関連付けられている名前を取得します|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|ダイアログ ボックスの動作に影響するフラグのセットを取得します。|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|イメージ エディターを起動し、ユーザーがツール バー ボタンまたはメニュー項目のアイコンをカスタマイズできます。|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|プロパティ シートの初期化処理を拡張するためにオーバーライドします。 (上書き[cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog))。|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|ウィンドウが破棄された後に、フレームワークによって呼び出されます。 (`CPropertySheet::PostNcDestroy` をオーバーライドします)。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|指定したカテゴリまたはすべてのカテゴリから、指定されたコマンド ID を持つボタンを削除します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|カテゴリのリスト ボックス内にあるカテゴリの名前を変更、**コマンド**タブです。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|コマンドの一覧で、ボタンが置き換えられます、**コマンド**新規ツール バー ボタン オブジェクトを持つタブです。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|表示されるカテゴリの一覧にカテゴリを追加、**コマンド**タブです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|ユーザー定義のツールの一覧が有効かどうかを判断するためにフレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|ユーザー定義のツールのプロパティを変更するときに、フレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|指定されたキーボード ショートカットをアクションに割り当て可能かどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|ユーザー定義のツールを変更できるかどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|ユーザーが選択したときに、フレームワークによって呼び出されます、**ツール** タブを要求します。|  
  
## <a name="remarks"></a>コメント  
 表示する、**カスタマイズ** ダイアログ ボックスで、作成、`CMFCToolBarsCustomizeDialog`オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::Create](#create)メソッドです。  
  
 中に、**カスタマイズ** ダイアログ ボックスがアクティブな場合、アプリケーションのカスタマイズのタスクにユーザーを制限する特殊なモードで動作します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarsCustomizeDialog`クラスです。 例では、コマンドのリスト ボックスにツール バー ボタンを交換する方法を示しています、**コマンド** ページを使用して新しいツールバーの作成を有効にする、**カスタマイズ**ダイアログ ボックスと表示、 **カスタマイズ** ダイアログ ボックス。 このコード スニペットの一部である、 [IE デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>要件  
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
 [入力] `uiCategoryId`  
 ボタンを挿入するカテゴリの ID を指定します。  
  
 [入力] `button`  
 挿入するボタンを指定します。  
  
 [入力] `iInsertBefore`  
 ボタンを挿入する前にあるツールバーのボタンの 0 から始まるインデックスを指定します。  
  
 [入力] `lpszCategory`  
 ボタンを挿入するカテゴリ文字列を指定します。  
  
### <a name="remarks"></a>コメント  
 `AddButton`メソッド (ID_FILE_MRU_FILE1) などの標準コマンド Id を持つボタンは無視されます、コマンドは許可されていません (を参照してください[CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) のボタンのダミーとします。  
  
 このメソッドと同じ型の新しいオブジェクトを作成する`button`(通常、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)) ボタンのランタイム クラスを使用しています。 呼び出して[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)をボタンのデータ メンバーをコピーし、指定したカテゴリに、コピーを挿入します。  
  
 新しいボタンを挿入すると、受信、`OnAddToCustomizePage`通知します。  
  
 場合`iInsertBefore`-1 で、カテゴリの一覧に、ボタンが追加されます。 それ以外の場合、指定したインデックス項目の前に挿入されます。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`AddButton`のメソッド、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、[スライダー サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu  
 リソースと呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を追加するメニュー コマンドの一覧、**コマンド**ページ。  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuResId`  
 読み込むメニューのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メニューが正常に追加された場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 呼び出しで`AddMenuCommands`、`bPopup`は`FALSE`します。 その結果、そのメソッドでは、コマンドの一覧にサブメニューを含むメニュー項目は追加されません。 このメソッドは、コマンドの一覧に、サブメニューのメニュー項目を追加はします。  
  
##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands  
 コマンドの一覧に項目を追加、**コマンド**ページを指定されたメニューのすべての項目を表します。  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenu`  
 追加する CMenu オブジェクトへのポインター。  
  
 [入力] `bPopup`  
 コマンドの一覧に、ポップアップ メニュー項目を挿入するかどうかを指定します。  
  
 [入力] `lpszCategory`  
 メニューを挿入するカテゴリの名前。  
  
 [入力] `lpszMenuPath`  
 コマンドが表示されている場合、名前に追加されるプレフィックス、**すべてのカテゴリ** ボックスの一覧です。  
  
### <a name="remarks"></a>コメント  
 `AddMenuCommands`のすべてのメニュー項目をメソッドのループ`pMenu`です。 サブメニューを含まないメニュー項目ごとに、このメソッドを作成、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)ツールバーとメニュー項目を追加する方法コマンドの一覧にボタンを**コマンド**ページ。 区切り記号は、このプロセスで無視されます。  
  
 場合`bPopup`は`TRUE`、サブメニューを含むメニュー項目ごとに、このメソッドを作成、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトを呼び出すことによって、コマンドのリストに挿入`AddButton`です。 それ以外の場合を含むサブメニューのメニュー項目は、コマンドの一覧には表示されません。 どちらの場合と`AddMenuCommands`メニュー項目を検出したサブメニュー呼び出し自体としてサブメニューにポインターを渡す、再帰的に、`pMenu`パラメーターとサブメニューのラベルを追加`lpszMenuPath`です。  
  
##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar  
 リソースからツールバーを読み込みます。 その後、メニューの呼び出しで各コマンドについて、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧で、ボタンを挿入する方法、**コマンド**指定されたカテゴリ内のページです。  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCategoryId`  
 ツールバーを追加するカテゴリのリソース ID を指定します。  
  
 [入力] `uiToolbarResId`  
 コマンドの一覧に挿入するがコマンド、ツールバーのリソース ID を指定します。  
  
 [入力] `lpszCategory`  
 ツールバーを追加するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`AddToolBar`メソッドで、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>コメント  
 各コマンドを表すために使用するコントロールが、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト。 ツールバーを追加した後に置き換えることができます、ボタン、派生型のコントロールを呼び出して[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)です。  
  
##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 ユーザー ツールの一覧の有効性を確認します。  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lstTools`  
 確認するユーザー定義のツールの一覧。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`ユーザー定義のツールの一覧は、それ以外の有効な場合`FALSE`です。 既定の実装では、常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって返されるユーザー定義のツールを表すオブジェクトの有効性を確認するには、このメソッドを呼び出して[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)です。  
  
 上書き、`CheckToolsValidity`から派生したクラスのメソッド`CMFCToolBarsCustomizeDialog`ユーザーがダイアログ ボックスを閉じる前にユーザー ツールを検証するかどうか。 このメソッドが戻る場合`FALSE`、ユーザーがいずれかをクリックしたとき、**閉じる** ダイアログ ボックスまたはボタンの右上隅のボタン**閉じる** ダイアログ ボックスの右下隅で、ダイアログ ボックスが表示されます、**ツール**終了ではなくタブです。 このメソッドが戻る場合`FALSE`の外に移動するタブをクリックすると、**ツール** タブのナビゲーションは発生しません。 検証が失敗する原因となった問題をユーザーに通知を適切なメッセージ ボックスを表示する必要があります。  
  
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
 [入力] `pWndParentFrame`  
 親フレームへのポインター。 このパラメーターは `NULL` にすることはできません。  
  
 [入力] `bAutoSetFromMenus`  
 コマンドの一覧にすべてのメニューからメニュー コマンドを追加するかどうかを指定するブール値、**コマンド**ページ。 このパラメーターが場合`TRUE`、メニュー コマンドが追加されます。 それ以外の場合、メニュー コマンドは追加されません。  
  
 [入力] `uiFlags`  
 ダイアログ ボックスの動作に影響するフラグの組み合わせ。 このパラメーターには、次の値の 1 つ以上を指定できます。  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [入力] `plistCustomPages`  
 リストへのポインター`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `plistCustomPages`パラメーターの一覧を参照`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。 コンス トラクターを使用して、ダイアログ ボックスに複数のページを追加、 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject)メソッドです。 CustomPages のサンプルを複数のページを追加する例を参照してください、**カスタマイズ** ダイアログ ボックス。  
  
 渡すことができる値の詳細については、`uiFlags`パラメーターを参照してください[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)です。  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create  
 表示、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` カスタマイズのプロパティ シートが正常に作成された場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`Create`メソッド、クラスを完全に初期化した後にのみです。  
  
##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 有効または無効を使用して新しいツールバーの作成、**カスタマイズ** ダイアログ ボックス。  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` ユーザー定義のツールバーで; を有効にするには`FALSE`ツールバーを無効にします。  
  
### <a name="remarks"></a>コメント  
 場合`bEnable`は`TRUE`、**新規**、**の名前を変更**と**削除**にボタンが表示される、**ツールバー**ページ。  
  
 既定では、または`bEnable`は`FALSE`、これらのボタンは表示されず、ユーザーが新しいツールバーを定義することはできません。  
  
##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 指定された設定`CListBox`オブジェクト内のコマンドを**すべてコマンド**カテゴリ。  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndListOfCommands`  
 参照、`CListBox`を設定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 **すべてコマンド**カテゴリには、すべてのカテゴリのコマンドが含まれています。 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドが提供されているボタンに関連付けられているコマンドを追加、**すべてコマンド**のカテゴリ。  
  
 このメソッドが用意されている内容を消去`CListBox`コマンドで設定する前にオブジェクト、**すべてコマンド**カテゴリ。  
  
 `CMFCMousePropertyPage`クラスでは、このメソッドを使用して、ダブルクリック イベントのリスト ボックスに入力します。  
  
##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 指定された設定`CComboBox`内の各コマンド カテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndCategory`  
 参照、`CComboBox`を設定するオブジェクト。  
  
 [入力] `bAddEmpty`  
 コマンドがないコンボ ボックスにカテゴリを追加するかどうかを指定するブール値。 このパラメーターが場合`TRUE`、コンボ ボックスに空のカテゴリを追加します。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>コメント  
 同様に、このメソッドは、 [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)メソッドでこのメソッドが動作する点を除いて、`CComboBox`オブジェクト。  
  
 このメソッドの内容を消去していない、`CComboBox`値を設定する前にオブジェクト。 保証されます、**すべてコマンド**カテゴリは、コンボ ボックスの最終的な項目です。  
  
 使用して新しいコマンドのカテゴリを追加することができます、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドです。 使用して既存のカテゴリの名前を変更することができます、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッドです。  
  
 `CMFCToolBarsKeyboardPropertyPage`と`CMFCKeyMapDialog`クラスでは、このメソッドを使用して、キーボード マップを分類します。  
  
##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 指定された設定`CListBox`内の各コマンド カテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndCategory`  
 参照、`CListBox`を設定するオブジェクト。  
  
 [入力] `bAddEmpty`  
 コマンドがないリスト ボックスにカテゴリを追加するかどうかを指定するブール値。 このパラメーターは場合`TRUE`、リスト ボックスに空のカテゴリを追加します。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>コメント  
 同様に、このメソッドは、 [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)メソッドでこのメソッドが動作する点を除いて、`CListBox`オブジェクト。  
  
 このメソッドの内容を消去していない、`CListBox`値を設定する前にオブジェクト。 保証されます、**すべてコマンド**カテゴリは、リスト ボックス内の最後の項目。  
  
 使用して新しいコマンドのカテゴリを追加することができます、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドです。 使用して既存のカテゴリの名前を変更することができます、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッドです。  
  
 `CMFCToolBarsCommandsPropertyPage`クラスでは、このメソッドを使用して、各コマンドの分類に関連付けられているコマンドの一覧を表示します。  
  
##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName  
 指定されたコマンド ID に関連付けられている名前を取得します  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 取得するコマンドの ID。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID に関連付けられている名前または`NULL`コマンドが存在しない場合。  
  
##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory  
 指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszItemName`  
 一致するようにテキスト ラベル。  
  
 [入力] `lstCommands`  
 含むリストへの参照を`CMFCToolBarButton`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 指定した項目の数の一覧をテキスト ラベル equals`lpszItemName`です。  
  
### <a name="remarks"></a>コメント  
 指定されたオブジェクトの一覧内の各要素が型でなければなりません`CMFCToolBarButton`です。 このメソッドは比較`lpszItemName`で、 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)データ メンバーです。  
  
##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags  
 ダイアログ ボックスの動作に影響するフラグのセットを取得します。  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの動作に影響するフラグのセット。  
  
### <a name="remarks"></a>コメント  
 このメソッドの値を取得、`uiFlags`コンス トラクターに渡されるパラメーター。 戻り値には、次の値の 1 つ以上を指定できます。  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 メニューの影を指定することができます。  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 ツール バー ボタンのイメージの下にテキスト ラベルが表示されるかどうかを指定することができます。  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 メニューのアニメーションのスタイルを指定することができます。  
  
 `AFX_CUSTOMIZE_NOHELP`  
 カスタマイズ ダイアログ ボックスから、ヘルプ ボタンを削除します。  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 により、 `WS_EX_CONTEXTHELP` visual スタイル。  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 削除、**ツール**ページのカスタマイズ ダイアログ ボックスからです。 このフラグがアプリケーションで使用する場合は、有効では、`CUserToolsManager`クラスです。  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 ボタンのキャプション、アンパサンドを含めるには、( **&**) 文字です。  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 削除、**大きいアイコン**のカスタマイズ ダイアログ ボックスからオプション。  
  
 詳細については、 `WS_EX_CONTEXTHELP` visual スタイルを参照してください[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)です。  
  
##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 これが発生した後すぐには、ユーザー ツールの変更に応答します。  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pSelTool`  
 変更されているユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ユーザーがユーザー定義のツールのプロパティを変更すると、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 このメソッドから派生したクラスでオーバーライド`CMFCToolBarsCustomizeDialog`ユーザー ツールへの変更が発生した後の処理を実行します。  
  
##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey  
 ユーザーが定義には、キーボード ショートカットを検証します。  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pAccel`  
 として表現される提案されたキーの割り当てへのポインター、 [ACCEL](http://msdn.microsoft.com/library/windows/desktop/ms646340)構造体。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` キーを割り当てることができる場合、または`FALSE`場合は、キーを割り当てることができません。 既定の実装では、常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが新しいキーボード ショートカットを割り当てるか、またはユーザーとしてのキーボード ショートカットを検証するには、それを定義するときに、余分な処理を実行する派生クラスでこのメソッドをオーバーライドします。 ショートカットが割り当てられていることを防ぐために返す`FALSE`です。 またメッセージ ボックスを表示またはそれ以外の場合、キーボード ショートカットが拒否された理由のためのユーザーに通知する必要があります。  
  
##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 カスタムの処理、ユーザー ツールに変化したとき、ユーザーが変更を適用を実行します。  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pSelTool`  
 置換しようとするは、ユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義のツールのプロパティを変更しようと、このメソッドは、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 上書き、`OnBeforeChangeTool`から派生したクラスのメソッド`CMFCToolBarsCustomizeDialog`リソースを解放するなど、ユーザー ツールへの変更が発生する前に、処理を実行する場合を`pSelTool`を使用します。  
  
##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 イメージ エディターを起動し、ユーザーがツール バー ボタンまたはメニュー項目のアイコンをカスタマイズできます。  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウへのポインター。  
  
 [入力] `bitmap`  
 オブジェクトへの参照、ビットマップを編集することです。  
  
 [入力] `nBitsPerPixel`  
 ビットマップのピクセルあたりのビット単位の色の解像度。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 変更がコミットされている場合それ以外の場合`FALSE`です。 既定の実装は、ダイアログ ボックスを表示しを返します`TRUE`、ユーザーがクリックした場合**OK**、または`FALSE`、ユーザーがクリックした場合**キャンセル**または**閉じる**ボタンをクリックします。  
  
### <a name="remarks"></a>コメント  
 ユーザー イメージ エディターの実行時に、このメソッドは、フレームワークによって呼び出されます。 既定の実装で、表示[[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)] ダイアログ ボックス。 オーバーライド`OnEditToolbarMenuImage`カスタム イメージ エディターを使用して派生クラスでします。  
  
##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog  
 プロパティ シートの初期化処理を拡張するためにオーバーライドします。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出しの結果、 [cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)メソッドです。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張[cpropertysheet::oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)、表示することによって、**閉じる**ボタン、および移動することによって、ダイアログ ボックスが現在の画面サイズに収まることを確認して、**ヘルプ** ダイアログ ボックスの左下隅にボタンをクリックします。  
  
##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 フレームワークからの通知を処理する、**ツール**ページが初期化しようとしています。  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 この通知を処理する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy  
 ウィンドウが破棄された後に、フレームワークによって呼び出されます。  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張`CPropertySheet::PostNcDestroy`、以前のモードにアプリケーションを復元しています。  
  
 [CMFCToolBarsCustomizeDialog::Create](#create)メソッドは、カスタマイズのタスクにユーザーを制限する特殊なモードでアプリケーションを配置します。  
  
##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton  
 指定したカテゴリまたはすべてのカテゴリから、指定されたコマンド ID を持つボタンを削除します。  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCategoryId`  
 ボタンを削除するカテゴリの ID を指定します。  
  
 [入力] `uiCmdId`  
 ボタンのコマンド ID を指定します。  
  
 [入力] `lpszCategory`  
 ボタンを削除するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 削除のボタン、または指定したカテゴリで、指定されたコマンド ID が見つからなかった場合は-1 の 0 から始まるインデックス。 場合`uiCategoryId`-1 で、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドとセットの最初のオーバー ロードを呼び出すすべてのカテゴリから、ボタンを削除、 `uiCategoryId` -1 です。  
  
##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory  
 カテゴリのリスト ボックス内にあるカテゴリの名前を変更、**コマンド**ページ。  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCategoryOld`  
 変更するカテゴリ名。  
  
 [入力] `lpszCategoryNew`  
 新しいカテゴリ名。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 カテゴリ名は一意である必要があります。  
  
##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton  
 コマンドのリスト ボックスにツール バー ボタンを置き換える、**コマンド**ページ。  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 置き換えられる ボタンのコマンドを指定します。  
  
 [入力] `button`  
 A`const`古い ボタンの代わりをツール バー ボタンのオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 ときに[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)、 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)、または[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)を追加します。コマンドを**コマンド**ページで、コマンドがの形式である、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト (または[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)メニュー オブジェクトによって追加されるサブメニューを含む項目`AddMenuCommands`)。 フレームワークでは、これらのコマンドを自動的に追加する 3 つのメソッドも呼び出します。 代わりに、派生型で表現するためのコマンドを実行する場合に、呼び出す`ReplaceButton`を渡して、派生型のボタンをクリックします。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`ReplaceButton`メソッドで、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory  
 カテゴリの一覧でカテゴリを指定します、**コマンド**ページは、ユーザーのカテゴリ。 呼び出す前に、この関数を呼び出す必要があります[CMFCToolBarsCustomizeDialog::Create](#create)です。  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCategory`  
 カテゴリの名前。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 現在、ユーザーのカテゴリの設定は、フレームワークによって使用されていません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)
