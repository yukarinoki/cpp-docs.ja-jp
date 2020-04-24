---
title: CContextMenuManager クラス
ms.date: 11/04/2016
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
ms.openlocfilehash: c676355ebf44d6cc02bfa66ac870757627ae5a58
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754804"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager クラス

オブジェクト`CContextMenuManager`はショートカット メニュー (コンテキスト メニューとも呼ばれます) を管理します。

## <a name="syntax"></a>構文

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[メニューマネージャー::Cコンテキストメニューマネージャー](#ccontextmenumanager)|`CContextMenuManager` オブジェクトを構築します。|
|`CContextMenuManager::~CContextMenuManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[メニューマネージャー:メニューの追加](#addmenu)|新しいショートカット メニューを追加します。|
|[メニューマネージャー::メニューバイId](#getmenubyid)|指定されたリソース ID に関連付けられたメニューへのハンドルを返します。|
|[メニューマネージャー::メニューの名前を取得します。](#getmenubyname)|指定されたメニュー名と一致するメニューへのハンドルを返します。|
|[メニューマネージャー::メニュー名を取得します。](#getmenunames)|メニュー名の一覧を返します。|
|[メニューマネージャー::ロードステート](#loadstate)|Windows レジストリに格納されているショートカット メニューを読み込みます。|
|[メニューマネージャー::リセットステート](#resetstate)|ショートカット メニューをショートカット メニュー マネージャから消去します。|
|[メニューマネージャー::セーブステート](#savestate)|ショートカット メニューを Windows レジストリに保存します。|
|[メニューメニュー::セットドントクローズアクティブメニュー](#setdontcloseactivemenu)|新しいショートカット`CContextMenuManager`メニューを表示したときに、アクティブなショートカット メニューを閉じるかどうかを制御します。|
|[メニューメニュー::メニューを表示します。](#showpopupmenu)|指定したショートカット メニューを表示します。|
|[メニューメニュー::トラックポップアップメニュー](#trackpopupmenu)|指定したショートカット メニューを表示します。 選択したメニュー コマンドのインデックスを返します。|

## <a name="remarks"></a>解説

`CContextMenuManager`は、ショートカット メニューを管理し、一貫性のある外観を持つことを確認します。

オブジェクトは手動で`CContextMenuManager`作成しないでください。 アプリケーションのフレームワークによってオブジェクトが作成`CContextMenuManager`されます。 ただし、アプリケーションが初期化されるときに[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)を呼び出す必要があります。 コンテキスト マネージャーを初期化した後、メソッド[CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)を使用して、アプリケーションのコンテキスト マネージャーへのポインターを取得します。

ショートカット メニューは、実行時に を`AddMenu`呼び出して作成できます。 ユーザー入力を受け取らずにメニューを表示する場合は`ShowPopupMenu`、 を呼び出します。 `TrackPopupMenu`は、メニューを作成してユーザー入力を待つ場合に使用します。 `TrackPopupMenu`は、選択したコマンドのインデックスを返します。

また`CContextMenuManager`、その状態を保存して Windows レジストリに読み込むこともできます。

## <a name="example"></a>例

次の例は、`CContextMenuManager`オブジェクトにメニューを追加する方法と、オブジェクトに新しいポップアップ メニューが表示されたときにアクティブなポップアップ`CContextMenuManager`メニューを閉じないようにする方法を示しています。 このコード スニペットは、[カスタム ページのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcontextmenumanager.h

## <a name="ccontextmenumanageraddmenu"></a><a name="addmenu"></a>メニューマネージャー:メニューの追加

新しいショートカット メニューを[追加](../../mfc/reference/ccontextmenumanager-class.md)します。

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]新しいメニューの名前を含む文字列のリソース ID。

*をクリックします。*<br/>
[in]メニュー リソース ID。

*名前を指定します。*<br/>
[in]新しいメニューの名前を含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。メソッドが失敗した場合は 0。

### <a name="remarks"></a>解説

*uiMenuResId*が無効な場合、または同じ名前の別のメニューが既に`CContextMenuManager`.

## <a name="ccontextmenumanagerccontextmenumanager"></a><a name="ccontextmenumanager"></a>メニューマネージャー::Cコンテキストメニューマネージャー

[オブジェクトを](../../mfc/reference/ccontextmenumanager-class.md)構築します。

```
CContextMenuManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、手動で`CContextMenuManager`作成しないでください。 アプリケーションのフレームワークによってオブジェクトが作成`CContextMenuManager`されます。 アプリケーションの初期化中に[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)を呼び出す必要があります。 コンテキスト マネージャーへのポインターを取得するには[、CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)を呼び出します。

## <a name="ccontextmenumanagergetmenubyid"></a><a name="getmenubyid"></a>メニューマネージャー::メニューバイId

指定されたリソース ID に関連付けられたメニューへのハンドルを返します。

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]メニューのリソース ID。

