---
title: InvokeModeOptions 構造体
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: ff16c6c5a2ce09313283198fe0b86e95d572e46c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785494"
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

**名前空間:** Microsoft::wrl

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource クラス](agileeventsource-class.md)