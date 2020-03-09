---
title: CBaseTabbedPane クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: d7ffaa7274a8ed12944cdbc5dcbbdcb8fd3fd2b9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883669"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane クラス

[CDockablePane Class](../../mfc/reference/cdockablepane-class.md) の機能を拡張して、タブ付きウィンドウの作成をサポートします。

## <a name="syntax"></a>構文

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CBaseTabbedPane:: AddTab](#addtab)|タブ付きペインに新しいタブを追加します。|
|[CBaseTabbedPane:: AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄できるかどうかを指定します。|
|[CBaseTabbedPane:: ApplyRestoredTabInfo](#applyrestoredtabinfo)|レジストリから読み込まれたタブ設定をタブ付きペインに適用します。|
|[CBaseTabbedPane:: CanFloat](#canfloat)|ペインをフローティングできるかどうかを判断します。 ( [Cbasepane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)をオーバーライドします)。|
|[CBaseTabbedPane:: CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを決定します。|
|[CBaseTabbedPane:: ConvertToTabbedDocument](#converttotabbeddocument)|( [CDockablePane:: ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument)をオーバーライドします。)|
|[CBaseTabbedPane::D etachPane](#detachpane)|1つ以上のドッキング可能なペインを MDI タブ付きドキュメントに変換します。|
|[CBaseTabbedPane:: EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|タブ付きペインで、アクティブなタブのラベルテキストとキャプションテキストを同期する機能を有効または無効にします。|
|[CBaseTabbedPane:: FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|内部タブオーダーを既定の状態に復元します。|
|[CBaseTabbedPane:: FindBarByTabNumber](#findbarbytabnumber)|0から始まるタブインデックスによってタブが識別された場合に、タブに存在するペインを返します。|
|||
|[CBaseTabbedPane:: FindPaneByID](#findpanebyid)|ペイン ID で識別されるペインを返します。|
|[CBaseTabbedPane:: FloatTab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。|
|[CBaseTabbedPane:: GetDefaultTabsOrder](#getdefaulttabsorder)|ペイン内のタブの既定の順序を返します。|
|[CBaseTabbedPane:: GetFirstVisibleTab](#getfirstvisibletab)|最初に表示されたタブへのポインターを取得します。|
|[CBaseTabbedPane:: GetMinSize](#getminsize)|ペインで許容される最小サイズを取得します。 ( [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)をオーバーライドします。)|
|[CBaseTabbedPane:: Get区画アイコン](#getpaneicon)|ペインアイコンへのハンドルを返します。 ( [Cbasepane:: Getpane アイコン](../../mfc/reference/cbasepane-class.md#getpaneicon)をオーバーライドします)。|
|[CBaseTabbedPane:: Get List](#getpanelist)|タブ付きペインに含まれるペインの一覧を返します。|
|[CBaseTabbedPane:: GetTabArea](#gettabarea)|上部および下部のタブ領域の外接する四角形を返します。|
|[CBaseTabbedPane:: GetTabsNum](#gettabsnum)|タブウィンドウ内のタブの数を返します。|
|[CBaseTabbedPane:: GetUnderlyingWindow](#getunderlyingwindow)|基になる (ラップされた) タブウィンドウを取得します。|
|[CBaseTabbedPane:: GetVisibleTabsNum](#getvisibletabsnum)|表示されるタブの数を返します。|
|[CBaseTabbedPane:: HasAutoHideMode](#hasautohidemode)|タブ付きペインを自動非表示モードに切り替えることができるかどうかを決定します。|
|[CBaseTabbedPane:: i Desingletab](#ishidesingletab)|1つのタブのみが表示されている場合に、タブ付きペインを非表示にするかどうかを指定します。|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|シリアル化中に内部的に使用されます。|
|[CBaseTabbedPane:: RecalcLayout](#recalclayout)|ペインのレイアウト情報を再計算します。 ( [CPane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout)をオーバーライドします。)|
|[CBaseTabbedPane:: RemovePane](#removepane)|タブ付きペインからペインを削除します。|
|`CBaseTabbedPane::SaveSiblingBarIDs`|シリアル化中に内部的に使用されます。|
|`CBaseTabbedPane::Serialize`|( [CDockablePane:: Serialize](cdockablepane-class.md)をオーバーライドします)。|
|`CBaseTabbedPane::SerializeTabWindow`|シリアル化中に内部的に使用されます。|
|[CBaseTabbedPane:: SetAutoDestroy](#setautodestroy)|タブ付きコントロールバーを自動的に破棄するかどうかを決定します。|
|[CBaseTabbedPane:: SetAutoHideMode](#setautohidemode)|ドッキングペインの表示と非表示を切り替えます。 ( [CDockablePane:: SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode)をオーバーライドします)。|
|[CBaseTabbedPane:: ShowTab](#showtab)|タブの表示と非表示を切り替えます。|

## <a name="remarks"></a>解説

このクラスは抽象クラスであり、インスタンス化することはできません。 すべての種類のタブ付きペインに共通のサービスを実装します。

現在、ライブラリには、 [CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)と[cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)の2つの派生したタブ付きペインクラスが含まれています。

`CBaseTabbedPane` オブジェクトは、 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)オブジェクトへのポインターをラップします。 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)は、タブ付きペインの子ウィンドウになります。

タブ付きペインを作成する方法の詳細については、「 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)」、「 [CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)」、および「 [cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxBaseTabbedPane

##  <a name="addtab"></a>CBaseTabbedPane:: AddTab

タブ付きペインに新しいタブを追加します。

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>パラメーター

*pNewBar*<br/>
[入力、出力]追加するペインへのポインター。 このポインターは、このメソッドを呼び出した後に無効になる場合があります。 詳細については、「解説」を参照してください。

*bVisible*<br/>
からタブが表示されるようにする場合は TRUE。それ以外の場合は FALSE。

*bSetActive*<br/>
からタブをアクティブなタブにする場合は TRUE。それ以外の場合は FALSE。

*bDetachable 可能*<br/>
からタブを切り離し可能にする場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ウィンドウがタブとして正常に追加され、プロセスで破棄されなかった場合は TRUE。 追加するペインが `CBaseTabbedPane`型のオブジェクトの場合は FALSE。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

タブ付きペインに新しいタブとしてペインを追加するには、このメソッドを呼び出します。 *Pnewbar*が `CBaseTabbedPane`型のオブジェクトを指している場合は、すべてのタブがタブ付きペインにコピーされ、 *pnewbar*が破棄されます。 したがって、 *Pnewbar*は無効なポインターになるため、使用しないでください。

##  <a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane:: AllowDestroyEmptyTabbedPane

空のタブ付きペインを破棄できるかどうかを指定します。

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>戻り値

空のタブ付きペインを破棄できる場合は TRUE。それ以外の場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

空のタブ付きペインを破棄することが許可されていない場合は、フレームワークによって代わりにペインが非表示になります。

##  <a name="applyrestoredtabinfo"></a>CBaseTabbedPane:: ApplyRestoredTabInfo

レジストリからタブ設定を読み込み、タブ付きペインに適用します。

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>パラメーター

*bUseTabIndexes*<br/>
からこのパラメーターは、フレームワークによって内部的に使用されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリからドッキング状態情報を再読み込みするときに、フレームワークによって呼び出されます。 メソッドは、タブ付きペインのタブオーダーとタブ名に関する情報を取得します。

##  <a name="canfloat"></a>CBaseTabbedPane:: CanFloat

タブ付きペインをフローティングできるかどうかを指定します。

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

ペインをフローティングできる場合は TRUE。それ以外の場合は FALSE。

##  <a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane:: CanSetCaptionTextToTabName

タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを決定します。

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>戻り値

タブ付きペインのキャプションテキストがアクティブなタブのテキストに設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メソッドは、タブ付きペインのキャプションに表示されるテキストが、アクティブなタブのラベルと重複するかどうかを判断するために使用されます。この機能を有効または無効にするには、 [CBaseTabbedPane:: EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)を呼び出します。

##  <a name="converttotabbeddocument"></a>CBaseTabbedPane:: ConvertToTabbedDocument

1つ以上のドッキング可能なペインを MDI タブ付きドキュメントに変換します。

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*bActiveTabOnly*<br/>
からタブ付きペインを変換する場合は、[TRUE] を指定して、アクティブなタブのみを変換します。ペイン内のすべてのタブを変換するには、FALSE を指定します。

##  <a name="detachpane"></a>CBaseTabbedPane::D etachPane

ペインをタブ付きペインから切り離します。

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
からデタッチするペインへのポインター。

*bHide*<br/>
からデタッチされた後、フレームワークがペインを非表示にするかどうかを指定するブール型パラメーターです。

### <a name="return-value"></a>戻り値

フレームワークがペインを正常にデタッチした場合は TRUE。*Pbar*が NULL であるか、またはタブ付きペインにないペインを参照している場合は FALSE。

### <a name="remarks"></a>解説

可能であれば、フレームワークはデタッチされたペインをフローティングします。 詳細については、「 [Cbasepane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)」を参照してください。

##  <a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane:: EnableSetCaptionTextToTabName

タブ付きペインで、アクティブなタブのラベルテキストとキャプションテキストを同期する機能を有効または無効にします。

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からタブ付きペインのキャプションとアクティブなタブのキャプションを同期する場合は TRUE。それ以外の場合は FALSE。

##  <a name="filldefaulttabsorderarray"></a>CBaseTabbedPane:: FillDefaultTabsOrderArray

内部タブオーダーを既定の状態に復元します。

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>解説

このメソッドは、フレームワークが Outlook バーを初期状態に復元するときに呼び出されます。

##  <a name="findpanebyid"></a>CBaseTabbedPane:: FindPaneByID

ペイン ID で識別されるペインを返します。

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>パラメーター

*uBarID*<br/>
から検索するペインの ID を指定します。

### <a name="return-value"></a>戻り値

見つかった場合は、ペインへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、ペイン内のすべてのタブを比較し、 *Ubarid*パラメーターによって指定された id を持つものを返します。

##  <a name="findbarbytabnumber"></a>CBaseTabbedPane:: FindBarByTabNumber

タブに存在するペインを返します。

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>パラメーター

*nTabNum*<br/>
から取得するタブの0から始まるインデックスを指定します。

*bGetWrappedBar*<br/>
からペイン自体ではなく、ペインの基になる (ラップされた) ウィンドウを返す場合は TRUE。それ以外の場合は FALSE。 これは、 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)から派生したペインにのみ適用されます。

### <a name="return-value"></a>戻り値

ペインが見つかった場合は、検索対象のペインへの有効なポインターが返されます。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*NTabNum*パラメーターで指定したタブにあるペインを取得するには、このメソッドを呼び出します。

##  <a name="floattab"></a>CBaseTabbedPane:: FloatTab

現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[入力、出力]フローティングするペインへのポインター。

*nTabID*<br/>
からフローティングするタブの0から始まるインデックスを指定します。

*dockMethod*<br/>
からペインをフローティングするために使用するメソッドを指定します。 詳細については、「解説」を参照してください。

*bHide*<br/>
からフローティングの前にペインを非表示にする場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ペインがフローティングになった場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

切り離し可能なタブに現在存在するペインをフローティングするには、このメソッドを呼び出します。

ウィンドウをプログラムによってデタッチする場合は、 *dockMethod*パラメーターに DM_SHOW を指定します。 ペインを前と同じ位置にフローティングする場合は、 *dockMethod*パラメーターとして DM_DBL_CLICK を指定します。

##  <a name="getdefaulttabsorder"></a>CBaseTabbedPane:: GetDefaultTabsOrder

ペイン内のタブの既定の順序を返します。

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>戻り値

ペイン内のタブの既定の順序を指定する `CArray` オブジェクト。

### <a name="remarks"></a>解説

Outlook バーが初期状態にリセットされると、フレームワークはこのメソッドを呼び出します。

##  <a name="getfirstvisibletab"></a>CBaseTabbedPane:: GetFirstVisibleTab

最初に表示されたタブへのポインターを取得します。

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>パラメーター

*iTabNum*<br/>
から整数への参照。 このメソッドは、最初に表示されたタブの0から始まるインデックスをこのパラメーターに書き込みます。表示されているタブが見つからない場合は-1 を書き込みます。

### <a name="return-value"></a>戻り値

成功した場合は、最初に表示されたタブへのポインター。それ以外の場合は NULL。

##  <a name="getminsize"></a>CBaseTabbedPane:: GetMinSize

ペインで許容される最小サイズを取得します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*size*<br/>
入出力許容される最小サイズを格納する `CSize` オブジェクト。

### <a name="remarks"></a>解説

最小ペインサイズの一貫した処理がアクティブ ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)) である場合、*サイズ*にはアクティブなタブで許容される最小サイズが設定されます。それ以外の場合、*サイズ*には[CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)の戻り値が格納されます。

##  <a name="getpaneicon"></a>CBaseTabbedPane:: Get区画アイコン

ペインで許容される最小サイズを取得します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*size*<br/>
入出力許容される最小サイズを格納する `CSize` オブジェクト。

### <a name="remarks"></a>解説

最小ペインサイズの一貫した処理がアクティブ ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)) である場合、*サイズ*にはアクティブなタブで許容される最小サイズが設定されます。それ以外の場合、*サイズ*には[CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)の戻り値が格納されます。

##  <a name="getpanelist"></a>CBaseTabbedPane:: Get List

タブ付きペインに含まれるペインの一覧を返します。

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
入出力タブ付きペインに格納されているペインを格納する `CObList`。

*pRTCFilter*<br/>
からNULL でない場合、返される一覧には、指定されたランタイムクラスのペインだけが含まれます。

##  <a name="gettabarea"></a>CBaseTabbedPane:: GetTabArea

上部および下部のタブ領域の外接する四角形を返します。

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>パラメーター

*rectTabAreaTop*<br/>
入出力上部のタブ領域の画面座標を受け取ります。

*rectTabAreaBottom*<br/>
入出力下部のタブ領域の画面座標を受け取ります。

### <a name="remarks"></a>解説

このメソッドを呼び出して、上部および下部のタブ領域の境界四角形を画面座標で確認します。

##  <a name="gettabsnum"></a>CBaseTabbedPane:: GetTabsNum

タブウィンドウ内のタブの数を返します。

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>戻り値

タブ付きペイン内のタブの数。

##  <a name="getunderlyingwindow"></a>CBaseTabbedPane:: GetUnderlyingWindow

基になる (ラップされた) タブウィンドウを取得します。

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>戻り値

基になるタブウィンドウへのポインター。

##  <a name="getvisibletabsnum"></a>CBaseTabbedPane:: GetVisibleTabsNum

表示されるタブの数を返します。

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>戻り値

0以上の、表示されるタブの数。

### <a name="remarks"></a>解説

このメソッドを呼び出して、タブ付きペインに表示されるタブの数を決定します。

##  <a name="hasautohidemode"></a>CBaseTabbedPane:: HasAutoHideMode

タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

ペインを自動非表示モードに切り替えることができる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[自動的に隠す] モードが無効になっている場合は、タブ付きペインのキャプションに [pin] ボタンが表示されません。

##  <a name="ishidesingletab"></a>CBaseTabbedPane:: i Desingletab

1つのタブのみが表示されている場合に、タブ付きペインを非表示にするかどうかを指定します。

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>戻り値

タブウィンドウが1つしか表示されていない場合に表示されない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

開いているタブが1つだけであるためにペインが表示されない場合は、このメソッドを呼び出して、タブ付きペインが正常に動作しているかどうかを確認できます。

##  <a name="removepane"></a>CBaseTabbedPane:: RemovePane

タブ付きペインからペインを削除します。

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[入力、出力]タブ付きペインから削除するペインへのポインター。

### <a name="return-value"></a>戻り値

ペインがタブ付きペインから正常に削除された場合、およびタブ付きペインがまだ有効である場合は TRUE。 タブ付きペインから最後のペインが削除され、タブ付きウィンドウが破棄されようとしている場合は FALSE。 戻り値が FALSE の場合は、タブ付きペインを使用しないでください。

### <a name="remarks"></a>解説

*Pbar*パラメーターによって指定されたペインをタブ付きペインから削除するには、このメソッドを呼び出します。

##  <a name="setautodestroy"></a>CBaseTabbedPane:: SetAutoDestroy

タブ付きコントロールバーを自動的に破棄するかどうかを決定します。

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*bAutoDestroy*<br/>
からタブ付きウィンドウが動的に作成され、その有効期間を制御していない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

タブ付きペインを動的に作成し、その有効期間を制御していない場合は、自動破棄モードを TRUE に設定します。 自動破棄モードが TRUE の場合、タブ付きペインはフレームワークによって自動的に破棄されます。

##  <a name="showtab"></a>CBaseTabbedPane:: ShowTab

タブの表示と非表示を切り替えます。

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
から表示または非表示にするペインへのポインター。

*bShow*<br/>
からペインを表示する場合は TRUE。ペインを非表示にする場合は FALSE。

*bDelay*<br/>
からタブレイアウトの調整を遅らせる場合は TRUE。それ以外の場合は FALSE。

*bActivate*<br/>
からタブをアクティブなタブにする場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

タブが正常に表示または非表示にされた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを呼び出すと、 *bShow*パラメーターの値に応じて、ペインが表示または非表示になります。 タブを非表示にし、基になるタブウィンドウの最後に表示されるタブである場合、タブ付きペインは非表示になります。 以前にタブが表示されていないときにタブを表示すると、タブ付きのペインが表示されます。

##  <a name="recalclayout"></a>CBaseTabbedPane:: RecalcLayout

ペインのレイアウト情報を再計算します。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>解説

ペインがフローティングの場合、このメソッドはペインのサイズをミニフレームの現在のサイズに変更するようにフレームワークに通知します。

ペインがドッキングされている場合、このメソッドは何も行いません。

##  <a name="setautohidemode"></a>CBaseTabbedPane:: SetAutoHideMode

タブ付きペインで、切り離し可能なウィンドウの自動非表示モードを設定します。

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>パラメーター

*bMode*<br/>
から自動非表示モードを有効にする場合は TRUE。通常のドッキングモードを有効にする場合は FALSE。

*dwAlignment*<br/>
から作成する自動的に隠すウィンドウの配置を指定します。 使用可能な値の一覧については、「 [CPane:: MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)」を参照してください。

*pCurrAutoHideBar*<br/>
[入力、出力]現在の自動的に隠すツールバーへのポインター。 NULL にすることができます。

*bUseTimer*<br/>
からユーザーがペインを自動的に隠すモードに切り替えたとき、またはウィンドウをすぐに非表示にするときに、自動的に隠す効果を使用するかどうかを指定します。

### <a name="return-value"></a>戻り値

自動非表示モードに切り替えるときに作成される自動的に隠すツールバーへのポインター。または、ツールバーが作成されていない場合は NULL。

### <a name="remarks"></a>解説

フレームワークは、ユーザーが [ピン留め] ボタンをクリックして、タブ付きペインを自動非表示モードまたは標準ドッキングモードに切り替えると、このメソッドを呼び出します。

自動非表示モードは、タブ付きペインの各切り離し可能なペインに対して設定されます。 非切り離し可能なペインは無視されます。 詳細については、「 [CMFCBaseTabCtrl:: EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)」を参照してください。

このメソッドを呼び出して、タブ付きペインをプログラムによって自動的に隠すモードに切り替えます。 ウィンドウはメインフレームウィンドウにドッキングする必要があります ( [CDockablePane:: GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider)は、 [Cpanedivider](../../mfc/reference/cpanedivider-class.md)への有効なポインターを返す必要があります)。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
