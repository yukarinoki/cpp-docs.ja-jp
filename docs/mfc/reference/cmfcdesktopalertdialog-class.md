---
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
ms.openlocfilehash: 479959e9b021255e309caf6fee02588a8cd8f1d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367651"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog クラス

クラス`CMFCDesktopAlertDialog`は、ポップアップ ウィンドウにカスタム ダイアログを表示する[CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)と共に使用されます。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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

1. 呼び出し[CMFCDesktopAlertWnd::パラメーター](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)として派生クラスのランタイム クラス情報へのポインターとダイアログ テンプレートのリソース ID を作成します。

1. ホストされるコントロールからのすべての通知を処理するようにカスタム ダイアログをプログラミングするか、これらの通知を直接処理するようにホストされるコントロールをプログラミングします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx デスクトップ アラート ダイアログ.h

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a>ダイアログ::からパラムを作成します。

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>パラメーター

[in]*パラム*<br/>

[in]*親*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a>ダイアログボックス::ゲットドルサイズ

```
CSize GetDlgSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a>ダイアログボックス::ハズフォーカス

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a>メッセージを再変換:P

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CDialogEx クラス](../../mfc/reference/cdialogex-class.md)
