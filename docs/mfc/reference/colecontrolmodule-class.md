---
description: '詳細情報: COleControlModule クラス'
title: COleControlModule クラス
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: f88296b7c0e897f82227343b31ca2f639902256e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227482"
---
# <a name="colecontrolmodule-class"></a>COleControlModule クラス

OLE コントロール モジュール オブジェクトを派生するための基底クラスです。

## <a name="syntax"></a>構文

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>解説

このクラスには、コントロールモジュールを初期化するためのメンバー関数が用意されています。 Microsoft Foundation クラスを使用する各 OLE コントロールモジュールには、から派生したオブジェクトを1つだけ含めることができ `COleControlModule` ます。 このオブジェクトは、他の C++ グローバルオブジェクトが構築されるときに構築されます。 派生 `COleControlModule` オブジェクトをグローバルレベルで宣言します。

クラスの使用方法の詳細については、 `COleControlModule` 「 [CWinApp](../../mfc/reference/cwinapp-class.md) クラス」と「 [ActiveX コントロール](../../mfc/mfc-activex-controls.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="see-also"></a>関連項目

[MFC のサンプル TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
