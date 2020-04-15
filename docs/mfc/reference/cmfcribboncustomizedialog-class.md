---
title: クラスをカスタマイズします。
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: a66c0a19c04e0a900b91c0c28c45bb9c766d25c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375202"
---
# <a name="cmfcribboncustomizedialog-class"></a>クラスをカスタマイズします。

リボンの **[カスタマイズ**] ページを表示します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックスをカスタマイズします。](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` オブジェクトを構築します。|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

MFC は、AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理しない場合、またはメッセージ ハンドラーから 0 を返す場合は、このクラスを自動的にインスタンス化します。

アプリケーションでこのクラスを使用してリボンの **[カスタマイズ**] ダイアログ ボックスを表示する場合は、インスタンス化`DoModal`してメソッドを呼び出します。

このクラスは[CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)から派生しているため、API を使用してカスタム`CMFCPropertySheet`ページを追加できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[ダイアログボックス](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon カスタマイザダイアログ.h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>ダイアログボックスをカスタマイズします。

`CMFCRibbonCustomizeDialog` オブジェクトを構築します。

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]親ウィンドウ (通常はメイン フレーム) へのポインター。

*pリボン*<br/>
[in]カスタマイズするを`CMFCRibbonBar`指すポインター。

### <a name="example"></a>例

オブジェクトを構築する方法を次の例`CMFCRibbonCustomizeDialog`に示します。

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>解説

コンストラクターは[、CMFCRibbonCustomizePropertyPage クラス](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)オブジェクトをインスタンス化し、プロパティ シート ページのコレクションに追加します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
