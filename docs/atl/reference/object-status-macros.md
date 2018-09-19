---
title: オブジェクトの状態に関するマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b684d66a96a7a3a7d7d60a1b107792c2061ce57
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086604"
---
# <a name="object-status-macros"></a>オブジェクトの状態に関するマクロ

このマクロは、ActiveX コントロールに属しているフラグを設定します。

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL の ActiveX コントロールにおける入りますフラグを設定するために使用します。|  

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS

ATL の ActiveX コントロールにおける入りますフラグを設定するために使用します。

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>パラメーター

*miscstatus*<br/>
該当するすべて入りますフラグ。

### <a name="remarks"></a>Remarks

このマクロは、ActiveX コントロールの入りますフラグの設定に使用されます。 参照してください[IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)の詳細。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
