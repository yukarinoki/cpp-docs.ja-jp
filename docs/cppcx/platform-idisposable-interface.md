---
title: Platform::IDisposable インターフェイス
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: 0024edbad0bb3311a0497be67fc8bcfc954602e1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214241"
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

|方法|説明|
|------------|-----------------|
|Dispose|アンマネージ リソースを解放するために使用されます。|

### <a name="requirements"></a>必要条件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform
