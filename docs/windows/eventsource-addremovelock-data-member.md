---
title: Eventsource::addremovelock _ データ メンバー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::addRemoveLock_
dev_langs:
- C++
helpviewer_keywords:
- addRemoveLock_ data member
ms.assetid: e2d69256-4891-4aad-ad0b-76479c0bb076
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 084a292ed5228f337deced74a87ee20acf0ee5ab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611736"
---
# <a name="eventsourceaddremovelock-data-member"></a>EventSource::addRemoveLock_ データ メンバー

アクセスを同期、 [targets _](../windows/eventsource-targets-data-member.md)配列を追加するときに、削除、またはイベント ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[EventSource クラス](../windows/eventsource-class.md)