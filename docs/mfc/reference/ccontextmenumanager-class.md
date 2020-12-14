---
description: '詳細情報: CContextMenuManager クラス'
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
ms.openlocfilehash: f026b493ae5f7ae90eccc416d8920d8b699e975d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227820"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager クラス

`CContextMenuManager`オブジェクトはショートカットメニューを管理します。ショートカットメニューは、コンテキストメニューとも呼ばれます。

## <a name="syntax"></a>構文

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|`CContextMenuManager` オブジェクトを構築します。|
|`CContextMenuManager::~CContextMenuManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CContextMenuManager:: AddMenu](#addmenu)|新しいショートカットメニューを追加します。|
|[CContextMenuManager::GetMenuById](#getmenubyid)|指定されたリソース ID に関連付けられているメニューへのハンドルを返します。|
|[CContextMenuManager::GetMenuByName](#getmenubyname)|指定されたメニュー名と一致するメニューへのハンドルを返します。|
|[CContextMenuManager:: GetMenuNames](#getmenunames)|メニュー名の一覧を返します。|
|[CContextMenuManager:: LoadState](#loadstate)|Windows レジストリに格納されているショートカットメニューを読み込みます。|
|[CContextMenuManager:: Resetstate 出す](#resetstate)|ショートカットメニューをコンテキストメニューマネージャーから消去します。|
|[CContextMenuManager:: SaveState](#savestate)|ショートカットメニューを Windows レジストリに保存します。|
|[CContextMenuManager:: SetDontCloseActiveMenu](#setdontcloseactivemenu)|`CContextMenuManager`新しいショートカットメニューが表示されたときに、アクティブなショートカットメニューを閉じるかどうかを制御します。|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|指定されたショートカットメニューを表示します。|
|[CContextMenuManager:: TrackPopupMenu](#trackpopupmenu)|指定されたショートカットメニューを表示します。 選択されたメニューコマンドのインデックスを返します。|

## <a name="remarks"></a>解説

`CContextMenuManager` ショートカットメニューを管理し、外観が一貫していることを確認します。

オブジェクトを手動で作成しないでください `CContextMenuManager` 。 アプリケーションのフレームワークによってオブジェクトが作成され `CContextMenuManager` ます。 ただし、アプリケーションを初期化するときは、 [CWinAppEx:: InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) を呼び出す必要があります。 コンテキストマネージャーを初期化した後、 [CWinAppEx:: GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) メソッドを使用して、アプリケーションのコンテキストマネージャーへのポインターを取得します。

を呼び出すことにより、実行時にショートカットメニューを作成でき `AddMenu` ます。 最初にユーザー入力を受信せずにメニューを表示する場合は、を呼び出し `ShowPopupMenu` ます。 `TrackPopupMenu` は、メニューを作成し、ユーザーの入力を待機する場合に使用します。 `TrackPopupMenu` 選択されたコマンドのインデックスを返します。ユーザーが何も選択せずに終了した場合は0を返します。

また、は、 `CContextMenuManager` その状態を保存して Windows レジストリに読み込むこともできます。

## <a name="example"></a>例

次の例では、オブジェクトにメニューを追加する方法 `CContextMenuManager` と、 `CContextMenuManager` オブジェクトに新しいポップアップメニューが表示されたときにアクティブなポップアップメニューを閉じないようにする方法を示します。 このコードスニペットは、 [カスタムページサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxcontextmenumanager

## <a name="ccontextmenumanageraddmenu"></a><a name="addmenu"></a> CContextMenuManager:: AddMenu

新しいショートカットメニューを [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)に追加します。

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>パラメーター

*uiMenuNameResId*<br/>
から新しいメニューの名前を含む文字列のリソース ID。

*uiMenuResId*<br/>
からメニューリソース ID。

*lpszName*<br/>
から新しいメニューの名前を含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は0以外の。メソッドが失敗した場合は0。

### <a name="remarks"></a>解説

*UiMenuResId* が無効な場合、または同じ名前の別のメニューがに既に存在する場合、このメソッドは失敗し `CContextMenuManager` ます。

## <a name="ccontextmenumanagerccontextmenumanager"></a><a name="ccontextmenumanager"></a> CContextMenuManager::CContextMenuManager

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトを構築します。

```
CContextMenuManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、手動でを作成することはできません `CContextMenuManager` 。 アプリケーションのフレームワークによってオブジェクトが作成され `CContextMenuManager` ます。 アプリケーションの初期化中に [CWinAppEx:: InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) を呼び出す必要があります。 コンテキストマネージャーへのポインターを取得するには、 [CWinAppEx:: GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)を呼び出します。

