---
description: '詳細については、次を参照してください: InvokeModeOptions 構造体'
title: InvokeModeOptions 構造体
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 1e1382242c95c47355239c220c43c278280dd451
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298982"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 構造体

デリゲートキュー内のすべてのイベントを発生させるか、エラーが発生した後に起動を停止するかを指定します。 許容値は列挙型で指定され `InvokeMode` ます。

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

**ヘッダー:** イベント .h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource クラス](agileeventsource-class.md)
