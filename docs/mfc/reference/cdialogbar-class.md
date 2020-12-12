---
description: '詳細情報: CDialogBar クラス'
title: CDialogBar クラス
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: 7feb31cd8152309557a398f5c8d0edb8d91c340e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185220"
---
# <a name="cdialogbar-class"></a>CDialogBar クラス

コントロール バー内の Windows のモードレス ダイアログ ボックスの機能を提供します。

## <a name="syntax"></a>構文

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDialogBar:: CDialogBar](#cdialogbar)|`CDialogBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDialogBar:: Create](#create)|Windows ダイアログバーを作成し、オブジェクトにアタッチし `CDialogBar` ます。|

## <a name="remarks"></a>解説

ダイアログバーは、ユーザーが tab キーを使用できる標準の Windows コントロールが含まれているのダイアログボックスに似ています。 もう1つの類似性は、ダイアログバーを表すダイアログテンプレートを作成することです。

ダイアログバーの作成と使用は、オブジェクトの作成と使用に似てい `CFormView` ます。 最初に、 [ダイアログエディター](../../windows/dialog-editor.md) を使用して、スタイル WS_CHILD で他のスタイルを指定せずにダイアログテンプレートを定義します。 テンプレートにスタイル WS_VISIBLE を指定することはできません。 アプリケーションコードで、コンストラクターを呼び出してオブジェクトを構築し、 `CDialogBar` を呼び出し `Create` てダイアログバーウィンドウを作成し、オブジェクトにアタッチし `CDialogBar` ます。

の詳細につい `CDialogBar` ては、「 [ダイアログバー](../../mfc/dialog-bars.md) 」と「 [テクニカルノート 31](../../mfc/tn031-control-bars.md)のコントロールバー」を参照してください。

> [!NOTE]
> 現在のリリースでは、 `CDialogBar` オブジェクトが Windows フォームコントロールをホストすることはできません。 Visual C++ の Windows フォームコントロールの詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a> CDialogBar:: CDialogBar

`CDialogBar` オブジェクトを構築します。

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a> CDialogBar:: Create

またはで指定されたダイアログボックスリソーステンプレート `lpszTemplateName` `nIDTemplate` を読み込み、ダイアログバーウィンドウを作成し、そのスタイルを設定して、オブジェクトに関連付け `CDialogBar` ます。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
親オブジェクトへのポインター `CWnd` 。

*lpszTemplateName*<br/>
`CDialogBar`オブジェクトのダイアログボックスリソーステンプレートの名前へのポインター。

*nStyle*<br/>
ツールバーのスタイル。 サポートされている追加のツールバースタイルは次のとおりです。

- CBRS_TOP コントロールバーは、フレームウィンドウの上部に表示されます。

- CBRS_BOTTOM コントロールバーは、フレームウィンドウの下部に表示されます。

- 親のサイズを変更しても、コントロールバー CBRS_NOALIGN は再配置されません。

- CBRS_TOOLTIPS コントロールバーには、ツールヒントが表示されます。

- CBRS_SIZE_DYNAMIC コントロールバーは動的です。

- CBRS_SIZE_FIXED コントロールバーは固定されています。

- CBRS_FLOATING コントロールバーはフローティングです。

- CBRS_FLYBY ステータスバーには、ボタンに関する情報が表示されます。

- CBRS_HIDE_INPLACE コントロールバーがユーザーに表示されません。

*nID*<br/>
ダイアログバーのコントロール ID。

*nIDTemplate*<br/>
`CDialogBar`オブジェクトのダイアログボックステンプレートのリソース ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

CBRS_TOP または CBRS_BOTTOM の配置スタイルを指定した場合、ダイアログバーの幅はフレームウィンドウの幅、高さは *nIDTemplate* で指定されたリソースの高さになります。 CBRS_LEFT または CBRS_RIGHT の配置スタイルを指定した場合、ダイアログバーの高さはフレームウィンドウの高さ、 *nIDTemplate* で指定されたリソースの幅になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
