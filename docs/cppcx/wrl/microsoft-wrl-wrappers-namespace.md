---
description: '詳細情報: Microsoft:: WRL:: Wrapper 名前空間'
title: Microsoft::WRL::Wrappers 名前空間
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 603fa14b0e43f481b1afe56d98e355d328f284fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209400"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers 名前空間

リソース取得は、オブジェクト、文字列、およびハンドルの有効期間の管理を簡略化する初期化 (RAII) ラッパー型を定義します。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedefs

|名前|説明|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[CriticalSection クラス](criticalsection-class.md)|クリティカルセクションオブジェクトを表します。|
|[イベントクラス (WRL)](event-class-wrl.md)|イベントを表します。|
|[ハンドラー Let クラス](handlet-class.md)|オブジェクトへのハンドルを表します。|
|[HString クラス](hstring-class.md)|HSTRING ハンドルの操作をサポートします。|
|[HStringReference クラス](hstringreference-class.md)|既存の文字列から作成された HSTRING を表します。|
|[Mutex クラス](mutex-class.md)|共有リソースを排他的に制御する同期オブジェクトを表します。|
|[RoInitializeWrapper クラス](roinitializewrapper-class.md)|Windows ランタイムを初期化します。|
|[セマフォクラス](semaphore-class.md)|限定された数のユーザーをサポートできる共有リソースを制御する同期オブジェクトを表します。|
|[SRWLock クラス](srwlock-class.md)|スリムリーダー/ライターロックを表します。|

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
