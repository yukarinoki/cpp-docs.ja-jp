---
title: InvokeModeOptions 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b1eb0e7f6cf49a7c6ac12a4810ae1622e263e2f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882838"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 構造体

デリゲート キュー内のすべてのイベントを発生させるか、エラーが発生した後の発生を停止するかどうかを指定します。 使用可能値が指定されて、`InvokeMode`列挙型。

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

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)
[Microsoft::WRL::AgileEventSource クラス](../windows/agileeventsource-class.md)