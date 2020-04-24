---
title: CDialogEx クラス
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: 717e560035d42957c16168097577d0c8c589e3c7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753353"
---
# <a name="cdialogex-class"></a>CDialogEx クラス

`CDialogEx` クラスは、ダイアログ ボックスの背景色と背景イメージを指定します。 

## <a name="syntax"></a>構文

```
class CDialogEx : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|`CDialogEx` オブジェクトを構築します。|
|`CDialogEx::~CDialogEx`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|ダイアログ ボックスの背景色を設定します。|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|ダイアログ ボックスの背景イメージを設定します。|

## <a name="remarks"></a>解説

`CDialogEx` クラスを使用するには、ダイアログ ボックス クラスを `CDialogEx` クラスではなく `CDialog` クラスから派生させます。

ダイアログ ボックス イメージは、リソース ファイルに格納されます。 フレームワークは、リソース ファイルから読み込まれたイメージを自動的に削除します。 プログラムで現在の背景イメージを削除するには[、CDialogEx::SetBackgroundImage](#setbackgroundimage)メソッドを呼`OnDestroy`び出すか、イベント ハンドラーを実装します。 [メソッドを](#setbackgroundimage)呼び出すときは、イメージ ハンドルとしてパラメーターを`HBITMAP`渡します。 `CDialogEx` オブジェクトがイメージの所有権を取得し、`m_bAutoDestroyBmp` フラグが `TRUE` である場合は、そのイメージを削除します。

オブジェクト`CDialogEx`は[、クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトの親にすることができます。 [クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトは、クラスオブジェクトが`CDialogEx::SetActiveMenu`開いたときにメソッド[を](../../mfc/reference/cmfcpopupmenu-class.md)呼び出します。 その後、`CDialogEx`オブジェクトは[、CMFCPopupMenu クラス オブジェクト](../../mfc/reference/cmfcpopupmenu-class.md)が閉じられるまで、メニュー イベントを処理します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdialogex.h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a>::CDialogEx

`CDialogEx` オブジェクトを構築します。

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
[in]ダイアログ ボックス テンプレートのリソース ID。

*テンプレート名*<br/>
[in]ダイアログ ボックス テンプレートのリソース名。

*親*<br/>
[in]親ウィンドウへのポインター。 既定値は NULL です。

*pParentWnd*<br/>
[in]親ウィンドウへのポインター。 既定値は NULL です。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a>::設定された背景色

ダイアログ ボックスの背景色を設定します。

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB カラー値。

*brepaint*<br/>
[in]直ちに画面を更新する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a>を設定します。

ダイアログ ボックスの背景イメージを設定します。

```cpp
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
[in]背景イメージへのハンドル。

*をクリックします。*<br/>
[in]背景イメージのリソース ID。

*location*<br/>
[in]イメージの場所`CDialogEx::BackgroundLocation`を指定する値の 1 つ。 有効な値には、BACKGR_TILE、BACKGR_TOPLEFT、BACKGR_TOPRIGHT、BACKGR_BOTTOMLEFT、およびBACKGR_BOTTOMRIGHTが含まれます。 既定値は BACKGR_TILE です。

*b自動破壊*<br/>
[in]背景イメージを自動的に破棄する場合は TRUE。それ以外の場合は FALSE。

*brepaint*<br/>
[in]ダイアログ ボックスをすぐに再描画する場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

2 番目のメソッドオーバーロード構文では、メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定したイメージは、ダイアログ ボックスのクライアント領域に合わせて伸長されません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)
