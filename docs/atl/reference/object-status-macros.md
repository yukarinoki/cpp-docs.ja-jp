---
description: '詳細情報: オブジェクトのステータスマクロ'
title: オブジェクトの状態マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 7aac547ac0b63a7db9ceea3b58befdea3e076f3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157907"
---
# <a name="object-status-macros"></a>オブジェクトの状態マクロ

このマクロは、ActiveX コントロールに属するフラグを設定します。

|名前|説明|
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|OLEMISC フラグを設定するために ATL ActiveX コントロールで使用されます。|

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a> DECLARE_OLEMISC_STATUS

OLEMISC フラグを設定するために ATL ActiveX コントロールで使用されます。

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>パラメーター

*間違った状態*<br/>
すべての該当する OLEMISC フラグ。

### <a name="remarks"></a>解説

このマクロは、ActiveX コントロールの OLEMISC フラグを設定するために使用されます。 詳細については、 [IOleObject:: Get誤 Cstatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
