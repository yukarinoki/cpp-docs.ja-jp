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
ms.openlocfilehash: ce7c48263ed511545757c94d61552e6206e74a00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352857"
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
|`CBaseTabbedPane::CBaseTabbedPane`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウタブペイン::追加タブ](#addtab)|タブ付きペインに新しいタブを追加します。|
|[Cベースタブベドペイン:::デストロイの空のタブ付きペイン](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄できるかどうかを指定します。|
|[ウィンドウ::復元されたタブ情報を適用します。](#applyrestoredtabinfo)|レジストリから読み込まれるタブ設定をタブ付きペインに適用します。|
|[Cベースタブベドペイン::缶詰](#canfloat)|ペインをフロートできるかどうかを判断します。 [(CBasePane をオーバーライドします::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[ウィンドウセットタブペイン::缶詰キャプションテキストタブ名](#cansetcaptiontexttotabname)|タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを指定します。|
|[ウィンドウタブ付きペイン::変換タブ付きドキュメント](#converttotabbeddocument)|[(CDockable ペインをオーバーライドします::変換タブードドキュメント](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::Dエタッハペイン](#detachpane)|1 つ以上のドッキング可能ペインを MDI タブ付きドキュメントに変換します。|
|[ウィンドウタブペイン:::セットキャプションテキストを有効にする](#enablesetcaptiontexttotabname)|タブ付きペインで、アクティブなタブのラベル テキストとキャプション テキストを同期する機能を有効または無効にします。|
|[ウィンドウタブペイン:::フィルデフォルトタブオーダー配列](#filldefaulttabsorderarray)|内部タブ オーダーを既定の状態に戻します。|
|[ウィンドウタブペイン::検索バーバイタブ番号](#findbarbytabnumber)|タブが 0 から始まるタブ インデックスで識別される場合に、タブ内に存在するペインを返します。|
|||
|[ウィンドウタブペイン::検索ペインバイID](#findpanebyid)|ペイン ID で識別されるペインを返します。|
|[ウィンドウタブペイン::フロートタブ](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。|
|[ウィンドウタブペイン::デフォルトタブの並び替え](#getdefaulttabsorder)|ペイン内のタブの既定の順序を返します。|
|[タブ付きペイン::ゲットファーストビジタブ](#getfirstvisibletab)|最初に表示されたタブへのポインターを取得します。|
|[タブ付きペイン::GetMinSize](#getminsize)|ペインに許可される最小サイズを取得します。 (CPane をオーバーライド[します。::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[ウィンドウズタブペイン::ゲパネアイコン](#getpaneicon)|ペイン アイコンへのハンドルを返します。 [(CBasePane をオーバーライドします。::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[ウィンドウタブペイン::ゲットペインリスト](#getpanelist)|タブ付きペインに含まれるペインの一覧を返します。|
|[ウィンドウタブペイン::ゲットタブエリア](#gettabarea)|タブ領域の上と下の四角形を返します。|
|[ウィンドウタブペイン::ゲットタブ](#gettabsnum)|タブ ウィンドウ内のタブの数を返します。|
|[ウィンドウ::取得基礎ウィンドウ](#getunderlyingwindow)|基になる (ラップされた) タブ ウィンドウを取得します。|
|[ウィンドウタブペイン::表示されるタブ](#getvisibletabsnum)|表示されるタブの数を返します。|
|[ウィンドウタブペイン::ハズオートハイドモード](#hasautohidemode)|タブ付きペインを自動非表示モードに切り替えられるかどうかを指定します。|
|[CBaseタブ付きペイン::IsHideシングルタブ](#ishidesingletab)|タブが 1 つだけ表示されている場合にタブ付きペインを非表示にするかどうかを指定します。|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|シリアル化中に内部的に使用されます。|
|[CBaseTabbedペイン::レカルクレイアウト](#recalclayout)|ペインのレイアウト情報を再計算します。 (CPane をオーバーライド[します::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[ウィンドウタブ付きペイン::ウィンドウの削除](#removepane)|タブ付きペインからペインを削除します。|
|`CBaseTabbedPane::SaveSiblingBarIDs`|シリアル化中に内部的に使用されます。|
|`CBaseTabbedPane::Serialize`|[(CDockable ペインをオーバーライドします。:シリアライズ](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|シリアル化中に内部的に使用されます。|
|[CBaseタブ付きペイン::セットオートデストロイ](#setautodestroy)|タブ付きコントロール バーを自動的に破棄するかどうかを決定します。|
|[ウィンドウタブペイン::セットオートハイドモード](#setautohidemode)|ドッキング ペインの表示モードと自動非表示モードを切り替えます。 [(CDockable ペインをオーバーライドします。::自動ハイドモードを設定](../../mfc/reference/cdockablepane-class.md#setautohidemode)します。|
|[ウィンドウタブペイン::ショータブ](#showtab)|タブの表示/非表示を切り替えます。|

## <a name="remarks"></a>解説

このクラスは抽象クラスであり、インスタンス化できません。 このメソッドは、すべての種類のタブ付きペインに共通するサービスを実装します。

現在、ライブラリには、2 つの派生タブ付きペイン クラスが含まれています: [CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)と[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)。

オブジェクト`CBaseTabbedPane`は、[クラス](../../mfc/reference/cmfcbasetabctrl-class.md)オブジェクトへのポインターをラップします。 [次に、CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)は、タブ付きペインの子ウィンドウになります。

タブ付きペインを作成する方法の詳細については、「 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md) [、CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)、および[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。

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

## <a name="cbasetabbedpaneaddtab"></a><a name="addtab"></a>ウィンドウタブペイン::追加タブ

タブ付きペインに新しいタブを追加します。

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[イン、アウト]追加するペインへのポインター。 このメソッドを呼び出した後、このポインターが無効になる場合があります。 詳細については、「解説」を参照してください。

*ビジブル*<br/>
[in]タブを表示するには TRUE。それ以外の場合は FALSE。

*アクティブな状態を示します。*<br/>
[in]タブをアクティブなタブにするには TRUE。それ以外の場合は FALSE。

*b取り外し可能*<br/>
[in]タブを取り外し可能にするには TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ペインがタブとして正常に追加され、プロセス内で破棄されなかった場合は TRUE。 追加されるペインが type`CBaseTabbedPane`のオブジェクトの場合は FALSE。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

ペインをタブ付きペインの新しいタブとして追加します。 *pNewBar*が型`CBaseTabbedPane`のオブジェクトを指している場合、そのタブはすべてタブ付きペインにコピーされ *、pNewBar*は破棄されます。 したがって *、pNewBar*は無効なポインターになり、使用しないでください。

## <a name="cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>Cベースタブベドペイン:::デストロイの空のタブ付きペイン

空のタブ付きペインを破棄できるかどうかを指定します。

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>戻り値

空のタブ付きペインを破棄できる場合は TRUE。それ以外の場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

空のタブ付きペインを破棄できない場合、フレームワークは代わりにペインを非表示にします。

## <a name="cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>ウィンドウ::復元されたタブ情報を適用します。

レジストリからタブ設定を読み込み、タブ付きペインに適用します。

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>パラメーター

*タブインデックス*<br/>
[in]このパラメーターは、フレームワークによって内部的に使用されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリからドッキング状態情報を再読み込みするときに、フレームワークによって呼び出されます。 このメソッドは、タブ付きペインのタブ オーダーとタブ名に関する情報を取得します。

## <a name="cbasetabbedpanecanfloat"></a><a name="canfloat"></a>Cベースタブベドペイン::缶詰

タブ付きペインをフローティングできるかどうかを指定します。

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

ペインがフローティングできる場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>ウィンドウセットタブペイン::缶詰キャプションテキストタブ名

タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを指定します。

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>戻り値

タブ付きペインのキャプション テキストがアクティブなタブのテキストに設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、タブ付きペインのキャプションに表示されるテキストが、アクティブなタブのラベルと重複するかどうかを判断するために使用されます。この機能を有効または無効にするには[、CBaseTabbedPane を](#enablesetcaptiontexttotabname)呼び出します。

## <a name="cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>ウィンドウタブ付きペイン::変換タブ付きドキュメント

1 つ以上のドッキング可能ペインを MDI タブ付きドキュメントに変換します。

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*タブのみ*<br/>
[in]タブ付きペインを変換する場合は、TRUE を指定してアクティブなタブのみを変換します。

## <a name="cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::Dエタッハペイン

タブ付きペインからペインを切り離します。

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]デタッチするペインへのポインター。

*bHide*<br/>
[in]デタッチされた後にフレームワークがペインを非表示にするかどうかを指定するブール値パラメーター。

### <a name="return-value"></a>戻り値

フレームワークが正常にペインをデタッチする場合は TRUE。false*を指定すると、pBar*が NULL であるか、タブ付きペインにないペインを参照します。

### <a name="remarks"></a>解説

可能な場合、フレームワークはデタッチされたペインを浮動させます。 詳細については[、「CBasePane::CanFloat」](../../mfc/reference/cbasepane-class.md#canfloat)を参照してください。

## <a name="cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>ウィンドウタブペイン:::セットキャプションテキストを有効にする

タブ付きペインで、アクティブなタブのラベル テキストとキャプション テキストを同期する機能を有効または無効にします。

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]タブ付きペインキャプションをアクティブなタブキャプションと同期させる場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>ウィンドウタブペイン:::フィルデフォルトタブオーダー配列

内部タブ オーダーを既定の状態に戻します。

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>解説

このメソッドは、フレームワークが Outlook バーを初期状態に復元するときに呼び出されます。

## <a name="cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>ウィンドウタブペイン::検索ペインバイID

ペイン ID で識別されるペインを返します。

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>パラメーター

*ユーバーID*<br/>
[in]検索するペインの ID を指定します。

### <a name="return-value"></a>戻り値

ペインが見つかった場合はペインへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、ペイン内のすべてのタブを比較し *、uBarID*パラメーターで指定された ID を持つタブを返します。

## <a name="cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>ウィンドウタブペイン::検索バーバイタブ番号

タブ内に存在するペインを返します。

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>パラメーター

*nタブ番号*<br/>
[in]取得するタブの 0 から始まるインデックスを指定します。

*ビゲラッピングバー*<br/>
[in]ペイン自体の代わりにペインの基になる (ラップされた) ウィンドウを返す場合は TRUE。それ以外の場合は FALSE。 これは[、CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)から派生したペインにのみ適用されます。

### <a name="return-value"></a>戻り値

ペインが見つかった場合は、検索対象のペインへの有効なポインタが返されます。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*nTabNum*パラメーターで指定されたタブにあるペインを取得します。

## <a name="cbasetabbedpanefloattab"></a><a name="floattab"></a>ウィンドウタブペイン::フロートタブ

現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[イン、アウト]フローティングするペインへのポインター。

*タブID*<br/>
[in]浮動するタブの 0 から始まるインデックスを指定します。

*ドックメソッド*<br/>
[in]ペインをフロートにする方法を指定します。 詳細については、「解説」を参照してください。

*bHide*<br/>
[in]フローティングの前にペインを非表示にする場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ペインが浮動表示された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

現在取り外し可能なタブに存在するペインをフローティングします。

プログラムによってペインをデタッチする場合は *、dockMethod*パラメーターにDM_SHOWを指定します。 以前にフローティングした位置と同じ位置にペインをフローティングする場合は *、DM_DBL_CLICKを dockMethod*パラメーターとして指定します。

## <a name="cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>ウィンドウタブペイン::デフォルトタブの並び替え

ペイン内のタブの既定の順序を返します。

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>戻り値

ペイン`CArray`内のタブの既定の順序を指定するオブジェクト。

### <a name="remarks"></a>解説

Outlook バーが初期状態にリセットされると、フレームワークはこのメソッドを呼び出します。

## <a name="cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>タブ付きペイン::ゲットファーストビジタブ

最初に表示されたタブへのポインターを取得します。

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>パラメーター

*アイタブバーナム*<br/>
[in]整数への参照。 このメソッドは、最初に表示されたタブの 0 から始まるインデックスをこのパラメーターに書き込みます。

### <a name="return-value"></a>戻り値

正常に実行された場合は、最初に表示されたタブへのポインター。それ以外の場合は NULL。

## <a name="cbasetabbedpanegetminsize"></a><a name="getminsize"></a>タブ付きペイン::GetMinSize

ペインに許可される最小サイズを取得します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[アウト]許可`CSize`される最小サイズで埋め込まれるオブジェクト。

### <a name="remarks"></a>解説

最小ペイン サイズの一貫した処理がアクティブな場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)) 、*サイズ*はアクティブなタブの最小許容*size*サイズで埋[められます。](../../mfc/reference/cpane-class.md#getminsize)

## <a name="cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>ウィンドウズタブペイン::ゲパネアイコン

ペインに許可される最小サイズを取得します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[アウト]許可`CSize`される最小サイズで埋め込まれるオブジェクト。

### <a name="remarks"></a>解説

最小ペイン サイズの一貫した処理がアクティブな場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)) 、*サイズ*はアクティブなタブの最小許容*size*サイズで埋[められます。](../../mfc/reference/cpane-class.md#getminsize)

## <a name="cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>ウィンドウタブペイン::ゲットペインリスト

タブ付きペインに含まれるペインの一覧を返します。

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
[アウト]タブ`CObList`付きペインに含まれるペインで塗りつぶされる A。

*フィルター*<br/>
[in]NULL でない場合、返されるリストには、指定されたランタイム クラスのペインのみが含まれます。

## <a name="cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>ウィンドウタブペイン::ゲットタブエリア

タブ領域の上と下の四角形を返します。

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>パラメーター

*レクトタブエリアトップ*<br/>
[アウト]上部タブ領域の画面座標を受け取ります。

*タブエリア下部*<br/>
[アウト]下部タブ領域の画面座標を受け取ります。

### <a name="remarks"></a>解説

上下のタブ領域に対して、画面座標で外接する四角形を決定します。

## <a name="cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>ウィンドウタブペイン::ゲットタブ

タブ ウィンドウ内のタブの数を返します。

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>戻り値

タブ付きペインのタブ数。

## <a name="cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>ウィンドウ::取得基礎ウィンドウ

基になる (ラップされた) タブ ウィンドウを取得します。

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>戻り値

基になるタブ ウィンドウへのポインター。

## <a name="cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>ウィンドウタブペイン::表示されるタブ

表示されるタブの数を返します。

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>戻り値

表示されるタブの数 (0 以上)。

### <a name="remarks"></a>解説

タブ付きペインに表示されるタブの数を調べます。

## <a name="cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>ウィンドウタブペイン::ハズオートハイドモード

タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

ペインを自動非表示モードに切り替えることができる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

自動非表示モードが無効になっている場合、タブ付きペインのキャプションにピン ボタンは表示されません。

## <a name="cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseタブ付きペイン::IsHideシングルタブ

タブが 1 つだけ表示されている場合にタブ付きペインを非表示にするかどうかを指定します。

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>戻り値

表示されるタブが 1 つしかない場合にタブ ウィンドウが表示されない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

1 つのタブのみが開いているためにペインが表示されない場合は、このメソッドを呼び出して、タブ付きペインが正しく機能しているかどうかを確認できます。

## <a name="cbasetabbedpaneremovepane"></a><a name="removepane"></a>ウィンドウタブ付きペイン::ウィンドウの削除

タブ付きペインからペインを削除します。

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[イン、アウト]タブ付きペインから削除するペインへのポインター。

### <a name="return-value"></a>戻り値

ペインがタブ付きペインから正常に削除され、タブ付きペインがまだ有効な場合は TRUE。 最後のペインがタブ付きペインから削除され、タブ付きペインが破棄されようとしている場合は FALSE。 戻り値が FALSE の場合は、タブ付きペインを使用しないでください。

### <a name="remarks"></a>解説

このメソッドを呼び出して *、pBar*パラメーターで指定されたペインをタブ付きペインから削除します。

## <a name="cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseタブ付きペイン::セットオートデストロイ

タブ付きコントロール バーを自動的に破棄するかどうかを決定します。

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*b自動破壊*<br/>
[in]タブ付きペインが動的に作成され、その有効期間を制御しない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

タブ付きペインを動的に作成し、その有効期間を制御しない場合は、自動破棄モードを TRUE に設定します。 自動破棄モードが TRUE の場合、タブ付きペインはフレームワークによって自動的に破棄されます。

## <a name="cbasetabbedpaneshowtab"></a><a name="showtab"></a>ウィンドウタブペイン::ショータブ

タブの表示/非表示を切り替えます。

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]表示または非表示にするペインへのポインター。

*bショー*<br/>
[in]ペインを表示する場合は TRUE。FALSE を指定すると、ウィンドウが非表示になります。

*bディレイ*<br/>
[in]タブ レイアウトの調整を遅らせる場合は TRUE。それ以外の場合は FALSE。

*bアクティブ化*<br/>
[in]タブをアクティブなタブにするには TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

タブが正常に表示または非表示にされた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを呼び出すと *、bShow*パラメーターの値に応じて、ペインが表示または非表示になります。 タブを非表示にし、そのタブが基になるタブ ウィンドウの最後に表示されているタブである場合、タブ付きペインは非表示になります。 以前に表示されていたタブがないときにタブを表示すると、タブ付きペインが表示されます。

## <a name="cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedペイン::レカルクレイアウト

ペインのレイアウト情報を再計算します。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>解説

ペインがフローティング状態の場合、このメソッドは、ペインのサイズをミニフレームの現在のサイズに変更するようフレームワークに通知します。

ペインがドッキングされている場合、このメソッドは何も実行しません。

## <a name="cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>ウィンドウタブペイン::セットオートハイドモード

タブ付きペインのデタッチ可能なペインの自動非表示モードを設定します。

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>パラメーター

*bモード*<br/>
[in]自動非表示モードを有効にするには TRUE。通常のドッキング モードを有効にするには、FALSE を指定します。

*dw配置*<br/>
[in]作成する自動非表示ペインの配置を指定します。 使用可能な値の一覧については[、「CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)」を参照してください。

*を使用します。*<br/>
[イン、アウト]現在の自動非表示ツール バーへのポインター。 NULL にすることができます。

*タイマーを使用します。*<br/>
[in]ユーザーがペインを自動非表示モードに切り替えたときに自動非表示効果を使用するか、ウィンドウをすぐに非表示にするかを指定します。

### <a name="return-value"></a>戻り値

自動非表示モードに切り替えたときに作成される自動非表示ツール バーへのポインター。

### <a name="remarks"></a>解説

ユーザーがピン ボタンを選択してタブ付きペインを自動非表示モードまたは通常のドッキング モードに切り替えると、フレームワークは、このメソッドを呼び出します。

タブ付きペインの各デタッチ可能なペインに対して、自動非表示モードが設定されます。 デタッチできないペインは無視されます。 詳細については[、「CMFC ベースタブCtrl::有効タブデタッチ](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)」を参照してください。

プログラムによってタブ付きペインを自動非表示モードに切り替えます。 ペインはメイン フレーム ウィンドウにドッキングする必要があります ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider)は[CPaneDivider](../../mfc/reference/cpanedivider-class.md)への有効なポインターを返す必要があります ) 。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
