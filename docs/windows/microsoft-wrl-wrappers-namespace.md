---
title: Microsoft::WRL::Wrappers Namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
dev_langs:
- C++
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b1a63494e06ce3117e7e8fccd1d0cbca8cdb4d0
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250342"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers 名前空間

オブジェクト、文字列、およびハンドルの有効期間管理を簡素化するリソースの取得は初期化 (RAII) のラッパー型を定義します。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedef

|名前|説明|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[CriticalSection クラス](../windows/criticalsection-class.md)|クリティカル セクション オブジェクトを表します。|
|[イベント クラス (WRL)](../windows/event-class-wrl.md)|イベントを表します。|
|[HandleT クラス](../windows/handlet-class.md)|オブジェクトへのハンドルを表します。|
|[HString クラス](../windows/hstring-class.md)|HSTRING ハンドルの操作をサポートします。|
|[HStringReference クラス](../windows/hstringreference-class.md)|既存の文字列から作成された HSTRING を表します。|
|[Mutex クラス](../windows/mutex-class.md)|共有リソースを排他的に制御する同期オブジェクトを表します。|
|[RoInitializeWrapper クラス](../windows/roinitializewrapper-class.md)|Windows ランタイムを初期化します。|
|[Semaphore クラス](../windows/semaphore-class.md)|ユーザーの数に制限をサポートできる共有リソースを制御する同期オブジェクトを表します。|
|[SRWLock クラス](../windows/srwlock-class.md)|スリム リーダー/ライター ロックを表します。|

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)