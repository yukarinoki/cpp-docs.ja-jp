---
title: CFolderPickerDialog クラス
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ed3dc151060519bce216cf4a2f3d6559d6b8937e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373870"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog クラス

クラスは、フォルダー ピッカー モードで CFileDialog を実装します。

## <a name="syntax"></a>構文

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::~Cフォルダピッカーダイアログ](#_dtorcfolderpickerdialog)|デストラクターです。|
|[ダイアログ ボックス::C フォルダークリック ダイアログ](#cfolderpickerdialog)|コンストラクターです。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a>ダイアログ ボックス::C フォルダークリック ダイアログ

コンストラクターです。

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
初期フォルダ。

*dwFlags*<br/>
ダイアログ ボックスをカスタマイズするための 1 つまたは複数のフラグの組み合わせ。

*pParentWnd*<br/>
ダイアログ ボックス オブジェクトの親ウィンドウまたはオーナー ウィンドウへのポインター。

*Dwsize*<br/>
ファイル名構造体のサイズ。

### <a name="remarks"></a>解説

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a>ダイアログボックス::~Cフォルダピッカーダイアログ

デストラクターです。

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
