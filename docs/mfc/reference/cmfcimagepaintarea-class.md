---
title: クラス
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
ms.openlocfilehash: 4e73bd7bc1a28317dbfc452df1f45541dfcbfd21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374431"
---
# <a name="cmfcimagepaintarea-class"></a>クラス

イメージ エディターダイアログ ボックスでイメージを変更するために使用する画像領域を提供します。

## <a name="syntax"></a>構文

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[次の値を指定します。](#cmfcimagepaintarea)|`CMFCImagePaintArea` オブジェクトを構築します。|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[ペインエリア::取得モード](#getmode)|現在の描画モードを取得します。|
|[を指定します。](#setbitmap)|ピクチャ領域のビットマップ イメージを設定します。|
|[カラーを設定します。](#setcolor)|現在の描画色を設定します。|
|[ペインエリア::セットモード](#setmode)|現在の描画モードを設定します。|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用して、画像領域をイメージ エディター ダイアログ ボックスに表示します。 イメージ エディター ダイアログ ボックスの詳細については[、「CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)」を参照してください。

## <a name="example"></a>例

次の例は、`CMFCImagePaintArea`クラスのオブジェクトの作成方法、現在の描画色の設定方法、現在の描画モードの設定方法、およびピクチャ領域のビットマップ イメージの設定方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[ペイン](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afximagepaintarea.h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>次の値を指定します。

`CMFCImagePaintArea` オブジェクトを構築します。

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*親の人*|[in]イメージ エディターの親であるダイアログ ボックスへのポインター。|

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a>ペインエリア::取得モード

現在の描画モードを取得します。

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>戻り値

現在の描画モードを指定する[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)値。

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>を指定します。

ピクチャ領域のビットマップ イメージを設定します。

```
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ビットマップ*|[in]表示する新しいビットマップ イメージ。|

### <a name="remarks"></a>解説

*pBitmap*が NULL の場合、このメソッドは、変更可能な描画領域のサイズを 0 に設定します。 それ以外の場合は、指定されたビットマップ イメージのサイズに変更可能なペイント領域のサイズを設定します。

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>カラーを設定します。

現在の描画色を設定します。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*色*|[in]新しい描画色。|

### <a name="remarks"></a>解説

イメージ エディターのパレット バーまたはカラー ピッカーから色を選択すると、フレームワークは現在の描画色を更新するためにこのメソッドを呼び出します。 初期描画色は黒 (COLORREF 値 0) です。

描画色は、イメージ エディターダイアログ ボックスで、IMAGE_EDIT_MODE_COLORを除くすべての描画モードで使用されます。 描画モードの詳細については、「列挙体を[IMAGE_EDIT_MODE表示](cmfcimagepaintarea-image-edit-mode-enumeration.md)します。

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a>ペインエリア::セットモード

現在の描画モードを設定します。

```
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*モード*|[in]現在の描画モードを指定する[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)値。|

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラスをイメージします。](../../mfc/reference/cmfcimageeditordialog-class.md)
