---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 853a4756df3b70f4f33deb7159b4d1aee610092c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369446"
---
# <a name="ccommondialog-class"></a>クラス

Windows コモン ダイアログの機能をカプセル化したクラスの基底クラスです。

## <a name="syntax"></a>構文

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ::Cコモンダイアログ](#ccommondialog)|`CCommonDialog` オブジェクトを構築します。|

## <a name="remarks"></a>解説

次のクラスは、Windows コモン ダイアログの機能をカプセル化します。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a>ダイアログ::Cコモンダイアログ

`CCommonDialog` オブジェクトを構築します。

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型 ) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

完全な情報については[、CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog)を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)<br/>
[クラス](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog クラス](../../mfc/reference/ccolordialog-class.md)<br/>
[クラスを設定します。](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog クラス](../../mfc/reference/cprintdialog-class.md)<br/>
[クラスを検索します。](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
