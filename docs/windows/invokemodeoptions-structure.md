---
title: InvokeModeOptions 構造体
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 315f1f0c49c4222bf525bbaf25c9ad0de8b9c7d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511699"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 構造体

デリゲート キュー内のすべてのイベントを発生させる、またはエラーが発生した後の発生を停止するかどうかを指定します。 許容値がで指定された、`InvokeMode`列挙型。

## <a name="syntax"></a>構文

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>必要条件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource クラス](../windows/agileeventsource-class.md)