---
title: Eventsource::targetspointerlock _ データ メンバー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs:
- C++
helpviewer_keywords:
- targetsPointerLock_ data member
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45c85502b7d0768f5fa3e275393a4071fd8649e4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598866"
---
# <a name="eventsourcetargetspointerlock-data-member"></a>EventSource::targetsPointerLock_ データ メンバー

このイベント ハンドラーの中にも、内部データ メンバーへのアクセスを同期**EventSource**の追加、削除、または呼び出されました。

## <a name="syntax"></a>構文

```cpp
Wrappers::SRWLock targetsPointerLock_;
```

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[EventSource クラス](../windows/eventsource-class.md)