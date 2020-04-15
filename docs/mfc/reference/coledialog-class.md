---
title: COleDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 6a1983d426e97dd8063aee2857dc36557aa20677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366092"
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
|[を返します。](#getlasterror)|ダイアログ ボックスによって返されるエラー コードを取得します。|

## <a name="remarks"></a>解説

Microsoft ファウンデーション クラス ライブラリ`COleDialog`には、 から派生したクラスがいくつか用意されています。

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a>を返します。

IDABORT`GetLastError`を返すときに、追加の`DoModal`エラー情報を取得するメンバー関数を呼び出します。

```
UINT GetLastError() const;
```

### <a name="return-value"></a>戻り値

返される`GetLastError`エラー コードは、表示されるダイアログ ボックスによって異なります。

### <a name="remarks"></a>解説

特定の`DoModal`エラー メッセージについては、派生クラスのメンバー関数を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
