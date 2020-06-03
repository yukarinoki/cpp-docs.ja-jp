---
title: クラスを編集します。
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: dfbf24f5833d143adc6d21b6cb54dd9ac81c2f0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372201"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>クラスを編集します。

フレームワークは、クラス`CMFCToolBarComboBoxEdit`を使用して、編集可能なコンボ ボックス コントロールのように動作するツール バー ボタンを作成します。

## <a name="syntax"></a>構文

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックスの編集::CMFCツールバーコンボボックス](#cmfctoolbarcomboboxedit)|`CMFCToolBarComboBoxEdit` オブジェクトを構築します。|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|

### <a name="remarks"></a>解説

クラスからクラスを派生`CMFCToolBarComboBoxEdit`させ、その編集操作をカスタマイズします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーコンボボックスボタン.h

## <a name="cmfctoolbarcomboboxeditcmfctoolbarcomboboxedit"></a><a name="cmfctoolbarcomboboxedit"></a>コンボボックスの編集::CMFCツールバーコンボボックス

`CMFCToolBarComboBoxEdit` オブジェクトを構築します。

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>パラメーター

*複合*<br/>
[in]コンボ ボックス コントロールを含むツール バー ボタンである[CMFC ツール バーコンボ ボックス ボタン](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)への参照。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCToolBarComboBoxEdit`示します。 このコード スニペットは、 [IE デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
