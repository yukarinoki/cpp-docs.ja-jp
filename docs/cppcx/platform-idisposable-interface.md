---
description: '詳細情報: Platform:: IDisposable インターフェイス'
title: Platform::IDisposable インターフェイス
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: 0a1e7b44861d48f496f21d634d4d28ff1c968bcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276778"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable インターフェイス

アンマネージ リソースを解放するために使用されます。

## <a name="syntax"></a>構文

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>属性

**GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")

**VersionAttribute**(NTDDI_WIN8)

### <a name="members"></a>メンバー

IDisposable インターフェイスは IUnknown インターフェイスから継承します。 また IDisposable には次の種類のメンバーもあります。

**メソッド**

IDisposable インターフェイスには、次のメソッドがあります。

|Method|説明|
|------------|-----------------|
|Dispose|アンマネージ リソースを解放するために使用されます。|

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform
