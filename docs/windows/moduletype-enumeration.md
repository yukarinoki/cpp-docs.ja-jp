---
title: ModuleType 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe8d41aded38db7cde5316e04cfa1689845aa4e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595473"
---
# <a name="moduletype-enumeration"></a>ModuleType 列挙型

モジュールがインプロセス サーバーまたはアウトプロセス サーバーをサポートするかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
enum ModuleType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`InProc`|・ インプロセス サーバーです。|
|`OutOfProc`|アウト プロセス サーバーの場合。|
|`DisableCaching`|モジュールのキャッシュ メカニズムを無効にします。|
|`InProcDisableCaching`|組み合わせた`InProc`と`DisableCaching`します。|
|`OutOfProcDisableCaching`|組み合わせた`OutOfProc`と`DisableCaching`します。|

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)