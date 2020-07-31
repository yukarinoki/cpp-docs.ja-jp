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
ms.openlocfilehash: a7ce730b8d723a839c5b509c825cff84111ca613
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226920"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 構造体

初期化されていないハンドルの一般的な特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | [説明]
------ | ---------------------
`Type` | ハンドルのシノニム。

### <a name="public-methods"></a>パブリック メソッド

名前                                                  | [説明]
----------------------------------------------------- | -----------------------------
[HANDLENullTraits:: Close](#close)                     | 指定されたハンドルを閉じます。
[HANDLENullTraits:: GetInvalidValue](#getinvalidvalue) | は無効なハンドルを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="handlenulltraitsclose"></a><a name="close"></a>HANDLENullTraits:: Close

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

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLENullTraits:: GetInvalidValue

は無効なハンドルを表します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

常にを返し **`nullptr`** ます。
