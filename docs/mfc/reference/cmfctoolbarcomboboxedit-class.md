---
title: CMFCToolBarComboBoxEdit クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01d04960adf8de43c72972e5c46d6f549003c6e7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378957"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit クラス

フレームワークを使用して、`CMFCToolBarComboBoxEdit`編集可能なコンボ ボックス コントロールのように動作するツール バー ボタンを作成するクラス。

## <a name="syntax"></a>構文

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|`CMFCToolBarComboBoxEdit` オブジェクトを構築します。|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|

### <a name="remarks"></a>Remarks

派生クラスを`CMFCToolBarComboBoxEdit`クラスの編集操作をカスタマイズします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtoolbarcomboboxbutton.h

##  <a name="cmfctoolbarcomboboxedit"></a>  CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit

`CMFCToolBarComboBoxEdit` オブジェクトを構築します。

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>パラメーター

*コンボ*<br/>
[in]参照を[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)コンボ ボックス コントロールを含むツール バー ボタンとなるオブジェクト。

### <a name="example"></a>例

次の例のオブジェクトを構築する方法、`CMFCToolBarComboBoxEdit`クラス。 このコード スニペットの一部、 [IE デモ サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
