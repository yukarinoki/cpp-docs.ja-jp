---
title: Platform::CallbackContext 列挙型
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 1daa3988fcb985dab9d3083233a3703a20cc2fdb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214275"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext 列挙型

コールバック関数 (イベント ハンドラー) が実行するスレッド コンテキストを指定します。

## <a name="syntax"></a>構文

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>メンバー

|型コード|説明|
|---------------|-----------------|
|Any|コールバック関数は、任意のスレッド コンテキストで実行できます。|
|同じ|コールバック関数は、非同期操作を開始したスレッド コンテキストでのみ実行できます。|

### <a name="requirements"></a>必要条件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd
