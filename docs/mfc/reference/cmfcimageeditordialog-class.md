---
description: '詳細情報: CMFCImageEditorDialog クラス'
title: CMFCImageEditorDialog クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 6c25cf4a1a8d0cc5852049a06c3a140cbb00a118
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265390"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog クラス

クラスは、[ `CMFCImageEditorDialog` イメージエディター] ダイアログボックスをサポートしています。

## <a name="syntax"></a>構文

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCImageEditorDialog:: CMFCImageEditorDialog](#cmfcimageeditordialog)|`CMFCImageEditorDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

クラスには、次のよう `CMFCImageEditorDialog` なダイアログボックスが用意されています。

- 画像内の個々のピクセルを変更するために使用する画像領域。

- 画像領域のピクセルを変更するための描画ツール。

- 描画ツールで使用される色を指定するためのカラーパレット。

- 編集の効果を表示するプレビュー領域。

次の図は、[イメージエディター] ダイアログボックスを示しています。

![[CMFCImageEditorDialog] ダイアログ ボックス](../../mfc/reference/media/imageedit.png "[CMFCImageEditorDialog] ダイアログ ボックス")

オブジェクトを使用する方法の1つとし `CMFCImageEditorDialog` て、編集対象のイメージを渡すことができ `CBitmap` ます。 イメージの編集領域のサイズは制限されており、その領域に合わせて論理ピクセルサイズが調整されるため、大きなイメージは作成しないでください。 `DoModal`モーダルダイアログボックスを開始するには、メソッドを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afximageeditordialog

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a> CMFCImageEditorDialog:: CMFCImageEditorDialog

`CMFCImageEditorDialog` オブジェクトを構築します。

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>パラメーター

*pBitmap*<br/>
イメージへのポインター。

*pParent*<br/>
[現在のイメージエディター] ダイアログボックスの親ウィンドウへのポインター。

*nBitsPixel*<br/>
1つのピクセルの色を表すために使用されるビット数。色深度とも呼ばれます。  *NBitsPixel* パラメーターが-1 の場合、色深度は *pbitmap* パラメーターによって指定されたイメージから派生します。 既定値は -1 です。

### <a name="return-value"></a>戻り値

イメージを変更するには、イメージポインターをコンストラクターに渡し `CMFCImageEditorDialog` ます。 次に、メソッドを呼び出して `DoModal` モーダルダイアログボックスを開きます。 メソッドから制御が戻ったときに `DoModal` 、ビットマップに新しいイメージが格納されます。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に示し `CMFCImageEditorDialog` ます。 この例は、「 [新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
