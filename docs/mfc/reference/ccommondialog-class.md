---
description: '詳細情報: CCommonDialog クラス'
title: CCommonDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 927348982529f14eb0ad762019bb4463aaa77c99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227898"
---
# <a name="ccommondialog-class"></a>CCommonDialog クラス

Windows コモン ダイアログの機能をカプセル化したクラスの基底クラスです。

## <a name="syntax"></a>構文

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|`CCommonDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

次のクラスは、Windows コモンダイアログの機能をカプセル化しています。

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxdlgs

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a> CCommonDialog::CCommonDialog

`CCommonDialog` オブジェクトを構築します。

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型) を指します。 NULL の場合は、ダイアログオブジェクトの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>解説

詳細については、「 [cdialog:: cdialog](../../mfc/reference/cdialog-class.md#cdialog) 」を参照してください。

## <a name="see-also"></a>関連項目

[CDialog クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)<br/>
[CFontDialog クラス](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog クラス](../../mfc/reference/ccolordialog-class.md)<br/>
[CPageSetupDialog クラス](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog クラス](../../mfc/reference/cprintdialog-class.md)<br/>
[CFindReplaceDialog クラス](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
