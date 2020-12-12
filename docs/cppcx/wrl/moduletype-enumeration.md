---
description: '詳細情報: ModuleType 列挙型'
title: ModuleType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 148f9594fd16a6c8a2af70ac0ff2ac03cd1f62e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209374"
---
# <a name="moduletype-enumeration"></a>ModuleType 列挙型

モジュールがインプロセス サーバーまたはアウトプロセス サーバーをサポートするかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
enum ModuleType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`InProc`|インプロセスサーバー。|
|`OutOfProc`|アウトプロセスサーバー。|
|`DisableCaching`|モジュールのキャッシュメカニズムを無効にします。|
|`InProcDisableCaching`|との `InProc` 組み合わせ `DisableCaching` 。|
|`OutOfProcDisableCaching`|との `OutOfProc` 組み合わせ `DisableCaching` 。|

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
