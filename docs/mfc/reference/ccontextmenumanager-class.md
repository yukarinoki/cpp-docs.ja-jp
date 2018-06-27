---
title: CContextMenuManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9407c98183fa923a58ca2939e8c534cd56dc8ef7
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954622"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager クラス
`CContextMenuManager`オブジェクト管理ショートカット メニュー、コンテキスト メニューとも呼ばれます。  
  
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
|[CContextMenuManager::AddMenu](#addmenu)|新しいショートカット メニューを追加します。|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|指定されたリソース ID に関連付けられたメニューへのハンドルを返します|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|指定されたメニュー名に一致するメニューへのハンドルを返します。|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|メニュー名の一覧を返します。|  
|[CContextMenuManager::LoadState](#loadstate)|Windows レジストリに格納されているショートカット メニューを読み込みます。|  
|[CContextMenuManager::ResetState](#resetstate)|コンテキスト メニュー マネージャーからショートカット メニューをクリアします。|  
|[CContextMenuManager::SaveState](#savestate)|ショートカット メニューを Windows レジストリに保存します。|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|コントロールかどうか、`CContextMenuManager`新しいショートカット メニューを表示すると、active のショートカット メニューを閉じます。|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|指定したショートカット メニューを表示します。|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|指定したショートカット メニューを表示します。 選択されたメニュー コマンドのインデックスを返します。|  
  
## <a name="remarks"></a>Remarks  
 `CContextMenuManager` ショートカット メニューを管理し、一貫した外観があることを確認します。  
  
 作成しないようにする、`CContextMenuManager`手動でのオブジェクトします。 アプリケーションのフレームワークを作成、`CContextMenuManager`オブジェクト。 ただし、呼び出す必要があります[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)アプリケーションが初期化される場合。 コンテキスト マネージャーを初期化した後にメソッドを使用して[CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)アプリケーションのコンテキスト マネージャーへのポインターを取得します。  
  
 実行時にショートカット メニューを作成するには呼び出すことによって`AddMenu`です。 最初の受信側ユーザー入力なしメニューを表示する場合は、呼び出す`ShowPopupMenu`です。 `TrackPopupMenu` メニューを作成し、ユーザー入力を待機するときに使用されます。 `TrackPopupMenu` ユーザーが何も選択せずに終了した場合は、選択したコマンドまたは 0 のインデックスを返します。  
  
 `CContextMenuManager`も保存し、Windows レジストリにその状態を読み込むことができます。  
  
## <a name="example"></a>例  
 次の例では、メニューを追加する方法、`CContextMenuManager`オブジェクト、およびアクティブなポップアップ メニューを閉じる方法ときに、`CContextMenuManager`オブジェクトが新しいポップアップ メニューを表示します。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>  CContextMenuManager::AddMenu  
 新しいショートカット メニューを追加、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)です。  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiMenuNameResId*  
 新しいメニューの名前を含む文字列のリソース ID です。  
  
 [in]*uiMenuResId*  
 メニューの リソース id です。  
  
 [in]*lpszName*  
 新しいメニューの名前を表す文字列。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。メソッドが失敗した場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは失敗*uiMenuResId*が無効か、同じ名前の別のメニューに既に存在するかどうか、`CContextMenuManager`です。  
  
##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager  
 構築、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクト。  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Remarks  
 ほとんどの場合、作成しないようにする、`CContextMenuManager`手動でします。 アプリケーションのフレームワークを作成、`CContextMenuManager`オブジェクト。 呼び出す必要があります[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)アプリケーションの初期化中にします。 コンテキスト マネージャーへのポインターを取得する[CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)です。  
  
##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById  
 特定のリソース ID に関連付けられたメニューへのハンドルを返します  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nMenuResId*  
 メニュー リソース ID です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられたメニューへのハンドルまたは`NULL`メニューが見つからない場合。  
  
##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName  
 特定のメニューのハンドルを返します。  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 取得するメニューの名前を表す文字列。  
  
 [out]*puiOrigResID*  
 `UINT` へのポインター。 このパラメーターには、指定されたメニューのリソース ID が含まれる場合が見つかりました。  
  
### <a name="return-value"></a>戻り値  
 指定された名前に一致するメニューへのハンドル*lpszName*です。 `NULL` メニューと呼ばれるがないかどうかは*lpszName*です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドに一致するメニューが検出されると*lpszName*、`GetMenuByName`パラメーターでメニュー リソース ID を格納*puiOrigResID*です。  
  
##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames  
 追加のメニュー名の一覧を返します、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)です。  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*listOfNames*  
 参照、 [CStringList](../../mfc/reference/cstringlist-class.md)パラメーター。 このメソッドは、このパラメーターにあるメニュー名の一覧を書き込みます。  
  
##  <a name="loadstate"></a>  CContextMenuManager::LoadState  
 関連付けられている情報を読み込み、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)Windows レジストリからです。  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 レジストリ キーの相対パスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 *LpszProfileName*パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 取得または既定のレジストリ キーを設定、メソッドを使用して[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase)それぞれします。  
  
 メソッドを使用して[CContextMenuManager::SaveState](#savestate)ショートカット メニューをレジストリに保存します。  
  
##  <a name="resetstate"></a>  CContextMenuManager::ResetState  
 関連付けられたショートカット メニューからのすべての項目を削除、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)です。  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合`FALSE`障害が発生した場合。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ポップアップ メニューをクリアし、削除してから、`CContextMenuManager`です。  
  
##  <a name="savestate"></a>  CContextMenuManager::SaveState  
 関連付けられている情報を保存、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)Windows レジストリにします。  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 レジストリ キーの相対パスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 *LpszProfileName*パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 取得または既定のレジストリ キーを設定、メソッドを使用して[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase)それぞれします。  
  
 メソッドを使用して[CContextMenuManager::LoadState](#loadstate)ショートカット メニューをレジストリから読み込めません。  
  
##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu  
 コントロールかどうか、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)新しいポップアップ メニューを表示するときに、アクティブなポップアップ メニューを閉じます。  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bSet*  
 アクティブなポップアップ メニューを閉じるかどうかを制御するブール型のパラメーターです。 値`TRUE`アクティブなポップアップ メニューが閉じられていないことを示します。 `FALSE` アクティブなポップアップ メニューが閉じられたことを示します。  
  
