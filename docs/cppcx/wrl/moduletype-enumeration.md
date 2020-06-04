---
title: ModuleType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 8425a15d594f7b8b30027d3576ee86015b656130
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213721"
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
|`InProcDisableCaching`|`InProc` と `DisableCaching`の組み合わせ。|
|`OutOfProcDisableCaching`|`OutOfProc` と `DisableCaching`の組み合わせ。|

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
