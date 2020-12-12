---
description: '詳細情報: COleDialog クラス'
title: COleDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 9bdb532d58136ac2aac622fa88f674e60ec7221e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227300"
---
# <a name="coledialog-class"></a>COleDialog クラス

OLE のダイアログ ボックスに共通の機能が用意されています。

## <a name="syntax"></a>構文

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDialog:: GetLastError](#getlasterror)|ダイアログボックスによって返されるエラーコードを取得します。|

## <a name="remarks"></a>解説

Microsoft Foundation Class ライブラリには、から派生したクラスがいくつか用意されてい `COleDialog` ます。

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxodlgs

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a> COleDialog:: GetLastError

が `GetLastError` IDABORT を返す場合は、メンバー関数を呼び出して追加のエラー情報を取得し `DoModal` ます。

```
UINT GetLastError() const;
```

### <a name="return-value"></a>戻り値

によって返されるエラーコードは `GetLastError` 、表示される特定のダイアログボックスによって異なります。

### <a name="remarks"></a>解説

`DoModal`特定のエラーメッセージについては、派生クラスのメンバー関数を参照してください。

## <a name="see-also"></a>関連項目

[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
