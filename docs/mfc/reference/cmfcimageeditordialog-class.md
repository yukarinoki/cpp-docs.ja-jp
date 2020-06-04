---
title: クラスをイメージします。
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 23c2a919428689fe107b82041bd87b758ede2bc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367467"
---
# <a name="cmfcimageeditordialog-class"></a>クラスをイメージします。

この`CMFCImageEditorDialog`クラスはイメージ エディター ダイアログ ボックスをサポートします。

## <a name="syntax"></a>構文

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::CMFC イメージ エディター ダイアログ](#cmfcimageeditordialog)|`CMFCImageEditorDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

この`CMFCImageEditorDialog`クラスには、次のダイアログ ボックスが用意されています。

- イメージ内の個々のピクセルを変更するために使用する画像領域。

- 描画領域のピクセルを変更するための描画ツール。

- 描画ツールで使用される色を指定するカラー パレット。

- 編集の効果を表示するプレビュー領域。

次の図は、イメージ エディターダイアログ ボックスを示しています。

![[CMFCImageEditorDialog] ダイアログ ボックス](../../mfc/reference/media/imageedit.png "[CMFCImageEditorDialog] ダイアログ ボックス")

`CMFCImageEditorDialog`オブジェクトを使用する 1 つの方法は、`CBitmap`編集するイメージを渡す方法です。 画像編集領域のサイズが制限され、論理ピクセル サイズが領域に合わせて調整されるため、大きな画像を作成しないでください。 モーダル`DoModal`ダイアログ ボックスを開始するには、メソッドを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afximage エディターダイアログ.h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>ダイアログ ボックス::CMFC イメージ エディター ダイアログ

`CMFCImageEditorDialog` オブジェクトを構築します。

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
イメージへのポインター。

*親*<br/>
現在のイメージ エディター ダイアログ ボックスの親ウィンドウへのポインター。

*ピクセル数*<br/>
単一ピクセルの色を表すために使用されるビット数(色深度とも呼ばれます)。  *nBitsPixel*パラメーターが -1 の場合、色深度は*pBitmap*パラメーターで指定されたイメージから派生します。 既定値は -1 です。

### <a name="return-value"></a>戻り値

イメージを変更するには、イメージ ポインターをコンストラクターに`CMFCImageEditorDialog`渡します。 次に、`DoModal`モーダル ダイアログ ボックスを開くメソッドを呼び出します。 メソッドが`DoModal`返されるときに、ビットマップには新しいイメージが含まれます。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCImageEditorDialog`示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)
