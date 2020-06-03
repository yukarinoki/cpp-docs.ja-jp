---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: e3928c0d3ae4f607dceb99c0762277e8ea9ddbde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319824"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>クラス

この`CMFCWindowsManagerDialog`オブジェクトを使用すると、ユーザーは MDI アプリケーションの MDI 子ウィンドウを管理できます。

## <a name="syntax"></a>構文

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::CMFC マネージャー ダイアログ](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

`CMFCWindowsManagerDialog`には、現在アプリケーションで開いている MDI 子ウィンドウの一覧が含まれます。 このダイアログ ボックスを使用して、MDI 子ウィンドウの状態を手動で制御できます。

`CMFCWindowsManagerDialog`は[、クラス](../../mfc/reference/cmdiframewndex-class.md)内に埋め込まれています。 `CMFCWindowsManagerDialog`は、手動で作成する必要のあるクラスではありません。 代わりに、関数を呼び出[します。](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog) `CMFCWindowsManagerDialog`

## <a name="example"></a>例

を呼び出`CMFCWindowsManagerDialog``CMDIFrameWndEx::ShowWindowsDialog`してオブジェクトを構築する方法を次の例に示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxWindows マネージャーダイアログ.h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a>ダイアログ ボックス::CMFC マネージャー ダイアログ

[オブジェクトを](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)構築します。

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
[in]親ウィンドウまたはオーナー ウィンドウへのポインター。

*ヘルプボタン*<br/>
[in]フレームワークに **[ヘルプ**] ボタンを表示するかどうかを指定するブール値パラメーター。

### <a name="remarks"></a>解説

ビジュアル マネージャーの詳細については、「[ビジュアル化](../../mfc/visualization-manager.md)マネージャー 」を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラスを作成します。](../../mfc/reference/cmdiframewndex-class.md)
