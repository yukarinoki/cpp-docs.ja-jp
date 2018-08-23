---
title: Eventsource::getsize メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::GetSize
dev_langs:
- C++
helpviewer_keywords:
- GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e852f2664e03ee0ac788fb426951c244f895bb6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581104"
---
# <a name="eventsourcegetsize-method"></a>EventSource::GetSize メソッド

現在関連付けられているイベント ハンドラーの数を取得**EventSource**オブジェクト

## <a name="syntax"></a>構文

```cpp
size_t GetSize() const;
```

## <a name="return-value"></a>戻り値

内のイベント ハンドラーの数[targets _](../windows/eventsource-targets-data-member.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[EventSource クラス](../windows/eventsource-class.md)