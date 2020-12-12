---
description: '詳細情報: CFolderPickerDialog クラス'
title: CFolderPickerDialog クラス
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: f4a5bcc3162a5fffcc723d7ec420685b02be10f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184427"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog クラス

CFolderPickerDialog クラスは、フォルダー選択モードで CFileDialog を実装します。

## <a name="syntax"></a>構文

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#_dtorcfolderpickerdialog)|デストラクターです。|
|[CFolderPickerDialog:: CFolderPickerDialog](#cfolderpickerdialog)|コンストラクターです。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxdlgs

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a> CFolderPickerDialog:: CFolderPickerDialog

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
初期フォルダー。

*dwFlags*<br/>
ダイアログボックスをカスタマイズできる1つ以上のフラグの組み合わせ。

*pParentWnd*<br/>
ダイアログボックスオブジェクトの親またはオーナーウィンドウへのポインター。

*dwSize*<br/>
OPENFILENAME 構造体のサイズ。

### <a name="remarks"></a>解説

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a> CFolderPickerDialog:: ~ CFolderPickerDialog

デストラクターです。

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
