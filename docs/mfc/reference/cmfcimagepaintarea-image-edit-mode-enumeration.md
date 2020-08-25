---
title: CMFCImagePaintArea::IMAGE_EDIT_MODE 列挙体
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: 37c877cc8562a9479535d9c6132e49e7c9b7e82f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831139"
---
# <a name="cmfcimagepaintareaimage_edit_mode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE 列挙体

イメージエディターダイアログボックスでイメージを変更するために使用する描画モードを指定します。

## <a name="syntax"></a>構文

```
enum IMAGE_EDIT_MODE
{
    IMAGE_EDIT_MODE_PEN = 0,
    IMAGE_EDIT_MODE_FILL,
    IMAGE_EDIT_MODE_LINE,
    IMAGE_EDIT_MODE_RECT,
    IMAGE_EDIT_MODE_ELLIPSE,
    IMAGE_EDIT_MODE_COLOR
};
```

## <a name="members"></a>メンバー

|名前|説明|
|-|-|
|IMAGE_EDIT_MODE_PEN|個々のピクセルを描画するために使用されます。|
|IMAGE_EDIT_MODE_FILL|現在のカーソル位置にある色を含むすべての隣接領域を塗りつぶすために使用されます。|
|IMAGE_EDIT_MODE_LINE|線を描画するために使用します。|
|IMAGE_EDIT_MODE_RECT|四角形を描画するために使用します。|
|IMAGE_EDIT_MODE_ELLIPSE|楕円を描画するために使用します。|
|IMAGE_EDIT_MODE_COLOR|現在の色を現在のカーソル位置の色に設定するために使用します。|

### <a name="remarks"></a>解説

`CMFCImagePaintArea`クラスと `CMFCImageEditorDialog` クラスは、この列挙を使用して現在の描画モードを設定します。 描画モードと現在の色は、[イメージエディター] ダイアログボックスの画像領域を変更するために使用されます。 およびの詳細について `CMFCImagePaintArea` `CMFCImageEditorDialog` は、「 [CMFCImagePaintArea クラス](../../mfc/reference/cmfcimagepaintarea-class.md) 」および「 [cmfcimageeditordialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)」を参照してください。

IMAGE_EDIT_MODE_COLOR 描画モードを使用してイメージから色を選択すると、フレームワークによって現在の描画モードが IMAGE_EDIT_MODE_PEN に設定されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** afximagepaintarea

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea クラス](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)
