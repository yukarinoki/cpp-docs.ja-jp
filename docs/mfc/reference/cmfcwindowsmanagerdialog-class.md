---
description: '詳細情報: CMFCWindowsManagerDialog クラス'
title: CMFCWindowsManagerDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 526cf731e049ffd267382b0c3895b5d29792dcb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331618"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog クラス

オブジェクトを使用すると、mdi `CMFCWindowsManagerDialog` アプリケーションで mdi 子ウィンドウを管理できます。

## <a name="syntax"></a>構文

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCWindowsManagerDialog:: CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

には、 `CMFCWindowsManagerDialog` アプリケーションで現在開いている MDI 子ウィンドウの一覧が含まれています。 ユーザーは、このダイアログボックスを使用して、MDI 子ウィンドウの状態を手動で制御できます。

`CMFCWindowsManagerDialog` は [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)内に埋め込まれています。 `CMFCWindowsManagerDialog`は、手動で作成する必要があるクラスではありません。 代わりに、関数 [CMDIFrameWndEx:: ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)を呼び出し、オブジェクトを作成して表示し `CMFCWindowsManagerDialog` ます。

## <a name="example"></a>例

次の例は、を呼び出してオブジェクトを構築する方法を示し `CMFCWindowsManagerDialog` て `CMDIFrameWndEx::ShowWindowsDialog` います。 このコードスニペットは、 [Visual Studio のデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxWindowsManagerDialog

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a> CMFCWindowsManagerDialog:: CMFCWindowsManagerDialog

[Cmfcwindowsmanagerdialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)オブジェクトを構築します。

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>パラメーター

*pMDIFrame*<br/>
から親またはオーナーウィンドウへのポインター。

*bHelpButton*<br/>
からフレームワークで [ **ヘルプ** ] ボタンを表示するかどうかを指定するブール型パラメーターです。

### <a name="remarks"></a>解説

ビジュアルマネージャーの詳細については、「 [Visualization Manager](../../mfc/visualization-manager.md)」を参照してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)
