---
title: Microsoft::WRL::Wrappers::HandleTraits 名前空間
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: b19cc426fc7c1b4fc6ec0638730d59998f8c108a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213734"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 名前空間

ハンドルベースの共通リソース型の特性について説明します。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>メンバー

### <a name="structures"></a>構造体

|Name|説明|
|----------|-----------------|
|[CriticalSectionTraits 構造体](criticalsectiontraits-structure.md)|クリティカルセクションを解放するための無効なクリティカルセクションまたは関数のいずれかをサポートするために、`CriticalSection` オブジェクトを特殊化します。|
|[EventTraits 構造体](eventtraits-structure.md)|`Event` クラスハンドルの特性を定義します。|
|[FileHandleTraits 構造体](filehandletraits-structure.md)|ファイルハンドルの特性を定義します。|
|[HANDLENullTraits 構造体](handlenulltraits-structure.md)|初期化されていないハンドルの一般的な特性を定義します。|
|[HANDLETraits 構造体](handletraits-structure.md)|ハンドルの共通特性を定義します。|
|[MutexTraits 構造体](mutextraits-structure.md)|[Mutex](mutex-class.md)クラスの一般的な特性を定義します。|
|[SemaphoreTraits 構造体](semaphoretraits-structure.md)|セマフォオブジェクトの一般的な特性を定義します。|
|[SRWLockExclusiveTraits 構造体](srwlockexclusivetraits-structure.md)|排他ロックモードでの `SRWLock` クラスの一般的な特性について説明します。|
|[SRWLockSharedTraits 構造体](srwlocksharedtraits-structure.md)|共有ロックモードでの `SRWLock` クラスの一般的な特性について説明します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="see-also"></a>参照

[Microsoft::WRL::Wrappers 名前空間](microsoft-wrl-wrappers-namespace.md)
