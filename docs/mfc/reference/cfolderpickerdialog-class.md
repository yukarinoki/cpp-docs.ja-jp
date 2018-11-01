---
title: CFolderPickerDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ba189badaa9b1605e3467526e7b92a18a1bb5a73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561305"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog クラス

CFolderPickerDialog クラスは、フォルダー ピッカー モードの CFileDialog を実装します。

## <a name="syntax"></a>構文

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|デストラクターです。|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|コンストラクターです。|

## <a name="remarks"></a>Remarks

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

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

コンストラクターです。

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>パラメーター

*lpszFolder*<br/>
初期のフォルダー。

*dwFlags*<br/>
ダイアログ ボックスをカスタマイズするための 1 つまたは複数のフラグの組み合わせ。

*pParentWnd*<br/>
ウィンドウ、ダイアログ ボックスのオブジェクトの親またはオーナー ウィンドウへのポインター。

*ない dwSize*<br/>
OPENFILENAME 構造体のサイズ。

### <a name="remarks"></a>Remarks

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog:: ~ CFolderPickerDialog

デストラクターです。

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
