---
title: InvokeModeOptions 構造体
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 9bca49479d97ee371f6728f90a9aa96da0387f54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213838"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 構造体

デリゲートキュー内のすべてのイベントを発生させるか、エラーが発生した後に起動を停止するかを指定します。 許容される値は `InvokeMode` 列挙型で指定されます。

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

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource クラス](agileeventsource-class.md)
