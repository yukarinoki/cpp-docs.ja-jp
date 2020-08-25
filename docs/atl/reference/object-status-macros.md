---
title: オブジェクトの状態マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: d9e2223739dc3d0636337e2e2f713c80dff50131
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835234"
---
# <a name="object-status-macros"></a>オブジェクトの状態マクロ

このマクロは、ActiveX コントロールに属するフラグを設定します。

|名前|説明|
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|OLEMISC フラグを設定するために ATL ActiveX コントロールで使用されます。|

## <a name="requirements"></a>必要条件

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

[[マクロ]](../../atl/reference/atl-macros.md)
