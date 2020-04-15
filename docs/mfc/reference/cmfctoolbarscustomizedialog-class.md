---
title: クラスをカスタマイズします。
ms.date: 11/04/2016
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
ms.openlocfilehash: d47ecf45a7bbfc563be0c05cd15ee84d430f502f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377360"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>クラスをカスタマイズします。

ユーザーがアプリケーションのツールバー、メニュー、キーボード ショートカット、ユーザー定義ツール、およびビジュアル スタイルをカスタマイズできるようにするモードレス タブ ダイアログ ボックス ( [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)) 。 通常、このダイアログ ボックスを表示するには、 **[ツール]** メニューの **[ユーザー設定]** をクリックします。

**[ユーザー設定]** ダイアログ ボックスには、**コマンド**、**ツール バー**、**ツール**、**キーボード**、**メニュー**、およびオプションの 6 つのタブ**があります**。

## <a name="syntax"></a>構文

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックスをカスタマイズします。](#cmfctoolbarscustomizedialog)|`CMFCToolBarsCustomizeDialog` オブジェクトを構築します。|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックスをカスタマイズします。](#addbutton)|**[コマンド**] ページのコマンドの一覧にツール バー ボタンを挿入します。|
|[ダイアログボックスをカスタマイズします。](#addmenu)|リソースからメニューを読み込み[、CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を呼び出して、そのメニューを **[コマンド**] ページのコマンドの一覧に追加します。|
|[ダイアログボックスをカスタマイズします。](#addmenucommands)|リソースからメニューを読み込み[、CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を呼び出して、そのメニューを **[コマンド**] ページのコマンドの一覧に追加します。|
|[ダイアログボックスをカスタマイズします。](#addtoolbar)|リソースからツール バーを読み込みます。 次に、メニューの各コマンドに対して[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドを呼び出して、指定したカテゴリの下の **[コマンド**] ページのコマンドの一覧にボタンを挿入します。|
|[ダイアログボックスをカスタマイズする::作成](#create)|**[カスタマイズ**] ダイアログ ボックスを表示します。|
|`CMFCToolBarsCustomizeDialog::EnableTools`|将来利用するために予約されています。|
|[ダイアログ ボックスを表示します。](#enableuserdefinedtoolbars)|[**ユーザー設定**] ダイアログ ボックスを使用して、新しいツールバーの作成を有効または無効にします。|
|[ダイアログボックスをカスタマイズします。](#fillallcommandslist)|指定した`CListBox`オブジェクトに **[すべてのコマンド]** カテゴリのコマンドを設定します。|
|[ダイアログボックスをカスタマイズします。](#fillcategoriescombobox)|指定した`CComboBox`オブジェクトに、[**カスタマイズ**] ダイアログ ボックスの各コマンド カテゴリの名前を設定します。|
|[ダイアログ ボックスをカスタマイズします。](#fillcategorieslistbox)|指定した`CListBox`オブジェクトに、[**カスタマイズ**] ダイアログ ボックスの各コマンド カテゴリの名前を設定します。|
|[ダイアログボックスをカスタマイズします。](#getcommandname)|指定されたコマンド ID に関連付けられている名前を取得します。|
|[ダイアログボックスをカスタマイズします。](#getcountincategory)|指定されたテキスト ラベルを持つ、指定されたリスト内の項目数を取得します。|
|[ダイアログボックスをカスタマイズします。](#getflags)|ダイアログ ボックスの動作に影響を与えるフラグのセットを取得します。|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ダイアログボックスをカスタマイズします。](#onedittoolbarmenuimage)|ユーザーがツール バー ボタンまたはメニュー項目アイコンをカスタマイズできるように、イメージ エディターを起動します。|
|[ダイアログをカスタマイズします。](#oninitdialog)|プロパティ シートの初期化を強化するためにオーバーライドします。 (C プロパティ シートをオーバーライドします[。::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[ダイアログ:PostNcをカスタマイズする](#postncdestroy)|ウィンドウが破棄された後に、フレームワークによって呼び出されます。 ( `CPropertySheet::PostNcDestroy`をオーバーライドします)。|
|[ダイアログボックスをカスタマイズします。](#removebutton)|指定したコマンド ID を持つボタンを、指定したカテゴリまたはすべてのカテゴリから削除します。|
|[ダイアログボックスをカスタマイズします。](#renamecategory)|[**コマンド**] タブのカテゴリのリスト ボックス内のカテゴリの名前を変更します。|
|[ダイアログボックスをカスタマイズします。](#replacebutton)|[**コマンド**] タブのコマンド一覧のボタンを、新しいツール バー ボタン オブジェクトに置き換えます。|
|[ダイアログボックスをカスタマイズします。](#setusercategory)|[**コマンド**] タブに表示されるカテゴリの一覧にカテゴリを追加します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックスをカスタマイズする::チェックツール妥当性](#checktoolsvalidity)|ユーザー定義ツールの一覧が有効かどうかを判断するために、フレームワークによって呼び出されます。|
|[ダイアログボックスをカスタマイズします。](#onafterchangetool)|ユーザー定義ツールのプロパティが変更されたときに、フレームワークによって呼び出されます。|
|[ダイアログボックスをカスタマイズします。](#onassignkey)|指定したキーボード ショートカットをアクションに割り当てることができるかどうかを判断します。|
|[ダイアログボックスをカスタマイズします。](#onbeforechangetool)|ユーザー定義ツールを変更できるかどうかを決定します。|
|[ダイアログボックスをカスタマイズする::オンイニトツールページ](#oninittoolspage)|ユーザーが **[ツール**] タブを選択したときに、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

[**カスタマイズ**] ダイアログ ボックスを表示`CMFCToolBarsCustomizeDialog`するには、オブジェクトを作成し[、CMFCToolBarsCustomizeDialog::Create](#create)メソッドを呼び出します。

[**カスタマイズ]** ダイアログ ボックスがアクティブな間は、アプリケーションはユーザーをカスタマイズタスクに制限する特別なモードで動作します。

## <a name="example"></a>例

`CMFCToolBarsCustomizeDialog` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、[**コマンド]** ページのコマンドのリスト ボックスにあるツール バー ボタンを置き換える方法、**ユーザー設定**] ダイアログ ボックスを使用して新しいツールバーを作成する方法、および **[カスタマイズ**] ダイアログ ボックスを表示する方法を示します。 このコード スニペットは、 [IE デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxToolBars カスタマイズダイアログ.h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>ダイアログボックスをカスタマイズします。

[**コマンド**] ページのコマンドの一覧にツール バー ボタンを挿入します。

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

*uiカテゴリId*<br/>
[in]ボタンを挿入するカテゴリ ID を指定します。

*ボタン*<br/>
[in]挿入するボタンを指定します。

*前に挿入します。*<br/>
[in]ボタンが挿入される前に、ツール バー ボタンの 0 から始まるインデックスを指定します。

*カテゴリ*<br/>
[in]ボタンを挿入するカテゴリ文字列を指定します。

### <a name="remarks"></a>解説

この`AddButton`メソッドは、標準のコマンド ID (ID_FILE_MRU_FILE1 など)、許可されていないコマンド[(CMFCToolBar::IsCommand許可](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)を参照) およびダミー ボタンを持つボタンを無視します。

このメソッドは、ボタンのランタイム クラスを使用`button`して、同じ型の新しいオブジェクトを作成します ( 通常[は CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)) 。 次に[、CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)を呼び出してボタンのデータ メンバーをコピーし、指定したカテゴリにコピーを挿入します。

新しいボタンが挿入されると、通知を`OnAddToCustomizePage`受け取ります。

1`iInsertBefore`の場合、ボタンはカテゴリのリストに追加されます。それ以外の場合は、指定されたインデックスを持つ項目の前に挿入されます。

### <a name="example"></a>例

クラスのメソッドの使用方法を`AddButton`次の例に示します`CMFCToolBarsCustomizeDialog`。 このコード スニペットは[、スライダーサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>ダイアログボックスをカスタマイズします。

リソースからメニューを読み込み[、CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)を呼び出して、そのメニューを **[コマンド**] ページのコマンドの一覧に追加します。

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]読み込むメニューのリソース ID を指定します。

### <a name="return-value"></a>戻り値

メニューが正常に追加された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

への`AddMenuCommands`呼び出しでは *、bPopup*は FALSE です。 その結果、このメソッドは、サブメニューを含むメニュー項目をコマンドのリストに追加しません。 このメソッドは、サブメニューのメニュー項目をコマンドの一覧に追加します。

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>ダイアログボックスをカスタマイズします。

指定したメニューのすべての項目を表す**コマンド**ページのコマンドの一覧に項目を追加します。

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
[in]追加する CMenu オブジェクトへのポインター。

*bPopup*<br/>
[in]コマンドの一覧にポップアップ メニュー項目を挿入するかどうかを指定します。

*カテゴリ*<br/>
[in]メニューを挿入するカテゴリの名前を指定します。

*メニューパス*<br/>
[in][**すべてのカテゴリ**] リストにコマンドが表示されたときに、名前に追加されるプレフィックス。

### <a name="remarks"></a>解説

この`AddMenuCommands`メソッドは*pMenu*のすべてのメニュー項目をループします。 サブメニューを含まない各メニュー項目に対して、このメソッドは[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトを作成し[、CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドを呼び出して、メニュー項目をツール バー ボタンとして **[コマンド**] ページのコマンドの一覧に追加します。 このプロセスでは、区切り記号は無視されます。

*bPopup*が TRUE の場合、サブメニューを含む各メニュー項目に対して、このメソッドは[CMFCToolBarMenuButton クラス クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)を作成`AddButton`し、それを呼び出すことによってコマンドのリストに挿入します。 それ以外の場合は、サブメニューを含むメニュー項目は、コマンドの一覧に表示されません。 どちらの場合も、サブ`AddMenuCommands`メニューを持つメニュー項目が検出されると、再帰的に呼び出され、サブメニューへのポインターを*pMenu*パラメーターとして渡し、サブメニューのラベルを*lpszMenuPath*に追加します。

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>ダイアログボックスをカスタマイズします。

リソースからツール バーを読み込みます。 次に、メニューの各コマンドに対して[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドを呼び出して、指定したカテゴリの下の **[コマンド**] ページのコマンドの一覧にボタンを挿入します。

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>パラメーター

*uiカテゴリId*<br/>
[in]ツール バーを追加するカテゴリのリソース ID を指定します。

*uiツールバーのId*<br/>
[in]コマンドの一覧にコマンドが挿入されるツール バーのリソース ID を指定します。

*カテゴリ*<br/>
[in]ツール バーを追加するカテゴリの名前を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`AddToolBar`次の例に`CMFCToolBarsCustomizeDialog`示します。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>解説

各コマンドを表すために使用されるコントロールは[、CMFCToolBarButton クラスオブジェクト](../../mfc/reference/cmfctoolbarbutton-class.md)です。 ツール バーを追加した後[、CMFCToolBarsCustomizeDialog::置換ボタン](#replacebutton)を呼び出すことによって、ボタンを派生型のコントロールに置き換えることができます。

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>ダイアログボックスをカスタマイズする::チェックツール妥当性

ユーザー ツールの一覧の有効性を検証します。

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>パラメーター

*lst ツール*<br/>
[in]確認するユーザー定義ツールのリスト。

### <a name="return-value"></a>戻り値

ユーザー定義ツールの一覧が有効な場合は TRUE を返します。それ以外の場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して[、CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)によって返されるユーザー定義ツールを表すオブジェクトの有効性を確認します。

ユーザー`CheckToolsValidity`ツールを検証してからダイアログ`CMFCToolBarsCustomizeDialog`ボックスを閉じる場合は、派生したクラスのメソッドをオーバーライドします。 ユーザーがダイアログ ボックスの右上隅にある [**閉じる**] ボタン、またはダイアログ ボックスの右下隅にある **[閉じる**] ボタンをクリックしたときに、このメソッドから FALSE が返された場合、ダイアログ ボックスには閉じる代わりに **[ツール**] タブが表示されます。 ユーザーがタブをクリックして **[ツール**] タブから移動したときにこのメソッドが FALSE を返した場合、ナビゲーションは行われません。 検証が失敗する原因となった問題をユーザーに通知するには、適切なメッセージ ボックスを表示する必要があります。

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>ダイアログボックスをカスタマイズします。

`CMFCToolBarsCustomizeDialog` オブジェクトを構築します。

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>パラメーター

*親フレーム*<br/>
[in]親フレームへのポインター。 このパラメーターは NULL にすることはできません。

*メニューからセットを行う*<br/>
[in]すべてのメニューのメニュー コマンドを[**コマンド**]ページのコマンドの一覧に追加するかどうかを指定するブール値。 このパラメーターが TRUE の場合、メニュー コマンドが追加されます。 それ以外の場合、メニュー コマンドは追加されません。

*ui フラグ*<br/>
[in]ダイアログ ボックスの動作に影響を与えるフラグの組み合わせ。 このパラメーターには、次の値の 1 つ以上を指定できます。

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*カスタムページ*<br/>
[in]追加のカスタム ページを`CRuntimeClass`指定するオブジェクトのリストへのポインター。

### <a name="remarks"></a>解説

*plistCustomPages*パラメーターは、追加のカスタム`CRuntimeClass`ページを指定するオブジェクトのリストを参照します。 コンストラクターは[、CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject)メソッドを使用して、ダイアログ ボックスにさらにページを追加します。 CustomPages のサンプルを参照して、[**ユーザー設定**] ダイアログ ボックスにさらにページを追加する例を示します。

*パラメーターで*渡すことができる値の詳細については[、「CMFCToolBars カスタマイズ ダイアログ::GetFlags](#getflags)」を参照してください。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCToolBarsCustomizeDialog`示します。 このコード スニペットは、[カスタム ページのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>ダイアログボックスをカスタマイズする::作成

**[カスタマイズ**] ダイアログ ボックスを表示します。

```
virtual BOOL Create();
```

### <a name="return-value"></a>戻り値

カスタマイズ プロパティ シートが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

クラスを`Create`完全に初期化した後にのみ、このメソッドを呼び出します。

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>ダイアログ ボックスを表示します。

[**ユーザー設定**] ダイアログ ボックスを使用して、新しいツールバーの作成を有効または無効にします。

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]ユーザー定義のツール バーを有効にする場合は TRUE。FALSE を指定すると、ツール バーが無効になります。

### <a name="remarks"></a>解説

*bEnable*が TRUE の場合は、[**ツールバー** ] ページに **[新規作成**]、[**名前変更**]、および [**削除**] ボタンが表示されます。

デフォルトで、または*bEnable*が FALSE の場合、これらのボタンは表示されず、ユーザーは新しいツールバーを定義できません。

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>ダイアログボックスをカスタマイズします。

指定した`CListBox`オブジェクトに **[すべてのコマンド]** カテゴリのコマンドを設定します。

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>パラメーター

*コマンドを実行します。*<br/>
[アウト]設定する`CListBox`オブジェクトへの参照。

### <a name="remarks"></a>解説

**[すべてのコマンド]** カテゴリには、すべてのカテゴリのコマンドが含まれています。 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドは、提供されたボタンに関連付けられているコマンドを **[すべてのコマンド**]カテゴリに追加します。

このメソッドは、指定された`CListBox`オブジェクトの内容をクリアしてから、**すべてのコマンド**カテゴリのコマンドを設定します。

クラス`CMFCMousePropertyPage`はこのメソッドを使用して、ダブルクリックイベント リスト ボックスにデータを設定します。

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>ダイアログボックスをカスタマイズします。

指定した`CComboBox`オブジェクトに、[**カスタマイズ**] ダイアログ ボックスの各コマンド カテゴリの名前を設定します。

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[アウト]設定する`CComboBox`オブジェクトへの参照。

*空を追加します。*<br/>
[in]コマンドを持たないコンボ ボックスにカテゴリを追加するかどうかを指定するブール値。 このパラメーターが TRUE の場合、空のカテゴリがコンボ ボックスに追加されます。 それ以外の場合、空のカテゴリは追加されません。

### <a name="remarks"></a>解説

このメソッドは、このメソッドが`CComboBox`オブジェクトで動作することを除いて[、CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)メソッドに似ています。

このメソッドは、オブジェクトの内容を取得`CComboBox`する前にクリアしません。 **[すべてのコマンド]** カテゴリがコンボ ボックスの最後の項目であることを保証します。

新しいコマンド カテゴリを追加するには、[メソッド](#addbutton)を使用します。 既存のカテゴリの名前を変更するには、[メソッド](#renamecategory)を使用します。

クラス`CMFCToolBarsKeyboardPropertyPage`と`CMFCKeyMapDialog`クラスは、このメソッドを使用してキーボード マッピングを分類します。

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>ダイアログ ボックスをカスタマイズします。

指定した`CListBox`オブジェクトに、[**カスタマイズ**] ダイアログ ボックスの各コマンド カテゴリの名前を設定します。

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[アウト]設定する`CListBox`オブジェクトへの参照。

*空を追加します。*<br/>
[in]コマンドを含まないカテゴリをリスト ボックスに追加するかどうかを指定するブール値。 このパラメーターが TRUE の場合、空のカテゴリがリスト ボックスに追加されます。 それ以外の場合、空のカテゴリは追加されません。

### <a name="remarks"></a>解説

このメソッドは、このメソッドが`CListBox`オブジェクトで動作することを除いて[、CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)メソッドに似ています。

このメソッドは、オブジェクトの内容を取得`CListBox`する前にクリアしません。 **[すべてのコマンド]** カテゴリがリスト ボックスの最後の項目であることを保証します。

新しいコマンド カテゴリを追加するには、[メソッド](#addbutton)を使用します。 既存のカテゴリの名前を変更するには、[メソッド](#renamecategory)を使用します。

クラス`CMFCToolBarsCommandsPropertyPage`は、このメソッドを使用して、各コマンド カテゴリに関連付けられているコマンドの一覧を表示します。

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>ダイアログボックスをカスタマイズします。

指定されたコマンド ID に関連付けられている名前を取得します。

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]取得するコマンドの ID。

### <a name="return-value"></a>戻り値

指定されたコマンド ID に関連付けられている名前。またはコマンドが存在しない場合は NULL。

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>ダイアログボックスをカスタマイズします。

指定されたテキスト ラベルを持つ、指定されたリスト内の項目数を取得します。

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
[in]一致させるテキスト ラベル。

*コマンド*<br/>
[in]オブジェクトを含む`CMFCToolBarButton`リストへの参照。

### <a name="return-value"></a>戻り値

指定されたリスト内の項目のうち、テキスト ラベルが*lpszItemName*に等しい数。

### <a name="remarks"></a>解説

指定されたオブジェクト リストの各要素は、 `CMFCToolBarButton`type である必要があります。 このメソッドは、*データ*メンバーを[m_strText比較](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)します。

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>ダイアログボックスをカスタマイズします。

ダイアログ ボックスの動作に影響を与えるフラグのセットを取得します。

```
UINT GetFlags() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの動作に影響を与えるフラグのセット。

### <a name="remarks"></a>解説

このメソッドは、コンストラクターに渡される*uiFlags*パラメーターの値を取得します。 戻り値は、次の値のいずれかまたは複数です。

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|メニューのシャドウの外観を指定できます。  |
|AFX_CUSTOMIZE_TEXT_LABELS|ツール バー ボタン イメージの下にテキスト ラベルを表示するかどうかをユーザーが指定できるようにします。  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|ユーザーがメニュー アニメーションスタイルを指定できるようにします。  |
|AFX_CUSTOMIZE_NOHELP|カスタマイズ ダイアログ ボックスからヘルプ ボタンを削除します。  |
|AFX_CUSTOMIZE_CONTEXT_HELP|WS_EX_CONTEXTHELP表示スタイルを有効にします。  |
|AFX_CUSTOMIZE_NOTOOLS|[**ツール**] ページをカスタマイズ ダイアログ ボックスから削除します。 このフラグは、アプリケーションがクラスを使用`CUserToolsManager`する場合に有効です。  |
|AFX_CUSTOMIZE_MENUAMPERS|ボタンキャプションにアンパサンド ()**&** 文字を含めることができます。  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|[**大きいアイコン]** オプションをカスタマイズ ダイアログ ボックスから削除します。  |

WS_EX_CONTEXTHELP表示スタイルの詳細については、「[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)」を参照してください。

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>ダイアログボックスをカスタマイズします。

ユーザー ツールの変更が発生した直後に応答します。

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[イン、アウト]変更されたユーザー ツール オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、ユーザーがユーザー定義ツールのプロパティを変更したときに、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 ユーザー ツールの変更後に処理`CMFCToolBarsCustomizeDialog`を実行するには、派生したクラスでこのメソッドをオーバーライドします。

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>ダイアログボックスをカスタマイズします。

ユーザーが定義したキーボード ショートカットを検証します。

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>パラメーター

*アッセル*<br/>
[イン、アウト][ACCEL](/windows/win32/api/winuser/ns-winuser-accel)構造体として表現される、提案されたキーボードのアシグメントへのポインター。

### <a name="return-value"></a>戻り値

キーを割り当てることができる場合は TRUE、キーを割り当てることができない場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

ユーザーが新しいキーボード ショートカットを割り当てるときに余分な処理を実行したり、ユーザーが定義したキーボード ショートカットを検証したりするには、派生クラスでこのメソッドをオーバーライドします。 ショートカットが割り当てられないようにするには、FALSE を返します。 また、メッセージ ボックスを表示するか、キーボード ショートカットが拒否された理由をユーザーに通知する必要があります。

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>ダイアログボックスをカスタマイズします。

ユーザーが変更を適用する際にユーザー ツールを変更するときに、カスタム処理を実行します。

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[イン、アウト]置き換えられるユーザー ツール オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、ユーザー定義ツールのプロパティが変更されようとしているときに、フレームワークによって呼び出されます。 既定の実装では、何も行われません。 *pSelTool*が使用するリソース`CMFCToolBarsCustomizeDialog`の`OnBeforeChangeTool`解放など、ユーザー ツールに対する変更が発生する前に処理を実行する場合は、派生クラスのメソッドをオーバーライドします。

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>ダイアログボックスをカスタマイズします。

ユーザーがツール バー ボタンまたはメニュー項目アイコンをカスタマイズできるように、イメージ エディターを起動します。

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]親ウィンドウへのポインター。

*ビットマップ*<br/>
[in]編集するビットマップ オブジェクトへの参照。

*ピクセル数*<br/>
[in]ビットマップのカラー解像度 (ピクセルあたりのビット数)。

### <a name="return-value"></a>戻り値

変更がコミットされている場合は TRUE。それ以外の場合は FALSE。 既定の実装ではダイアログ ボックスが表示され、ユーザーが **[OK]** をクリックした場合は TRUE を返し、ユーザーが **[キャンセル]** または **[閉じる**] ボタンをクリックした場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、ユーザーがイメージ エディターを実行するときに、フレームワークによって呼び出されます。 既定の実装では、[クラス] ダイアログ ボックス[が](../../mfc/reference/cmfcimageeditordialog-class.md)表示されます。 カスタム`OnEditToolbarMenuImage`イメージ エディターを使用するには、派生クラスでオーバーライドします。

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>ダイアログをカスタマイズします。

プロパティ シートの初期化を強化するためにオーバーライドします。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

[メソッドを](../../mfc/reference/cpropertysheet-class.md#oninitdialog)呼び出した結果。

### <a name="remarks"></a>解説

このメソッドは、ダイアログ ボックスが現在の画面サイズに合っていることを確認し、ダイアログ ボックスの左下隅に [**ヘルプ**] ボタンを移動することによって、**基**底クラスの実装[CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)を拡張します。

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>ダイアログボックスをカスタマイズする::オンイニトツールページ

**[ツール**] ページが初期化されるフレームワークからの通知を処理します。

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 この通知を処理するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>ダイアログ:PostNcをカスタマイズする

ウィンドウが破棄された後に、フレームワークによって呼び出されます。

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>解説

このメソッドは、アプリケーションを前の`CPropertySheet::PostNcDestroy`モードに復元することによって、基本クラスの実装を拡張します。

[CMFCToolBarsCustomizeDialog::Create](#create)メソッドは、ユーザーをカスタマイズ タスクに制限する特別なモードでアプリケーションを配置します。

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>ダイアログボックスをカスタマイズします。

指定したコマンド ID を持つボタンを、指定したカテゴリまたはすべてのカテゴリから削除します。

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>パラメーター

*uiカテゴリId*<br/>
[in]ボタンを削除するカテゴリ ID を指定します。

*uiCmdId*<br/>
[in]ボタンのコマンド ID を指定します。

*カテゴリ*<br/>
[in]ボタンを削除するカテゴリの名前を指定します。

### <a name="return-value"></a>戻り値

指定されたカテゴリで指定したコマンド ID が見つからなかった場合は、削除されたボタンの 0 から始まるインデックス。 *uiCategoryId*が -1 の場合、戻り値は 0 です。

### <a name="remarks"></a>解説

すべてのカテゴリからボタンを削除するには、このメソッドの最初のオーバーロードを呼び出し *、uiCategoryId*を -1 に設定します。

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>ダイアログボックスをカスタマイズします。

**[コマンド**] ページのカテゴリのリスト ボックス内のカテゴリの名前を変更します。

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>パラメーター

*古いカテゴリ*<br/>
[in]変更するカテゴリ名。

*新しいカテゴリ*<br/>
[in]新しいカテゴリ名。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

カテゴリ名は一意である必要があります。

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>ダイアログボックスをカスタマイズします。

**[コマンド**] ページのコマンドのリスト ボックス内のツール バー ボタンを置き換えます。

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]置き換えるボタンのコマンドを指定します。

*ボタン*<br/>
[in]古いボタンを置き換えるツール バー ボタン オブジェクトへの**const**参照。

### <a name="remarks"></a>解説

[CMFCToolBars カスタマイズ ダイアログ:::メニュー](#addmenu)バー[カスタマイズダイアログ::](#addmenucommands)または[CMFCMenuコマンドカスタマイズダイアログ:::AddToolBar](#addtoolbar)は **、コマンド**ページにコマンドを追加し、そのコマンドは[CMFCToolBarButtonクラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト(またはサブメニューが追加されたメニュー項目の[CMFCToolBarMenuButtonクラスオブジェクト](../../mfc/reference/cmfctoolbarmenubutton-class.md))の形です`AddMenuCommands`。 フレームワークは、コマンドを自動的に追加するために、これら 3 つのメソッドも呼び出します。 コマンドを派生型で表す場合は、派生型のボタンを`ReplaceButton`呼び出して渡します。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`ReplaceButton`次の例に`CMFCToolBarsCustomizeDialog`示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>ダイアログボックスをカスタマイズします。

**[コマンド**] ページのカテゴリの一覧で、ユーザー カテゴリを指定します。 この関数を呼び出してから[、ダイアログ::作成](#create)を呼び出す必要があります。

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[in]カテゴリの名前。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ユーザー カテゴリの設定は、現在フレームワークによって使用されていません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)