### <a name="return-value"></a>戻り値

関連付けられたメニューへのハンドル、`NULL`またはメニューが見つからない場合。

## <a name="ccontextmenumanagergetmenubyname"></a><a name="getmenubyname"></a>メニューマネージャー::メニューの名前を取得します。

特定のメニューへのハンドルを返します。

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]取得するメニューの名前を含む文字列。

*プイオリグレスID*<br/>
[アウト]UINT へのポインター。 このパラメーターには、指定されたメニューのリソース ID (見つかった場合) が入ります。

### <a name="return-value"></a>戻り値

*lpszName*で指定された名前と一致するメニューへのハンドル。 *lpszName*という名前のメニューがない場合は NULL。

### <a name="remarks"></a>解説

このメソッドが*lpszName*に一致する`GetMenuByName`メニューを見つけた場合は、メニュー リソース ID をパラメーター *puiOrigResID*に格納します。

## <a name="ccontextmenumanagergetmenunames"></a><a name="getmenunames"></a>メニューマネージャー::メニュー名を取得します。

に追加されたメニュー名の一覧を返[します](../../mfc/reference/ccontextmenumanager-class.md)。

```cpp
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>パラメーター

*名前の一覧*<br/>
[アウト][パラメーターへの](../../mfc/reference/cstringlist-class.md)参照。 このメソッドは、メニュー名のリストをこのパラメーターに書き込みます。

## <a name="ccontextmenumanagerloadstate"></a><a name="loadstate"></a>メニューマネージャー::ロードステート

クラス[に関連](../../mfc/reference/ccontextmenumanager-class.md)付けられている情報を Windows レジストリから読み込みます。

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]レジストリ キーの相対パスを含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*パラメーター*はレジストリ エントリの絶対パスではありません。 これは、アプリケーションの既定のレジストリ キーの末尾に追加される相対パスです。 既定のレジストリ キーを取得または設定するには、それぞれメソッド[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase を](../../mfc/reference/cwinappex-class.md#setregistrybase)使用します。

ショートカット メニューをレジストリに保存するには、メソッド[CContextMenuManager::SaveState](#savestate)を使用します。

## <a name="ccontextmenumanagerresetstate"></a><a name="resetstate"></a>メニューマネージャー::リセットステート

[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)に関連付けられているショートカット メニューからすべての項目をクリアします。

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。失敗が発生した場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ポップアップ メニューをクリアし、 から削除します`CContextMenuManager`。

## <a name="ccontextmenumanagersavestate"></a><a name="savestate"></a>メニューマネージャー::セーブステート

[クラス](../../mfc/reference/ccontextmenumanager-class.md)に関連付けられている情報を Windows レジストリに保存します。

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]レジストリ キーの相対パスを含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*パラメーター*はレジストリ エントリの絶対パスではありません。 これは、アプリケーションの既定のレジストリ キーの末尾に追加される相対パスです。 既定のレジストリ キーを取得または設定するには、それぞれメソッド[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase を](../../mfc/reference/cwinappex-class.md#setregistrybase)使用します。

レジストリからショートカット メニューを読み込むには、メソッド[CContextMenuManager::LoadState](#loadstate)を使用します。

## <a name="ccontextmenumanagersetdontcloseactivemenu"></a><a name="setdontcloseactivemenu"></a>メニューメニュー::セットドントクローズアクティブメニュー

新しいポップアップ メニューを表示したときに[、](../../mfc/reference/ccontextmenumanager-class.md)アクティブなポップアップ メニューを閉じるかどうかを制御します。

```cpp
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bセット*<br/>
[in]アクティブなポップアップ メニューを閉じるかどうかを制御するブール値パラメーター。 TRUE の値は、アクティブなポップアップ メニューが閉じられていない状態であることを示します。 FALSE は、アクティブなポップアップ メニューが閉じられていることを示します。