## <a name="ccontextmenumanagergetmenubyid"></a><a name="getmenubyid"></a> CContextMenuManager::GetMenuById

指定したリソース ID に関連付けられているメニューへのハンドルを返します。

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>パラメーター

*nMenuResId*<br/>
からメニューのリソース ID。

### <a name="return-value"></a>戻り値

関連付けられているメニューへのハンドル `NULL` 。メニューが見つからない場合は。

## <a name="ccontextmenumanagergetmenubyname"></a><a name="getmenubyname"></a> CContextMenuManager::GetMenuByName

特定のメニューへのハンドルを返します。

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
から取得するメニューの名前を格納している文字列。

*puiOrigResID*<br/>
入出力UINT を指すポインターです。 このパラメーターには、指定したメニューのリソース ID が含まれます (見つかった場合)。

### <a name="return-value"></a>戻り値

*Lpszname* によって指定された名前と一致するメニューへのハンドル。 *Lpszname* という名前のメニューがない場合は NULL です。

### <a name="remarks"></a>解説

このメソッドが *Lpszname* と一致するメニューを見つけると、は `GetMenuByName` メニューリソース ID をパラメーター *puiOrigResID* に格納します。

## <a name="ccontextmenumanagergetmenunames"></a><a name="getmenunames"></a> CContextMenuManager:: GetMenuNames

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)に追加されたメニュー名の一覧を返します。

```cpp
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>パラメーター

*listOfNames*<br/>
入出力 [Cstringlist](../../mfc/reference/cstringlist-class.md) パラメーターへの参照。 このメソッドは、メニュー名のリストをこのパラメーターに書き込みます。

## <a name="ccontextmenumanagerloadstate"></a><a name="loadstate"></a> CContextMenuManager:: LoadState

Windows レジストリから [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md) に関連付けられている情報を読み込みます。

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からレジストリキーの相対パスを含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Lpszprofilename* パラメーターが、レジストリエントリの絶対パスではありません。 これは、アプリケーションの既定のレジストリキーの末尾に追加される相対パスです。 既定のレジストリキーを取得または設定するには、メソッド [CWinAppEx:: getregistrybase](../../mfc/reference/cwinappex-class.md#getregistrybase) と [CWinAppEx:: setregistrybase](../../mfc/reference/cwinappex-class.md#setregistrybase) をそれぞれ使用します。

[CContextMenuManager:: SaveState](#savestate)メソッドを使用して、ショートカットメニューをレジストリに保存します。

## <a name="ccontextmenumanagerresetstate"></a><a name="resetstate"></a> CContextMenuManager:: Resetstate 出す

[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)に関連付けられているショートカットメニューからすべての項目を削除します。

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。エラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ポップアップメニューをクリアし、から削除し `CContextMenuManager` ます。

## <a name="ccontextmenumanagersavestate"></a><a name="savestate"></a> CContextMenuManager:: SaveState

[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)に関連付けられている情報を Windows レジストリに保存します。

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からレジストリキーの相対パスを含む文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Lpszprofilename* パラメーターが、レジストリエントリの絶対パスではありません。 これは、アプリケーションの既定のレジストリキーの末尾に追加される相対パスです。 既定のレジストリキーを取得または設定するには、メソッド [CWinAppEx:: getregistrybase](../../mfc/reference/cwinappex-class.md#getregistrybase) と [CWinAppEx:: setregistrybase](../../mfc/reference/cwinappex-class.md#setregistrybase) をそれぞれ使用します。

[CContextMenuManager:: LoadState](#loadstate)メソッドを使用して、レジストリからショートカットメニューを読み込みます。

## <a name="ccontextmenumanagersetdontcloseactivemenu"></a><a name="setdontcloseactivemenu"></a> CContextMenuManager:: SetDontCloseActiveMenu

新しいポップアップメニューが表示されたときに、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) がアクティブなポップアップメニューを閉じるかどうかを制御します。

```cpp
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSet*<br/>
からアクティブなポップアップメニューを閉じるかどうかを制御するブール型パラメーターです。 値が TRUE の場合は、アクティブなポップアップメニューが閉じていないことを示します。 FALSE は、アクティブなポップアップメニューが閉じていることを示します。

