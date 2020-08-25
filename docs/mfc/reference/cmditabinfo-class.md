---
title: CMDITabInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: 8e4053bf16672d693adc104c9e88bb46a67ba7dd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845914"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo クラス

クラスは、 `CMDITabInfo` [CMDIFrameWndEx:: EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) メソッドにパラメーターを渡すために使用されます。 MDI タブ付きグループの動作を制御するために、このクラスのメンバーを設定します。

## <a name="syntax"></a>構文

```
class CMDITabInfo
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMDITabInfo:: Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMDITabInfo:: m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|アクティブなタブのラベルに [ **閉じる** ] ボタンを表示するかどうかを指定します。|
|[CMDITabInfo:: m_bAutoColor](#m_bautocolor)|MDI タブに色を設定するかどうかを指定します。|
|[CMDITabInfo:: m_bDocumentMenu](#m_bdocumentmenu)|開いているドキュメントの一覧を表示するポップアップメニューをタブグループに表示するか、スクロールボタンを表示するかを指定します。|
|[CMDITabInfo:: m_bEnableTabSwap](#m_benabletabswap)|ユーザーがタブの位置をドラッグして入れ替えることができるかどうかを指定します。|
|[CMDITabInfo:: m_bFlatFrame](#m_bflatframe)|タブにフラットフレームがあるかどうかを指定します。|
|[CMDITabInfo:: m_bTabCloseButton](#m_btabclosebutton)|各タブラベルに [ **閉じる** ] ボタンを表示するかどうかを指定します。|
|[CMDITabInfo:: m_bTabCustomTooltips](#m_btabcustomtooltips)|カスタムツールヒントを有効にするかどうかを指定します。|
|[CMDITabInfo:: m_bTabIcons](#m_btabicons)|MDI タブにアイコンを表示するかどうかを指定します。|
|[CMDITabInfo:: m_nTabBorderSize](#m_ntabbordersize)|各タブウィンドウの境界線のサイズを指定します。|
|[CMDITabInfo:: m_style](#m_style)|タブラベルのスタイルを指定します。|
|[CMDITabInfo:: m_tabLocation](#m_tablocation)|タブラベルをページの上部または下部に配置するかどうかを指定します。|

## <a name="remarks"></a>解説

このクラスは、フレームワークによって作成される MDI タブグループのパラメーターを指定します。

## <a name="example"></a>例

クラスのさまざまなメンバー変数の値を設定する方法を次の例に示し `CMDITabInfo` ます。

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmdiclientareawnd

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a> CMDITabInfo:: m_bActiveTabCloseButton;

アクティブなタブのラベルに [ **閉じる** ] ボタンを表示するかどうかを指定します。

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>解説

TRUE の場合、アクティブなタブのラベルには [ **閉じる** ] ボタンが表示されます。 タブ領域の右上隅から [ **閉じる** ] ボタンが削除されます。 それ以外の場合、アクティブなタブのラベルには [ **閉じる** ] ボタンが表示されません。 タブ領域の右上隅に [ **閉じる** ] ボタンが表示されます。

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a> CMDITabInfo:: m_bAutoColor

各 MDI タブに独自の色を設定するかどうかを指定します。

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブには独自の色が設定されます。 一連の色は、MFC ライブラリによって管理されます。 それ以外の場合は、タブが白で表示されます。 既定値は FALSE です。

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a> CMDITabInfo:: m_bDocumentMenu

タブ領域の右端に開いているドキュメントの一覧を表示するポップアップメニューを各タブに表示するかどうかを指定します。

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブウィンドウには、タブ領域の右端に開いているドキュメントの一覧を示すポップアップメニューが表示されます。それ以外の場合、タブウィンドウにはタブ領域の右端にスクロールボタンが表示されます。 既定値は FALSE です。

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a> CMDITabInfo:: m_bEnableTabSwap

ユーザーがタブの位置をドラッグして入れ替えることができるかどうかを指定します。

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>解説

TRUE の場合、ユーザーはタブをドラッグしてタブの位置を変更できます。 それ以外の場合、ユーザーはタブの位置を変更できません。 既定値は TRUE です。

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a> CMDITabInfo:: m_bFlatFrame

各タブウィンドウにフラットなフレームを表示するかどうかを指定します。

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a> CMDITabInfo:: m_bTabCloseButton

各タブウィンドウに [ **閉じる** ] ボタンを表示するかどうかを指定します。

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブウィンドウにタブの右端に [ **閉じる** ] ボタンが表示されます。それ以外の場合は、[ **閉じる** ] ボタンが表示されません。 既定値は TRUE です。

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a> CMDITabInfo:: m_bTabCustomTooltips

タブにツールヒントを表示するかどうかを指定します。

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>解説

TRUE の場合、アプリケーションは AFX_WM_ON_GET_TAB_TOOLTIP メッセージをメインフレームに送信します。 このメッセージは、ON_REGISTERED_MESSAGE マクロを使用して処理できます。

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a> CMDITabInfo:: m_bTabIcons

MDI タブにアイコンを表示するかどうかを指定します。

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>解説

TRUE の場合、各 MDI タブにアイコンが表示されます。それ以外の場合、アイコンはタブに表示されません。 既定値は FALSE です。

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a> CMDITabInfo:: m_nTabBorderSize

各タブウィンドウの境界線のサイズをピクセル単位で指定します。

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>解説

[Cmfcvisualmanager:: GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) 既定値を返します。

## <a name="cmditabinfom_style"></a><a name="m_style"></a> CMDITabInfo:: m_style

タブラベルのスタイルを指定します。

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>解説

タブラベルに対して次のいずれかのスタイルを指定します。

|マクロ|説明|
|-|-|
|STYLE_3D|3D スタイル。  |
|STYLE_3D_ONENOTE|Microsoft OneNote スタイル。  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 スタイル。  |
|STYLE_3D_SCROLLED|四角形のタブラベル付きの3D スタイル。  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|共有された水平スクロールバーを持つフラットスタイル。  |
|STYLE_3D_ROUNDED_SCROLL|丸いタブラベル付きの3D スタイル。  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a> CMDITabInfo:: m_tabLocation

タブラベルをページの上部または下部に配置するかどうかを指定します。

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>解説

次のいずれかの場所フラグをタブに適用します。

- LOCATION_BOTTOM: タブラベルはページの下部にあります。

- LOCATION_TOP: タブラベルはページの上部にあります。

## <a name="cmditabinfoserialize"></a><a name="serialize"></a> CMDITabInfo:: Serialize

アーカイブまたはアーカイブからこのオブジェクトの読み取りまたは書き込みを行います。

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*<br/>
からシリアル化する [CArchive クラス](../../mfc/reference/carchive-class.md) オブジェクト。

## <a name="see-also"></a>関連項目

[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI タブ付きグループ](../../mfc/mdi-tabbed-groups.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