### <a name="remarks"></a>Remarks  
 既定では、`CContextMenuManager`アクティブなポップアップ メニューを閉じます。  
  
##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu  
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
 [in]*uiMenuResId*  
 このメソッドが表示されるメニューのリソース ID です。  
  
 [in]*x*  
 水平方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [in]*y*  
 クライアント座標でショートカット メニューを縦方向のオフセット  
  
 [in]*pWndOwner*  
 ショートカット メニューの親ウィンドウへのポインター。  
  
 [in]*bOwnMessage*  
 メッセージがルーティングされる方法を示すブール値パラメーターです。 場合*bOwnMessage*は`FALSE`MFC の標準的なルーティングが使用されます。 それ以外の場合、 *pWndOwner*メッセージを受信します。  
  
 [in]*hmenuPopup*  
 このメソッドが表示されるメニューのハンドル。  
  
 [in]*bAutoDestroy*  
 メニューが自動的に破棄されるかどうかを示すブール値パラメーターです。  
  
 [in]*bRightAlign*  
 メニュー項目を配置する方法を示すブール値パラメーターです。 場合*bRightAlign*は`TRUE`メニューが右から左への読み取り順序の右側に配置します。  
  
### <a name="return-value"></a>戻り値  
 最初のメソッド オーバー ロードが、メソッドは、メニューを正常に表示されている場合は 0 以外を返しますそれ以外の場合 0 を返します。 2 番目のメソッド オーバー ロードへのポインターを返します[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)正しくです。 それ以外の場合、ショートカット メニューが表示される場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドがメソッドに似た[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)点で、両方のメソッドは、ショートカット メニューを表示します。 ただし、`TrackPopupMenu`選択されたメニュー コマンドのインデックスを返します。  
  
 場合、パラメーター *bAutoDestroy*は`FALSE`、手動で呼び出す必要があります、継承された`DestroyMenu`メモリ リソースを解放します。 既定の実装`ShowPopupMenu`パラメーターを使用しない*bAutoDestroy*です。 派生したカスタム クラスの将来使用するために用意されて、`CContextMenuManager`クラスです。  
  
##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu  
 指定したショートカット メニューを表示し、選択したショートカット メニューのコマンドのインデックスを返します。  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hmenuPopup*  
 このメソッドは、表示されるショートカット メニューのハンドル。  
  
 [in]*x*  
 水平方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [in]*y*  
 垂直方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [in]*pWndOwner*  
 ショートカット メニューの親ウィンドウへのポインター。  
  
 [in]*bRightAlign*  
 メニュー項目を配置する方法を示すブール値パラメーターです。 場合*bRightAlign*は`TRUE`メニューが右から左への読み取り順序の右側に配置します。 場合*bRightAlign*は`FALSE`メニューが左から右への読み取り順序の左側に配置します。  
  
### <a name="return-value"></a>戻り値  
 ユーザーが選択されたコマンドのメニュー コマンド IDユーザーがメニュー コマンドを選択せずに、ショートカット メニューを閉じた場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ショートカット メニューを表示するモーダル呼び出しとして機能します。 アプリケーションは、ユーザーは、ショートカット メニューを閉じるかコマンドを選択するまでのコードに、次の行には続行されません。 ショートカット メニューを表示に使用できる代替のメソッドは[CContextMenuManager::ShowPopupMenu](#showpopupmenu)です。 そのメソッドでは、モーダル呼び出しではありませんし、選択したコマンドの ID は返されません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
