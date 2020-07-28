---
title: CriticalSectionTraits 構造体
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 3573cad21734a97629cbc12b76d73b99024cbc2f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220510"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 構造体

重要な `CriticalSection` セクションを解放するために、無効なクリティカルセクションまたは関数のいずれかをサポートするオブジェクトを特殊化します。

## <a name="syntax"></a>構文

```
struct CriticalSectionTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | **`typedef`** クリティカルセクションへのポインターを定義する。 `Type` は `typedef CRITICAL_SECTION* Type;` と定義されます。

### <a name="public-methods"></a>パブリック メソッド

名前                                                       | 説明
---------------------------------------------------------- | -----------------
[CriticalSectionTraits:: GetInvalidValue](#getinvalidvalue) | テンプレート `CriticalSection` が常に無効になるようにテンプレートを特殊化します。
[CriticalSectionTraits:: Unlock](#unlock)                   | `CriticalSection`指定されたクリティカルセクションオブジェクトの所有権の解放をサポートするようにテンプレートを特殊化します。

## <a name="inheritance-hierarchy"></a>継承階層

`CriticalSectionTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>CriticalSectionTraits:: GetInvalidValue

テンプレート `CriticalSection` が常に無効になるようにテンプレートを特殊化します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

は、無効なクリティカルセクションへのポインターを常に返します。

### <a name="remarks"></a>解説

`Type`修飾子は、として定義され `typedef CRITICAL_SECTION* Type;` ます。

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>CriticalSectionTraits:: Unlock

`CriticalSection`指定されたクリティカルセクションオブジェクトの所有権の解放をサポートするようにテンプレートを特殊化します。

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>パラメーター

*同時*<br/>
クリティカルセクションオブジェクトへのポインター。

### <a name="remarks"></a>解説

`Type`修飾子は、として定義され `typedef CRITICAL_SECTION* Type;` ます。

詳細については、Windows API ドキュメントの「**同期関数**」の「 **LeaveCriticalSection 関数**」を参照してください。
