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
ms.openlocfilehash: 05c93bf6a2765bd11489075067c627ab3c3ab691
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372579"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 構造体

オブジェクトを`CriticalSection`特化して、無効なクリティカル セクションをサポートするか、クリティカル セクションを解放する関数をサポートします。

## <a name="syntax"></a>構文

```
struct CriticalSectionTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | クリティカル`typedef`セクションへのポインターを定義する A。 `Type` は `typedef CRITICAL_SECTION* Type;` と定義されます。

### <a name="public-methods"></a>パブリック メソッド

名前                                                       | 説明
---------------------------------------------------------- | -----------------
[クリティカルセクショントレイト::無効な値を取得します。](#getinvalidvalue) | テンプレートが常`CriticalSection`に無効になるように、テンプレートを特化します。
[クリティカルセクショントレイツ::ロック解除](#unlock)                   | 指定したクリティカル`CriticalSection`セクション オブジェクトの所有権の解放をサポートするように、テンプレートを特化します。

## <a name="inheritance-hierarchy"></a>継承階層

`CriticalSectionTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>クリティカルセクショントレイト::無効な値を取得します。

テンプレートが常`CriticalSection`に無効になるように、テンプレートを特化します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

常に無効なクリティカル セクションへのポインターを返します。

### <a name="remarks"></a>解説

修飾子`Type`は として`typedef CRITICAL_SECTION* Type;`定義されます。

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>クリティカルセクショントレイツ::ロック解除

指定したクリティカル`CriticalSection`セクション オブジェクトの所有権の解放をサポートするように、テンプレートを特化します。

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
クリティカル セクション オブジェクトへのポインター。

### <a name="remarks"></a>解説

修飾子`Type`は として`typedef CRITICAL_SECTION* Type;`定義されます。

詳細については、Windows API ドキュメントの同期関数セクションの **「LeaveCriticalSection** **関数」** を参照してください。
