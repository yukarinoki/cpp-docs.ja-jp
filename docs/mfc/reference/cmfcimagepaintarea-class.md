---
title: CMFCImagePaintArea クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: 3d8bfc40c3c9e937ad5acd7228e49877af65204a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562156"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea クラス

イメージエディターダイアログボックスでイメージを変更するために使用する画像領域を提供します。

## <a name="syntax"></a>構文

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[CMFCImagePaintArea:: CMFCImagePaintArea](#cmfcimagepaintarea)|`CMFCImagePaintArea` オブジェクトを構築します。|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CMFCImagePaintArea:: GetMode](#getmode)|現在の描画モードを取得します。|
|[CMFCImagePaintArea:: SetBitmap](#setbitmap)|画像領域のビットマップイメージを設定します。|
|[CMFCImagePaintArea:: SetColor](#setcolor)|現在の描画色を設定します。|
|[CMFCImagePaintArea:: SetMode](#setmode)|現在の描画モードを設定します。|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用してイメージエディターのダイアログボックスに画像領域を表示します。 [イメージエディター] ダイアログボックスの詳細については、「 [Cmfcimageeditordialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)」を参照してください。

## <a name="example"></a>例

次の例では、クラスのオブジェクトの構築 `CMFCImagePaintArea` 、現在の描画色の設定、現在の描画モードの設定、および画像領域のビットマップイメージの設定を行う方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afximagepaintarea

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a> CMFCImagePaintArea:: CMFCImagePaintArea

`CMFCImagePaintArea` オブジェクトを構築します。

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>パラメーター

*pParentDlg*\
からイメージエディターの親であるダイアログボックスへのポインター。

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a> CMFCImagePaintArea:: GetMode

現在の描画モードを取得します。

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>戻り値

現在の描画モードを指定する [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 値。

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a> CMFCImagePaintArea:: SetBitmap

画像領域のビットマップイメージを設定します。

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*pBitmap*\
から表示する新しいビットマップイメージ。

### <a name="remarks"></a>解説

*Pbitmap*が NULL の場合、このメソッドは、変更可能な描画領域のサイズをゼロに設定します。 それ以外の場合は、変更可能な描画領域のサイズを、指定されたビットマップイメージのサイズに設定します。

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a> CMFCImagePaintArea:: SetColor

現在の描画色を設定します。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*\
から新しい描画色。

### <a name="remarks"></a>解説

イメージエディターパレットバーまたはカラーピッカーから色を選択すると、フレームワークはこのメソッドを呼び出して現在の描画色を更新します。 最初の描画色は黒 (COLORREF 値は 0) です。

描画色は、IMAGE_EDIT_MODE_COLOR を除くすべての描画モードの [イメージエディター] ダイアログボックスで使用されます。 描画モードの詳細については、「 [CMFCImagePaintArea:: IMAGE_EDIT_MODE 列挙型](cmfcimagepaintarea-image-edit-mode-enumeration.md)」を参照してください。

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a> CMFCImagePaintArea:: SetMode

現在の描画モードを設定します。

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>パラメーター

*mode*\
から現在の描画モードを指定する [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 値。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)
