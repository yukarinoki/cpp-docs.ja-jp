---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 683759c3bf0b2152ee6fadbb638cd2398daecccd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586130"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 名前空間

一般的なハンドル ベースのリソースの種類の特性について説明します。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>メンバー

### <a name="structures"></a>構造体

|名前|説明|
|----------|-----------------|
|[CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)|専門、`CriticalSection`無効のクリティカル セクションまたはクリティカル セクションを解放する関数をサポートするオブジェクト。|
|[EventTraits 構造体](../windows/eventtraits-structure.md)|特性を定義、`Event`クラスのハンドル。|
|[FileHandleTraits 構造体](../windows/filehandletraits-structure.md)|ファイル ハンドルの特性を定義します。|
|[HANDLENullTraits 構造体](../windows/handlenulltraits-structure.md)|初期化されていないハンドルの一般的な特性を定義します。|
|[HANDLETraits 構造体](../windows/handletraits-structure.md)|ハンドルの一般的な特性を定義します。|
|[MutexTraits 構造体](../windows/mutextraits-structure.md)|一般的な特性を定義、[ミュー テックス](../windows/mutex-class1.md)クラス。|
|[SemaphoreTraits 構造体](../windows/semaphoretraits-structure.md)|セマフォ オブジェクトの一般的な特性を定義します。|
|[SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)|一般的な特性について説明します、`SRWLock`排他ロック モードでのクラス。|
|[SRWLockSharedTraits 構造体](../windows/srwlocksharedtraits-structure.md)|一般的な特性について説明します、`SRWLock`共有ロック モードでのクラス。|

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)