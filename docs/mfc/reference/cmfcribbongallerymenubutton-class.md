---
title: CMFCRibbonGalleryMenuButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
ms.openlocfilehash: 305393def3b176b052b1db89c66c1e755f528ee6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375144"
---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton クラス

リボン ギャラリーを含むリボン メニュー ボタンを実装します。
詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|`CMFCRibbonGalleryMenuButton` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|([オーバーライドメニューボタン::コピー元](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom).)|
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(オーバーライドメニュー[ボタン::ポップアップメニューを作成](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu)します。|
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|( `CMFCToolBarMenuButton::HasButton`をオーバーライドします)。|
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(オーバーライドメニュー[ボタン::IsEmptyメニューを許可します](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed)。|

### <a name="remarks"></a>解説

ギャラリー メニュー ボタンが、矢印付きのポップアップ メニューとして表示されます。 ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。 ギャラリー メニュー ボタンを構築する場合は、それらのイメージが含まれているイメージ リストを指定する必要があります。

## <a name="example"></a>例

次の例は、メニュー ボタンに行頭記号のギャラリーを表示する方法を示しています。

```cpp
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)
{
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)
    {
        CMFCToolBarButton* pExButton =
        pMenuBar->GetButton(nBulletIndex);
        ASSERT_VALID (pExButton);

        CMFCRibbonGalleryMenuButton paletteBullet (
        pExButton->m_nID,
        pExButton->GetImage (),
        pExButton->m_strText);

        InitBulletPalette (&paletteBullet.GetPalette ());

        pMenuBar->ReplaceButton (ID_PARA_BULLETS,
        paletteBullet);
    }
}
```

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CMFCツールバーボタン](../../mfc/reference/cmfctoolbarbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCツールバーメニューボタン](../../mfc/reference/cmfctoolbarmenubutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCリボンギャラリーメニューボタン](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxリボンパレットギャラリー.h

## <a name="cmfcribbongallerymenubuttoncopyfrom"></a><a name="copyfrom"></a>メニューボタン::コピーフロイン

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

[in]*src*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbongallerymenubuttoncmfcribbongallerymenubutton"></a><a name="cmfcribbongallerymenubutton"></a>メニューボタン::CMFCリボンギャラリーメニューボタン

[オブジェクトを](../../mfc/reference/cmfcribbongallerymenubutton-class.md)構築し、初期化します。

```
CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    CMFCToolBarImages& imagesPalette);

CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    UINT uiImagesPaletteResID = 0,
    int cxPaletteImage = 0);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
ボタンのコマンド ID。 これは、ユーザーがこのボタンをクリックしたときにWM_COMMANDメッセージで送信される値です。

*iイメージ*<br/>
ギャラリー メニュー ボタンで表示するイメージのインデックス。 イメージは *、imagesパレット*パラメーターに格納されます。

*lpszText*<br/>
メニュー ボタンに表示するテキスト。

*画像パレット*<br/>
ギャラリーに表示するイメージの一覧を含みます。

*をクリックします。*<br/>
ギャラリーに表示するイメージのイメージ リストのリソース ID。

*イメージ*<br/>
ギャラリーに表示するイメージの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

ギャラリーメニューボタンは、矢印が付いたポップアップメニューとして表示されます。 ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。

### <a name="example"></a>例

クラスのコンストラクターを使用する方法を次の例に`CMFCRibbonGalleryMenuButton`示します。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

## <a name="cmfcribbongallerymenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>メニューボタン::ポップアップメニュー

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbongallerymenubuttongetpalette"></a><a name="getpalette"></a>メニューボタン::パレットを取得します。

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbongallerymenubuttonhasbutton"></a><a name="hasbutton"></a>メニューボタン::ハズボタン

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbongallerymenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>メニューボタン::IsEmptyメニューを許可

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbongallery-class.md)
