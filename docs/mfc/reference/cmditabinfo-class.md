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
ms.openlocfilehash: 0d230d2a3401ab556adc1183f4c4210ec6ff3c29
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370034"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo クラス

クラス`CMDITabInfo`は、パラメーターを渡すために使用[されます。](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) MDI タブ付きグループの動作を制御するために、このクラスのメンバーを設定します。

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
|[コマンドインフォ::シリアライズ](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[コマンドインフォ::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|アクティブなタブのラベルに**閉じる**ボタンを表示するかどうかを指定します。|
|[コマンドインフォ::m_bAutoColor](#m_bautocolor)|MDI タブに色を付けるかどうかを指定します。|
|[コマンドインフォ::m_bDocumentMenu](#m_bdocumentmenu)|開いているドキュメントの一覧を表示するポップアップ メニューをタブ グループに表示するか、スクロール ボタンを表示するかを指定します。|
|[コマンドインフォ::m_bEnableTabSwap](#m_benabletabswap)|ユーザーがドラッグしてタブの位置を入れ替えできるかどうかを指定します。|
|[コマンドインフォ::m_bFlatFrame](#m_bflatframe)|タブにフラット フレームを設定するかどうかを指定します。|
|[コマンドインフォ::m_bTabCloseButton](#m_btabclosebutton)|各タブ ラベルに**閉じる**ボタンを表示するかどうかを指定します。|
|[コマンドインフォ::m_bTabCustomTooltips](#m_btabcustomtooltips)|カスタム ツールヒントを有効にするかどうかを指定します。|
|[コマンドインフォ::m_bTabIcons](#m_btabicons)|MDI タブにアイコンを表示するかどうかを指定します。|
|[コマンドインフォ::m_nTabBorderSize](#m_ntabbordersize)|各タブ ウィンドウの境界線のサイズを指定します。|
|[コマンドインフォ::m_style](#m_style)|タブ ラベルのスタイルを指定します。|
|[コマンドインフォ::m_tabLocation](#m_tablocation)|タブのラベルをページの上部または下部のどちらに配置するかを指定します。|

## <a name="remarks"></a>解説

このクラスは、フレームワークが作成する MDI タブ グループのパラメーターを指定します。

## <a name="example"></a>例

クラス内のさまざまなメンバー変数の値を設定する方法を次の例に`CMDITabInfo`示します。

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmdiクライアントエリアウンド.h

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a>コマンドインフォ::m_bActiveTabCloseButton;

アクティブなタブのラベルに**閉じる**ボタンを表示するかどうかを指定します。

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>解説

TRUE の場合、アクティブなタブのラベルに**閉じる**ボタンが表示されます。 **[閉じる**] ボタンは、タブ領域の右上隅から削除されます。 そうしないと、アクティブなタブのラベルに**閉じる**ボタンは表示されません。 タブ領域の右上隅に**閉じる**ボタンが表示されます。

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a>コマンドインフォ::m_bAutoColor

各 MDI タブに独自の色があるかどうかを指定します。

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブは独自の色を持ちます。 色のセットは MFC ライブラリによって管理されます。 それ以外の場合、タブは白で表示されます。 既定値は FALSE です。

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a>コマンドインフォ::m_bDocumentMenu

各タブに、タブ領域の右端に開いているドキュメントの一覧を表示するポップアップ メニューを表示するかどうかを指定します。

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブ ウィンドウには、タブ領域の右端に開いているドキュメントの一覧を表示するポップアップ メニューが表示されます。それ以外の場合、タブウィンドウはタブ領域の右端にスクロールボタンを表示します。 既定値は FALSE です。

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a>コマンドインフォ::m_bEnableTabSwap

ユーザーがドラッグしてタブの位置を入れ替えできるかどうかを指定します。

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>解説

TRUE の場合、ユーザーはタブをドラッグしてタブの位置を変更できます。 それ以外の場合、ユーザーはタブの位置を変更できません。 既定値は TRUE です。

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a>コマンドインフォ::m_bFlatFrame

各タブ ウィンドウにフラット フレームを設定するかどうかを指定します。

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a>コマンドインフォ::m_bTabCloseButton

各タブ ウィンドウに **[閉じる**] ボタンを表示するかどうかを指定します。

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>解説

TRUE の場合、各タブ ウィンドウにはタブの右端に **[閉じる**] ボタン**Close**が表示されます。 既定値は TRUE です。

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a>コマンドインフォ::m_bTabCustomTooltips

タブにツールヒントを表示するかどうかを指定します。

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>解説

TRUE の場合、アプリケーションはメイン フレームにAFX_WM_ON_GET_TAB_TOOLTIPメッセージを送信します。 このメッセージは、ON_REGISTERED_MESSAGE マクロを使用して処理できます。

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a>コマンドインフォ::m_bTabIcons

MDI タブにアイコンを表示するかどうかを指定します。

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>解説

TRUE の場合、各 MDI タブにアイコンが表示されます。 既定値は FALSE です。

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a>コマンドインフォ::m_nTabBorderSize

各タブ ウィンドウの境界線のサイズをピクセル単位で指定します。

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>解説

[デフォルト値を](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)返します。

## <a name="cmditabinfom_style"></a><a name="m_style"></a>コマンドインフォ::m_style

タブ ラベルのスタイルを指定します。

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>解説

タブ ラベルに次のスタイルのいずれかを指定します。

|||
|-|-|
|STYLE_3D|3D スタイル。  |
|STYLE_3D_ONENOTE|マイクロソフトの OneNote スタイル。  |
|STYLE_3D_VS2005|2005 年のスタイルです。  |
|STYLE_3D_SCROLLED|長方形のタブラベルを持つ 3D スタイル。  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|水平スクロール バーが共有されたフラット スタイル。  |
|STYLE_3D_ROUNDED_SCROLL|ラウンドタブラベル付きの3Dスタイル。  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a>コマンドインフォ::m_tabLocation

タブのラベルをページの上部または下部のどちらに配置するかを指定します。

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>解説

タブに適用するには、次の場所フラグのいずれかを選択します。

- LOCATION_BOTTOM: タブラベルはページの下部にあります。

- LOCATION_TOP: タブラベルはページの上部にあります

## <a name="cmditabinfoserialize"></a><a name="serialize"></a>コマンドインフォ::シリアライズ

このオブジェクトをアーカイブまたはアーカイブから読み取るか書き込みます。

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[in]シリアル化する[CArchive クラス](../../mfc/reference/carchive-class.md)オブジェクト。

## <a name="see-also"></a>関連項目

[クラスを作成します。](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI タブ付きグループ](../../mfc/mdi-tabbed-groups.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
