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
ms.openlocfilehash: cf9a2658807959108b3bb0af672d4c1835b58bc5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375678"
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
|[コントロールバー::Cダイアログバー](#cdialogbar)|`CDialogBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロールバー::作成](#create)|Windows のダイアログ バーを作成し、オブジェクト`CDialogBar`にアタッチします。|

## <a name="remarks"></a>解説

ダイアログ バーは、ユーザーがタブで移動できる標準の Windows コントロールが含まれるという、ダイアログ ボックスに似ています。 もう 1 つの類似点は、ダイアログ バーを表すダイアログ テンプレートを作成することです。

ダイアログ バーの作成と使用は、`CFormView`オブジェクトの作成と使用に似ています。 まず、ダイアログ[エディター](../../windows/dialog-editor.md)を使用して、スタイルWS_CHILDを持ち、他のスタイルを使用しないダイアログ テンプレートを定義します。 テンプレートには、スタイル WS_VISIBLEを設定できません。 アプリケーション コードで、コンストラクターを呼び出して`CDialogBar`オブジェクトを構築し`Create`、ダイアログ バー ウィンドウを作成して`CDialogBar`オブジェクトにアタッチします。

の詳細については、[ダイアログ バー](../../mfc/dialog-bars.md)およびテクニカル[ノート 31](../../mfc/tn031-control-bars.md)のコントロール バーを参照してください。 `CDialogBar`

> [!NOTE]
> 現在のリリースでは、オブジェクト`CDialogBar`は Windows フォーム コントロールをホストできません。 Visual C++ での Windows フォーム コントロールの詳細については[、「MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[コントロールバー](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a>コントロールバー::Cダイアログバー

`CDialogBar` オブジェクトを構築します。

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a>コントロールバー::作成

で`lpszTemplateName`指定されたダイアログ ボックス リソース テンプレート`nIDTemplate`を読み込み、ダイアログ バー ウィンドウを作成し、スタイルを設定`CDialogBar`して、オブジェクトに関連付けます。

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
親`CWnd`オブジェクトへのポインター。

*テンプレート名*<br/>
`CDialogBar`オブジェクトのダイアログ ボックス リソース テンプレートの名前へのポインター。

*nStyle*<br/>
ツール バーのスタイル。 サポートされる追加のツールバー スタイルは次のとおりです。

- CBRS_TOP コントロール バーは、フレーム ウィンドウの上部にあります。

- CBRS_BOTTOMコントロール バーは、フレーム ウィンドウの下部にあります。

- CBRS_NOALIGNコントロールバーは、親のサイズを変更しても再配置されません。

- CBRS_TOOLTIPSコントロールバーにツールヒントが表示されます。

- CBRS_SIZE_DYNAMICコントロールバーは動的です。

- CBRS_SIZE_FIXEDコントロールバーが固定されています。

- CBRS_FLOATINGコントロールバーが浮いている。

- CBRS_FLYBYステータス バーには、ボタンに関する情報が表示されます。

- CBRS_HIDE_INPLACEコントロールバーはユーザーに表示されません。

*nID*<br/>
ダイアログ バーのコントロール ID。

*テンプレート*<br/>
オブジェクトの`CDialogBar`ダイアログ ボックス テンプレートのリソース ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

CBRS_TOPまたはCBRS_BOTTOMの配置スタイルを指定した場合、ダイアログ バーの幅はフレーム ウィンドウの幅で、高さは*nIDTemplate*で指定されたリソースの幅になります。 CBRS_LEFTまたはCBRS_RIGHTの配置スタイルを指定した場合、ダイアログ バーの高さはフレーム ウィンドウの高さであり、その幅は*nIDTemplate*で指定されたリソースの高さになります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL バー](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを表示します。](../../mfc/reference/cformview-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
