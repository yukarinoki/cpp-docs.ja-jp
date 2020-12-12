---
description: '詳細情報: CMFCRibbonCustomizeDialog クラス'
title: CMFCRibbonCustomizeDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: 9420ebdf32a1c26cba6efee17467fd3dfe202574
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293613"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog クラス

リボンの [ **カスタマイズ** ] ページを表示します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` オブジェクトを構築します。|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理しない場合、またはメッセージハンドラーから0を返した場合、MFC はこのクラスを自動的にインスタンス化します。

アプリケーションでこのクラスを使用してリボンの [ **カスタマイズ** ] ダイアログボックスを表示する場合は、インスタンス化してメソッドを呼び出すだけ `DoModal` です。

このクラスは [Cmfcpropertysheet プロパティクラス](../../mfc/reference/cmfcpropertysheet-class.md)から派生したものであるため、API を使用してカスタムページを追加でき `CMFCPropertySheet` ます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribboncustomizedialog

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a> CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

`CMFCRibbonCustomizeDialog` オブジェクトを構築します。

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
から親ウィンドウへのポインター (通常はメインフレーム)。

*プライマリ*<br/>
からカスタマイズするへのポインター `CMFCRibbonBar` 。

### <a name="example"></a>例

次の例は、オブジェクトを構築する方法を示して `CMFCRibbonCustomizeDialog` います。

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>解説

コンストラクターは、 [CMFCRibbonCustomizePropertyPage クラス](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) オブジェクトをインスタンス化し、プロパティシートページのコレクションに追加します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
