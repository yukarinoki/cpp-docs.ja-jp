---
title: HANDLETraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e670dca205f07d1e13a93f8acd0df5965b45109
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161711"
---
# <a name="handletraits-structure"></a>HANDLETraits 構造体

ハンドルの一般的な特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLETraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | ---------------------
`Type` | ハンドルのシノニムです。

### <a name="public-methods"></a>パブリック メソッド

名前                                              | 説明
------------------------------------------------- | -----------------------------
[Handletraits::close](#close)                     | 指定したハンドルを閉じます。
[Handletraits::getinvalidvalue](#getinvalidvalue) | 無効なハンドルを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLETraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>Handletraits::close

指定したハンドルを閉じます。

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドルを閉じます。

### <a name="return-value"></a>戻り値

**true**場合処理*h*正常。 それ以外の終了**false**します。

## <a name="getinvalidvalue"></a>Handletraits::getinvalidvalue

無効なハンドルを表します。

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>戻り値

INVALID_HANDLE_VALUE を常に返します。 (INVALID_HANDLE_VALUE は Windows によって定義されます)。
