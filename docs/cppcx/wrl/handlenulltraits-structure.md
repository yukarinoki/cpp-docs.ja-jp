---
title: HANDLENullTraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: 41e06cc50f36a077a34d992c416a543e5bf9b593
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371472"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 構造体

初期化されていないハンドルの共通の特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | ---------------------
`Type` | ハンドルの同義語。

### <a name="public-methods"></a>パブリック メソッド

名前                                                  | 説明
----------------------------------------------------- | -----------------------------
[ハンドルヌルトレイツ::閉じる](#close)                     | 指定したハンドルを閉じます。
[ハンドルヌルトレイト::無効な値を取得します。](#getinvalidvalue) | 無効なハンドルを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="handlenulltraitsclose"></a><a name="close"></a>ハンドルヌルトレイツ::閉じる

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

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>ハンドルヌルトレイト::無効な値を取得します。

無効なハンドルを表します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

常に `nullptr` を返します。
