---
title: ModuleType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: d822d214d9bad564286cd2c7494c9f480abdcf00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524749"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)