---
description: '詳細情報: CMFCDesktopAlertDialog クラス'
title: CMFCDesktopAlertDialog クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
ms.openlocfilehash: 327ec72b1e58d90e768f51c083ff9545f24f6f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193189"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog クラス

クラスは、 `CMFCDesktopAlertDialog` [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md) と共に使用して、ポップアップウィンドウにカスタムダイアログを表示します。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|( `CDialogEx::PreTranslateMessage`をオーバーライドします)。|

### <a name="remarks"></a>解説

次の手順を実行し、ポップアップ ウィンドウにカスタム ダイアログを表示します。

1. `CMFCDesktopAlertDialog` の派生クラスを作成します。

1. プロジェクトのリソースに、子のダイアログ テンプレートを作成します。

1. ダイアログテンプレートのリソース ID と、パラメーターとして派生クラスのランタイムクラス情報へのポインターを使用して、 [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) を呼び出します。

1. ホストされるコントロールからのすべての通知を処理するようにカスタム ダイアログをプログラミングするか、これらの通知を直接処理するようにホストされるコントロールをプログラミングします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDesktopAlertDialog

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a> CMFCDesktopAlertDialog:: CreateFromParams

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>パラメーター

から *params*<br/>

から *Pparent*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a> CMFCDesktopAlertDialog:: GetDlgSize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a> CMFCDesktopAlertDialog:: HasFocus

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a> CMFCDesktopAlertDialog::P reTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

から *pMsg*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CDialogEx クラス](../../mfc/reference/cdialogex-class.md)
