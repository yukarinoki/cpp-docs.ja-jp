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
ms.openlocfilehash: 604098cd3289722767117910d6e44e272dcb8b77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371445"
---
# <a name="handletraits-structure"></a>HANDLETraits 構造体

ハンドルの共通の特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLETraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | ---------------------
`Type` | ハンドルの同義語。

### <a name="public-methods"></a>パブリック メソッド

名前                                              | 説明
------------------------------------------------- | -----------------------------
[ハンドルトレイツ::閉じる](#close)                     | 指定したハンドルを閉じます。
[ハンドルトレイト::無効な値を取得します。](#getinvalidvalue) | 無効なハンドルを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLETraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="handletraitsclose"></a><a name="close"></a>ハンドルトレイツ::閉じる

指定したハンドルを閉じます。

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

ハンドル*h が*正常に終了した場合**は true。** それ以外の場合**は false。**

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>ハンドルトレイト::無効な値を取得します。

無効なハンドルを表します。

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>戻り値

常にINVALID_HANDLE_VALUEを返します。 (INVALID_HANDLE_VALUEは Windows によって定義されます。
