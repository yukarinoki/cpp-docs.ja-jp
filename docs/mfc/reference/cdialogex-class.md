---
description: '詳細情報: CDialogEx クラス'
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
ms.openlocfilehash: 27ec0011935871d472734cae6f0d62b402382727
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185246"
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

ダイアログ ボックス イメージは、リソース ファイルに格納されます。 フレームワークは、リソース ファイルから読み込まれたイメージを自動的に削除します。 現在の背景イメージをプログラムで削除するには、 [CDialogEx:: SetBackgroundImage](#setbackgroundimage) メソッドを呼び出すか、イベントハンドラーを実装し `OnDestroy` ます。 [CDialogEx:: SetBackgroundImage](#setbackgroundimage)メソッドを呼び出す場合は、 `HBITMAP` イメージハンドルとしてパラメーターを渡します。 `CDialogEx` オブジェクトがイメージの所有権を取得し、`m_bAutoDestroyBmp` フラグが `TRUE` である場合は、そのイメージを削除します。

オブジェクトは、 `CDialogEx` [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md) オブジェクトの親にすることができます。 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトは、 `CDialogEx::SetActiveMenu` [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが開いたときにメソッドを呼び出します。 その後、 `CDialogEx` オブジェクトは、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md) オブジェクトが閉じられるまで、すべてのメニューイベントを処理します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxdialogex

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a> CDialogEx:: CDialogEx

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

*nIDTemplate*<br/>
からダイアログボックステンプレートのリソース ID。

*lpszTemplateName*<br/>
からダイアログボックステンプレートのリソース名。

*pParent*<br/>
から親ウィンドウへのポインター。 既定値は NULL です。

*pParentWnd*<br/>
から親ウィンドウへのポインター。 既定値は NULL です。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a> CDialogEx:: SetBackgroundColor

ダイアログ ボックスの背景色を設定します。

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
からRGB カラー値。

*塗装*<br/>
から画面をすぐに更新する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a> CDialogEx:: SetBackgroundImage

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

*hBitmap*<br/>
から背景イメージを処理するハンドル。

*uiBmpResId*<br/>
から背景イメージのリソース ID。

*location*<br/>
から `CDialogEx::BackgroundLocation` イメージの場所を指定する値の1つ。 有効な値には、BACKGR_TILE、BACKGR_TOPLEFT、BACKGR_TOPRIGHT、BACKGR_BOTTOMLEFT、および BACKGR_BOTTOMRIGHT があります。 既定値は BACKGR_TILE です。

*bAutoDestroy*<br/>
から背景イメージを自動的に破棄する場合は TRUE。それ以外の場合は FALSE。

*塗装*<br/>
からダイアログボックスをすぐに再描画する場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

2番目のメソッドオーバーロード構文では、メソッドが成功した場合は TRUE になります。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定したイメージは、ダイアログボックスのクライアント領域に合わせるために拡張されていません。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)
