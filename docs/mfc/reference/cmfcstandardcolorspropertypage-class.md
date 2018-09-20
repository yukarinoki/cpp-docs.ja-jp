---
title: CMFCStandardColorsPropertyPage クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 475780db8883fe9a8c8393648876764406cee376
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380595"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage クラス

色のダイアログ ボックスで、標準の色を選択するユーザーを使用して、プロパティ ページを表します。

## <a name="syntax"></a>構文

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|既定のコンストラクター|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|`CMFCStandardColorsPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCStandardColorsPropertyPage::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|

### <a name="remarks"></a>Remarks

`CMFCColorDialog`クラスでは、このクラスを使用して、標準の色 ページを表示します。 詳細については`CMFCColorDialog`を参照してください[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxstandardcolorspropertypage.h

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCCustomColorsPropertyPage クラス](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
