---
title: Eventtargetarray::end メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::End
dev_langs:
- C++
helpviewer_keywords:
- End method
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 341333b0c4f51c42004ad638a5a8f4fcb7d7e466
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596492"
---
# <a name="eventtargetarrayend-method"></a>EventTargetArray::End メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
ComPtr<IUnknown>* End();
```

## <a name="return-value"></a>戻り値

イベント ハンドラーの内部配列の最後の要素のアドレス。

## <a name="remarks"></a>Remarks

イベント ハンドラーの内部配列の最後の要素のアドレスを取得します。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[EventTargetArray クラス](../windows/eventtargetarray-class.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)