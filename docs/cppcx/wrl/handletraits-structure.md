---
title: HANDLETraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: c04e53789fd737b12ca10ef2c279a05fb43f5925
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212996"
---
# <a name="handletraits-structure"></a>HANDLETraits 構造体

ハンドルの共通特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLETraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | ---------------------
`Type` | ハンドルのシノニム。

### <a name="public-methods"></a>パブリック メソッド

名前                                              | 説明
------------------------------------------------- | -----------------------------
[HANDLETraits:: Close](#close)                     | 指定されたハンドルを閉じます。
[HANDLETraits:: GetInvalidValue](#getinvalidvalue) | は無効なハンドルを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLETraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="handletraitsclose"></a><a name="close"></a>HANDLETraits:: Close

指定されたハンドルを閉じます。

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

**`true`***ハンドルが*正常に閉じられた場合は。それ以外の場合は **`false`** 。

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLETraits:: GetInvalidValue

は無効なハンドルを表します。

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>戻り値

常に INVALID_HANDLE_VALUE を返します。 (INVALID_HANDLE_VALUE は Windows で定義されています)。