### <a name="remarks"></a>解説

既定では、は `CContextMenuManager` アクティブなポップアップメニューを閉じます。

## <a name="ccontextmenumanagershowpopupmenu"></a><a name="showpopupmenu"></a> CContextMenuManager::ShowPopupMenu

指定されたショートカットメニューを表示します。

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

*uiMenuResId*<br/>
からこのメソッドが表示するメニューのリソース ID。

*x*<br/>
からクライアント座標のショートカットメニューの水平方向のオフセット。

*y*<br/>
からクライアント座標のショートカットメニューの垂直方向のオフセット

*pWndOwner*<br/>
からショートカットメニューの親ウィンドウへのポインター。

*bOwnMessage*<br/>
からメッセージのルーティング方法を示すブール型パラメーターです。 *BOwnMessage* が FALSE の場合、標準の MFC ルーティングが使用されます。 それ以外の場合、 *pWndOwner* はメッセージを受信します。

*hmenuPopup*<br/>
からこのメソッドが表示するメニューのハンドル。

*bAutoDestroy*<br/>
からメニューを自動的に破棄するかどうかを示すブール型パラメーターです。

*bRightAlign*<br/>
からメニュー項目のアライン方法を示すブール型パラメーター。 *BRightAlign* が TRUE の場合、右から左への読み取り順序に対してメニューが右揃えになります。

### <a name="return-value"></a>戻り値

最初のメソッドオーバーロードは、メソッドがメニューを正常に表示した場合は0以外の値を返します。それ以外の場合は0です。 2番目のメソッドオーバーロードは、ショートカットメニューが正しく表示された場合に、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) へのポインターを返します。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは [CContextMenuManager:: TrackPopupMenu](#trackpopupmenu) メソッドに似ていますが、どちらの方法でもショートカットメニューが表示されます。 ただし、では、 `TrackPopupMenu` 選択したメニューコマンドのインデックスが返されます。

パラメーター *Bautodestroy* が FALSE の場合は、継承されたメソッドを手動で呼び出して、 `DestroyMenu` メモリリソースを解放する必要があります。 の既定の実装で `ShowPopupMenu` は、パラメーター *Bautodestroy* は使用されません。 将来使用するため、またはクラスから派生したカスタムクラス用に提供され `CContextMenuManager` ます。

## <a name="ccontextmenumanagertrackpopupmenu"></a><a name="trackpopupmenu"></a> CContextMenuManager:: TrackPopupMenu

指定したショートカットメニューを表示し、選択したショートカットメニューコマンドのインデックスを返します。

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>パラメーター

*hmenuPopup*<br/>
からこのメソッドが表示するショートカットメニューのハンドル。

*x*<br/>
からクライアント座標のショートカットメニューの水平方向のオフセット。

*y*<br/>
からクライアント座標のショートカットメニューの垂直方向のオフセット。

*pWndOwner*<br/>
からショートカットメニューの親ウィンドウへのポインター。

*bRightAlign*<br/>
からメニュー項目のアライン方法を示すブール型パラメーター。 *BRightAlign* が TRUE の場合、右から左への読み取り順序に対してメニューが右揃えになります。 *BRightAlign* が FALSE の場合、メニューは左から右への読み取り順序で左揃えになります。

### <a name="return-value"></a>戻り値

ユーザーが選択したコマンドのメニューコマンド ID。ユーザーがメニューコマンドを選択せずにショートカットメニューを閉じる場合は0。

### <a name="remarks"></a>解説

このメソッドは、ショートカットメニューを表示するためのモーダル呼び出しとして機能します。 アプリケーションは、ユーザーがショートカットメニューを閉じるかコマンドを選択するまで、コード内の次の行に進みません。 ショートカットメニューを表示する別の方法として、 [CContextMenuManager:: ShowPopupMenu](#showpopupmenu)を使用できます。 このメソッドはモーダル呼び出しではなく、選択したコマンドの ID を返しません。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
