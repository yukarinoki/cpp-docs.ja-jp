---
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
ms.openlocfilehash: af84c5239a9cb3cbddb1ab4f0230e5b1a3373573
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425959"
---
# <a name="cdialogbar-class"></a>CDialogBar クラス

コントロール バー内の Windows のモードレス ダイアログ ボックスの機能を提供します。

## <a name="syntax"></a>構文

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CDialogBar:: CDialogBar](#cdialogbar)|`CDialogBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CDialogBar:: Create](#create)|Windows ダイアログバーを作成し、`CDialogBar` オブジェクトにアタッチします。|

## <a name="remarks"></a>解説

ダイアログバーは、ユーザーが tab キーを使用できる標準の Windows コントロールが含まれているのダイアログボックスに似ています。 もう1つの類似性は、ダイアログバーを表すダイアログテンプレートを作成することです。

ダイアログバーの作成と使用は、`CFormView` オブジェクトの作成と使用に似ています。 最初に、[ダイアログエディター](../../windows/dialog-editor.md)を使用して、スタイル WS_CHILD で他のスタイルを指定せずにダイアログテンプレートを定義します。 テンプレートにスタイル WS_VISIBLE を指定することはできません。 アプリケーションコードで、コンストラクターを呼び出して `CDialogBar` オブジェクトを作成し、`Create` を呼び出してダイアログバーウィンドウを作成し `CDialogBar` オブジェクトにアタッチします。

`CDialogBar`の詳細については、「[ダイアログバー](../../mfc/dialog-bars.md) 」と「[テクニカルノート 31](../../mfc/tn031-control-bars.md)のコントロールバー」を参照してください。

> [!NOTE]
>  現在のリリースでは、`CDialogBar` オブジェクトは Windows フォームコントロールをホストできません。 ビジュアルC++の Windows フォームコントロールの詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

##  <a name="cdialogbar"></a>CDialogBar:: CDialogBar

`CDialogBar` オブジェクトを構築します。

```
CDialogBar();
```

##  <a name="create"></a>CDialogBar:: Create

`lpszTemplateName` または `nIDTemplate`で指定されたダイアログボックスリソーステンプレートを読み込み、ダイアログバーウィンドウを作成し、そのスタイルを設定して、`CDialogBar` オブジェクトに関連付けます。

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
親 `CWnd` オブジェクトへのポインター。

*lpszTemplateName*<br/>
`CDialogBar` オブジェクトのダイアログボックスリソーステンプレートの名前へのポインター。

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
`CDialogBar` オブジェクトのダイアログボックステンプレートのリソース ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

CBRS_TOP または CBRS_BOTTOM の配置スタイルを指定した場合、ダイアログバーの幅はフレームウィンドウの幅、高さは*nIDTemplate*で指定されたリソースの高さになります。 CBRS_LEFT または CBRS_RIGHT の配置スタイルを指定した場合、ダイアログバーの高さはフレームウィンドウの高さ、 *nIDTemplate*で指定されたリソースの幅になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>参照

[MFC のサンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)
