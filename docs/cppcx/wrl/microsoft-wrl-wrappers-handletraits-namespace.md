---
description: '詳細については、次を参照してください: Microsoft:: WRL:: Wrapper:: HandleTraits 名前空間'
title: Microsoft::WRL::Wrappers::HandleTraits 名前空間
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 4bbc970a6d3445e8acda752be1a2030ee99759a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178057"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 名前空間

ハンドルベースの共通リソース型の特性について説明します。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>メンバー

### <a name="structures"></a>構造体

|名前|説明|
|----------|-----------------|
|[CriticalSectionTraits 構造体](criticalsectiontraits-structure.md)|重要な `CriticalSection` セクションを解放するために、無効なクリティカルセクションまたは関数のいずれかをサポートするオブジェクトを特殊化します。|
|[EventTraits 構造体](eventtraits-structure.md)|クラスハンドルの特性を定義 `Event` します。|
|[FileHandleTraits 構造体](filehandletraits-structure.md)|ファイルハンドルの特性を定義します。|
|[HANDLENullTraits 構造体](handlenulltraits-structure.md)|初期化されていないハンドルの一般的な特性を定義します。|
|[HANDLETraits 構造体](handletraits-structure.md)|ハンドルの共通特性を定義します。|
|[MutexTraits 構造体](mutextraits-structure.md)|[Mutex](mutex-class.md)クラスの一般的な特性を定義します。|
|[SemaphoreTraits 構造体](semaphoretraits-structure.md)|セマフォオブジェクトの一般的な特性を定義します。|
|[SRWLockExclusiveTraits 構造体](srwlockexclusivetraits-structure.md)|排他ロックモードでのクラスの一般的な特性について説明し `SRWLock` ます。|
|[SRWLockSharedTraits 構造体](srwlocksharedtraits-structure.md)|共有ロックモードでのクラスの一般的な特性について説明し `SRWLock` ます。|

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="see-also"></a>関連項目

[Microsoft:: WRL:: Wrapper 名前空間](microsoft-wrl-wrappers-namespace.md)
