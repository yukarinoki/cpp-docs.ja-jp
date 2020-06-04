---
title: オブジェクトステータスマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 5617ce7fb972c98775072f72244f91052d41ece3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326175"
---
# <a name="object-status-macros"></a>オブジェクトステータスマクロ

このマクロは、ActiveX コントロールに属するフラグを設定します。

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|OLEMISC フラグを設定するために ATL ActiveX コントロールで使用されます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

OLEMISC フラグを設定するために ATL ActiveX コントロールで使用されます。

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>パラメーター

*その他の状況*<br/>
適用可能なすべての OLEMISC フラグ。

### <a name="remarks"></a>解説

このマクロは、ActiveX コントロールの OLEMISC フラグを設定するために使用します。 詳細については[、IOleObject::GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
