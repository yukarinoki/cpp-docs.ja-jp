---
description: 詳細については、「Cancel遷移 Tionpolicy 列挙型」を参照してください。
title: CancelTransitionPolicy 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: 8de995ed492f8f1260534b08b818b77d889d95fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344537"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy 列挙型

クライアントから要求された取り消し状態に関して、非同期操作が完了またはエラーの状態に遷移する方法を示します。

## <a name="syntax"></a>構文

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`RemainCanceled`|非同期操作が現在クライアントによって要求された取り消し状態にある場合、これは、ターミナルの完了状態またはエラー状態に遷移するのではなく、キャンセル状態のままになることを示します。|
|`TransitionFromCanceled`|非同期操作が現在クライアントによって要求された取り消し状態にある場合は、このフラグを利用する呼び出しによって決定された状態が、その取り消し状態から完了またはエラーの状態に遷移することを示します。|

## <a name="requirements"></a>要件

**ヘッダー:** async .h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