### <a name="remarks"></a>解説

デフォルトでは、アクティブ`CContextMenuManager`なポップアップメニューが閉じます。

## <a name="ccontextmenumanagershowpopupmenu"></a><a name="showpopupmenu"></a>メニューメニュー::メニューを表示します。

指定したショートカット メニューを表示します。

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]このメソッドが表示するメニューのリソース ID。

*x*<br/>
[in]クライアント座標のショートカット メニューの水平オフセット。

*Y*<br/>
[in]クライアント座標のショートカット メニューの垂直オフセット

*オーナー*<br/>
[in]ショートカット メニューの親ウィンドウへのポインター。

*メッセージを見る*<br/>
[in]メッセージのルーティング方法を示すブール値パラメーター。 *bOwnMessage が*FALSE の場合は、標準の MFC ルーティングが使用されます。 それ以外の場合*は、pWndOwner が*メッセージを受信します。

*hmenuポップアップ*<br/>
[in]このメソッドが表示するメニューのハンドル。

*b自動破壊*<br/>
[in]メニューが自動的に破棄されるかどうかを示すブール値パラメーター。

*右揃え*<br/>
[in]メニュー項目の配置方法を示すブール値パラメーター。 *bRightAlign*が TRUE の場合、右から左への読み取り順序に合わせてメニューが右揃えになります。

### <a name="return-value"></a>戻り値

最初のメソッドオーバーロードは、メソッドがメニューを正常に表示した場合は 0 以外を返します。それ以外の場合は 0。 2 番目のメソッド オーバーロードは、ショートカット メニューが正しく表示された場合は[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)へのポインターを返します。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、両方のメソッドがショートカット メニューを表示するという意味で、メソッド[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)に似ています。 ただし、`TrackPopupMenu`選択したメニュー コマンドのインデックスを返します。

パラメーター *bAutoDestroy*が FALSE の場合は、手動`DestroyMenu`でメモリ リソースを解放する継承されたメソッドを呼び出す必要があります。 のデフォルトの`ShowPopupMenu`実装では、 *bAutoDestroy*パラメータは使用されません。 これは、将来使用するために、またはクラスから派生したカスタム`CContextMenuManager`クラスのために提供されます。

## <a name="ccontextmenumanagertrackpopupmenu"></a><a name="trackpopupmenu"></a>メニューメニュー::トラックポップアップメニュー

指定したショートカット メニューを表示し、選択したショートカット メニュー コマンドのインデックスを返します。

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>パラメーター

*hmenuポップアップ*<br/>
[in]このメソッドが表示するショートカット メニューのハンドル。

*x*<br/>
[in]クライアント座標のショートカット メニューの水平オフセット。

*Y*<br/>
[in]クライアント座標のショートカット メニューの垂直オフセット。

*オーナー*<br/>
[in]ショートカット メニューの親ウィンドウへのポインター。

*右揃え*<br/>
[in]メニュー項目の配置方法を示すブール値パラメーター。 *bRightAlign*が TRUE の場合、右から左への読み取り順序に合わせてメニューが右揃えになります。 *bRightAlign*が FALSE の場合、メニューは左から右への読み取り順序で左揃えになります。

### <a name="return-value"></a>戻り値

ユーザーが選択するコマンドのメニュー コマンド ID。ユーザーがメニュー コマンドを選択せずにショートカット メニューを閉じる場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ショートカット メニューを表示するモーダル呼び出しとして機能します。 ユーザーがショートカット メニューを閉じるか、コマンドを選択するまで、アプリケーションはコード内で次の行に進み続けます。 ショートカット メニューを表示する場合に使用できる別の方法は[、CContextMenuManager::ShowPopupMenu です](#showpopupmenu)。 このメソッドはモーダル呼び出しではなく、選択したコマンドの ID を返しません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
