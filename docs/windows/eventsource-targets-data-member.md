---
title: Eventsource::targets _ データ メンバー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targets_
dev_langs:
- C++
helpviewer_keywords:
- targets_ data member
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fcdcb759c90009410f76a4b10039a0d976ca0cc4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605116"
---
# <a name="eventsourcetargets-data-member"></a>EventSource::targets_ データ メンバー

1 つまたは複数のイベント ハンドラーの配列。

## <a name="syntax"></a>構文

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

## <a name="remarks"></a>Remarks

ときに、現在で表されるイベント**EventSource**オブジェクトが、イベント ハンドラーは呼び出されます。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[EventSource クラス](../windows/eventsource-class.md)