---
title: CBaseTabbedPane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
dev_langs:
- C++
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb9fe1942f9fe8b462ce9fc6a56e37538866174
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954989"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane クラス
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md) の機能を拡張して、タブ付きウィンドウの作成をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cbasetabbedpane::addtab](#addtab)|タブ付きペインに新しいタブを追加します。|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄するかどうかを指定します。|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|タブ付きペインに、レジストリから読み込まれているタブの設定を適用します。|  
|[CBaseTabbedPane::CanFloat](#canfloat)|ペインをフローティングできるかどうかを判断します。 (上書き[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat))。|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きウィンドウのキャプションがアクティブなタブとして同じテキストを表示するかどうかを判断します。|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(上書き[CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument))。|  
|[Cbasetabbedpane::detachpane](#detachpane)|1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|有効またはアクティブなタブにラベルのテキストとキャプション テキストを同期するタブ付きペインの機能を無効にします。|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|内部のタブ オーダーを既定の状態に復元します。|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|タブがタブの 0 から始まるインデックスによって識別されると、タブにあるペインを返します。|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|ペインの ID によって識別されるペインを返します|  
|[Cbasetabbedpane::floattab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|ウィンドウでタブの既定の順序を返します。|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|最初に表示されているタブへのポインターを取得します。|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|下限のウィンドウのサイズを取得します。 (上書き[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize))。|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|ウィンドウのアイコンへのハンドルを返します。 (上書き[CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon))。|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|タブ付きペインに含まれているペインの一覧を返します。|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|上部と下部のタブ領域に外接する四角形を返します。|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|タブ ウィンドウでタブの数を返します。|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|基になる (ラッピングした) タブ ウィンドウを取得します。|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|表示されるタブの数を返します。|  
|[Cbasetabbedpane::hasautohidemode](#hasautohidemode)|タブ付きペインを自動的に隠すモードに切り替えることができるかどうかを判断します。|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|1 つのタブが表示されるだけの場合に、タブ付きウィンドウを非表示にするかどうかを判断します。|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|シリアル化中に内部的に使用します。|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|ウィンドウのレイアウト情報を再計算されます。 (上書き[cpane::recalclayout](../../mfc/reference/cpane-class.md#recalclayout))。|  
|[CBaseTabbedPane::RemovePane](#removepane)|タブ付きウィンドウからウィンドウを削除します。|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|シリアル化中に内部的に使用します。|  
|`CBaseTabbedPane::Serialize`|(上書き[cdockablepane::serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6))。|  
|`CBaseTabbedPane::SerializeTabWindow`|シリアル化中に内部的に使用します。|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|タブ形式のコントロール バーを自動的に破棄されるかどうかを判断します。|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|ドッキング ペインの間での表示を切り替えます、自動非表示モード。 (上書き[CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode))。|  
|[CBaseTabbedPane::ShowTab](#showtab)|タブの表示と非表示を切り替えます。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは抽象クラスであり、インスタンス化することはできません。 タブ付きペインのすべての種類に共通するサービスを実装します。  
  
 現時点では、ライブラリには 2 つのタブ付きペイン:[派生クラス](../../mfc/reference/ctabbedpane-class.md)と[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
 A`CBaseTabbedPane`オブジェクトへのポインターをラップする、 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)オブジェクト。 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)タブ付きウィンドウの子ウィンドウになります。  
  
 タブ付きペインを作成する方法の詳細については、次を参照してください。 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)、[派生クラス](../../mfc/reference/ctabbedpane-class.md)、および[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxBaseTabbedPane.h  
  
##  <a name="addtab"></a>  Cbasetabbedpane::addtab  
 タブ付きペインに新しいタブを追加します。  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]*pNewBar*  
 追加するウィンドウへのポインター。 このポインターはこのメソッドを呼び出した後、無効になる可能性があります。 詳細については、「解説」を参照してください。  
  
 [in]*bVisible*  
 `TRUE` タブが表示されるようにするにはそれ以外の場合、`FALSE`です。  
  
 [in]*bSetActive*  
 `TRUE` アクティブなタブ、タブを作成するにはそれ以外の場合、`FALSE`です。  
  
 [in]*bDetachable*  
 `TRUE` タブを切り離し可能です。それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウがタブとして正常に追加されました、できなかった場合は、プロセスで破棄されます。 `FALSE` 追加されるウィンドウは、型のオブジェクトが場合`CBaseTabbedPane`です。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 タブ付きペインに新しいタブとして、ウィンドウを追加するには、このメソッドを呼び出します。 場合*pNewBar*型のオブジェクトを指す`CBaseTabbedPane`、そのすべてのタブはタブ付きペインにコピーし、 *pNewBar*は破棄されます。 したがって、 *pNewBar*に無効なポインターになりは使用できません。  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 空のタブ付きペインを破棄するかどうかを指定します。  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は空のタブ付きウィンドウに破棄できます。それ以外の場合、`FALSE`です。 既定の実装では、常に `TRUE` を返します。  
  
### <a name="remarks"></a>Remarks  
 空のタブ付きペインは、破棄されることは許可されていない場合、フレームワークは、ウィンドウを代わりに表示されません。  
  
##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo  
 レジストリから タブの設定を読み込んで、タブ付きウィンドウに適用します。  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bUseTabIndexes*  
 このパラメーターは、フレームワークによって内部的に使用します。  
  
### <a name="remarks"></a>Remarks  
 レジストリからドッキング状態情報を再読み込み時に、このメソッドは、フレームワークによって呼び出されます。 メソッドは、タブ オーダーおよびタブ付きウィンドウのタブ名に関する情報を取得します。  
  
##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat  
 タブ付きペインをフローティングできるかどうかを指定します。  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインをフローティングできる; 場合それ以外の場合、`FALSE`です。  
  
##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName  
 タブ付きウィンドウのキャプションがアクティブなタブとして同じテキストを表示するかどうかを判断します。  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ付きウィンドウのキャプションのテキストがアクティブなタブのテキストに設定されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 メソッドはタブ付きペインのキャプションに表示されるテキストが、アクティブなタブのラベルを使用するかどうかを決定するために使用します。有効にするにまたは呼び出すことによってこの機能を無効にする[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)です。  
  
##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument  
 1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bActiveTabOnly*  
 タブ付きペインを変換するときに指定`TRUE`にアクティブなタブのみを変換します。指定`FALSE`ペイン内のすべてのタブに変換します。  
  
##  <a name="detachpane"></a>  Cbasetabbedpane::detachpane  
 タブ付きウィンドウからウィンドウをデタッチします。  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 デタッチするウィンドウへのポインター。  
  
 [in]*bHide*  
 フレームワークがデタッチされた後に、ペインが非表示にするかどうかを示すブール型のパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` フレームワークは、;、ウィンドウを正常にデタッチ場合`FALSE`場合*pBar*は`NULL`かタブ付きペインに含まれていないペインを参照します。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、可能であればデタッチされたペインをフローティング状態です。 詳細については、次を参照してください。 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)です。  
  
##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName  
 有効またはアクティブなタブにラベルのテキストとキャプション テキストを同期するタブ付きペインの機能を無効にします。  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 `TRUE` タブ付きペインのキャプションをアクティブなタブのキャプションと同期するにはそれ以外の場合、`FALSE`です。  
  
##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray  
 内部のタブ オーダーを既定の状態に復元します。  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、初期状態にある Outlook バーを復元する際に、このメソッドが呼び出されます。  
  
##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID  
 ペインの ID によって識別されるペインを返します  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uBarID*  
 検索する、ペインの ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 見つかった場合、ウィンドウへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ペイン内のすべてのタブを比較しで指定された ID を持つ 1 つを返します、 *uBarID*パラメーター。  
  
##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber  
 タブ内にあるペインを返します。  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nTabNum*  
 取得するタブの 0 から始まるインデックスを指定します。  
  
 [in]*bGetWrappedBar*  
 `TRUE` ペイン自体ではなく、ペインの基になる (ラップ) のウィンドウに戻すそれ以外の場合`FALSE`です。 派生したウィンドウのみに限定される[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)です。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが見つかった場合、検索対象のウィンドウに、有効なポインターが返されます。それ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 指定されたタブ内に存在するウィンドウを取得するには、このメソッドを呼び出して、 *nTabNum*パラメーター。  
  
##  <a name="floattab"></a>  Cbasetabbedpane::floattab  
 現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]*pBar*  
 浮動小数点 ウィンドウへのポインター。  
  
 [in]*nTabID*  
 浮動小数点 タブの 0 から始まるインデックスを指定します。  
  
 [in]*dockMethod*  
 ペインをフローティングの作成に使用する方法を指定します。 詳細については、「解説」を参照してください。  
  
 [in]*bHide*  
 `TRUE` フローティングする前に、ウィンドウを非表示にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ペインをフローティング状態それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 切り離し可能なタブに現在あるペインをフローティングするには、このメソッドを呼び出します。  
  
 ウィンドウをプログラムからデタッチする場合は、指定`DM_SHOW`の*dockMethod*パラメーター。 ここで、フロート以前の同じ位置にペインをフローティングを指定する場合`DM_DBL_CLICK`として、 *dockMethod*パラメーター。  
  
##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder  
 ウィンドウでタブの既定の順序を返します。  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>戻り値  
 A`CArray`のウィンドウでタブの既定の順序を指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、初期状態にある Outlook バーがリセットされたときに、このメソッドを呼び出します。  
  
##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab  
 最初に表示されているタブへのポインターを取得します。  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iTabNum*  
 整数への参照。 このメソッドを書き込みます最初に表示されるタブの 0 から始まるインデックスまたはこのパラメーターを-1 に表示されなかった場合のタブが見つかった。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、最初に表示されているタブへのポインターそれ以外の場合、`NULL`です。  
  
##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize  
 下限のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*サイズ*  
 A`CSize`最小サイズで塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 最小ウィンドウ サイズの一貫した処理がアクティブな場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize))、*サイズ*はアクティブなタブのサイズが許容される最小で塗りつぶされます。それ以外の場合、*サイズ*の戻り値が格納[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)です。  
  
##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon  
 下限のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*サイズ*  
 A`CSize`最小サイズで塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 最小ウィンドウ サイズの一貫した処理がアクティブな場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize))、*サイズ*はアクティブなタブのサイズが許容される最小で塗りつぶされます。それ以外の場合、*サイズ*の戻り値が格納[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)です。  
  
##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList  
 タブ付きペインに含まれているペインの一覧を返します。  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*lst*  
 A`CObList`タブ付きペインに含まれているペインとを入力します。  
  
 [in]*pRTCFilter*  
 ない場合は`NULL`、返された一覧には、指定したランタイム クラスのペインのみが含まれています。  
  
##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea  
 上部と下部のタブ領域に外接する四角形を返します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rectTabAreaTop*  
 上のタブ領域の画面座標を受け取ります。  
  
 [out]*rectTabAreaBottom*  
 下のタブ領域の画面座標を受け取ります。  
  
### <a name="remarks"></a>Remarks  
 外接する四角形の上限と下限のタブ領域に、画面座標を判断するには、このメソッドを呼び出します。  
  
##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum  
 タブ ウィンドウでタブの数を返します。  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ付きペインにあるタブの数。  
  
##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow  
 基になる (ラッピングした) タブ ウィンドウを取得します。  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>戻り値  
 基になるタブ ウィンドウへのポインター。  
  
##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum  
 表示されるタブの数を返します。  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 大きいまたは 0 に等しいとなる、表示されるタブの数。  
  
### <a name="remarks"></a>Remarks  
 タブ付きペインに表示されるタブの数を決定するには、このメソッドを呼び出します。  
  
##  <a name="hasautohidemode"></a>  Cbasetabbedpane::hasautohidemode  
 タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウを隠すモードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 自動非表示モードが無効になっている場合は、タブ付きウィンドウのキャプションに固定 ボタンは表示されません。  
  
##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab  
 1 つのタブが表示されるだけの場合に、タブ付きウィンドウを非表示にするかどうかを判断します。  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 1 つだけに表示されるタブ; がある場合に、タブ ウィンドウが表示されない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 1 つだけのタブが開いているため、ウィンドウが表示されない場合は、タブ付きペインが正常に動作しているかどうかを確認するには、このメソッドを呼び出すことができます。  
  
##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane  
 タブ付きウィンドウからウィンドウを削除します。  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]*pBar*  
 タブ付きウィンドウから削除するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウはタブ付きウィンドウから正常に削除された場合、およびタブ付きウィンドウがまだ有効な場合は。 `FALSE` 最後のウィンドウがタブ付きペインと、タブ付きウィンドウから削除された場合は、破棄されようとしてです。 場合は、戻り値は`FALSE`、かどうかをタブ付きペインを使用しないでください。  
  
### <a name="remarks"></a>Remarks  
 指定されたウィンドウを削除するには、このメソッドを呼び出して、 *pBar*タブ付きウィンドウからのパラメーターです。  
  
##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy  
 タブ形式のコントロール バーを自動的に破棄されるかどうかを判断します。  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAutoDestroy*  
 `TRUE` タブ付きペインが動的に作成され、です。 有効期間を制御していない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 設定の自動破棄モードを`TRUE`タブ付きペインを動的に作成する場合、およびその有効期間を制御していない場合。 場合は自動破棄モードは`TRUE`、タブ付きペインは、フレームワークによって自動的に破棄します。  
  
##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab  
 タブの表示と非表示を切り替えます。  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 非表示 ウィンドウへのポインター。  
  
 [in]*bShow*  
 `TRUE` ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [in]*bDelay*  
 `TRUE` タブ レイアウトの調整を遅延するにはそれ以外の場合、`FALSE`です。  
  
 [in]*bActivate*  
 `TRUE` アクティブなタブ、タブを作成するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、タブが表示または非表示に正常にそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出すときにウィンドウを表示または非表示の値に応じて、 *bShow*パラメーター。 タブを非表示にして、基になるタブ ウィンドウの最後に表示されるタブは、タブ付きペインが表示されます。 存在しなかった以前タブ表示されているときに、タブを表示する場合は、タブ付きペインが表示されます。  
  
##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout  
 ウィンドウのレイアウト情報を再計算されます。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Remarks  
 ペインがフローティング状態の場合、このメソッドは、ミニフレームの現在のサイズには、ウィンドウのサイズを変更するのには、フレームワークを通知します。  
  
 場合は、ウィンドウがドッキングされている場合、このメソッドは何も行いません。  
  
##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode  
 タブ付きペインの切り離し可能なウィンドウの自動非表示モードを設定します。  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bMode*  
 `TRUE` 自動非表示モードを有効にするには`FALSE`標準ドッキング モードを有効にします。  
  
 [in]*場合*  
 作成するときに自動的に隠すウィンドウの配置を指定します。 使用可能な値の一覧は、次を参照してください。 [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)です。  
  
 [in][out]*pCurrAutoHideBar*  
 現在の自動的に隠すツールバーへのポインター。 指定できます`NULL`です。  
  
 [in]*bUseTimer*  
 ユーザーが自動的に隠すモードに、ウィンドウを切り替えるときに自動的に隠す効果を使用するか、すぐに、ウィンドウを非表示にするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 自動非表示モードに切り替えるときに作成される、自動的に隠すツールバーへのポインターまたは`NULL`ツールバーを作成していない場合。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ユーザーが自動非表示モードまたは標準ドッキング モードには、タブ付きペインを切り替えるには、暗証番号 (pin) ボタンを選択すると、このメソッドを呼び出します。  
  
 タブ付きペインに切り離し可能な各ウィンドウの自動非表示モードが設定されています。 切り離し不可能なペインは無視されます。 詳細については、次を参照してください。 [cmfcbasetabctrl::enabletabdetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)です。  
  
 タブ付きペインをプログラムで自動非表示モードに切り替えるには、このメソッドを呼び出します。 メイン フレーム ウィンドウに、ウィンドウをドッキングする必要があります ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider)への有効なポインターを返す必要があります、 [CPaneDivider](../../mfc/reference/cpanedivider-class.md))。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
