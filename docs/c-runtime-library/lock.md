---
title: _lock
ms.date: 11/04/2016
api_name:
- _lock
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lock
- _lock
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
ms.openlocfilehash: 9ab7cab2209dc2e02cacca6d540927aa39dc3965
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745395"
---
# <a name="_lock"></a>_lock

マルチスレッドのロックを取得します。

> [!IMPORTANT]
> この関数は、現在使用されていません。 Visual Studio 2015 以降では、CRT で使用できません。

## <a name="syntax"></a>構文

```cpp
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>パラメーター

*locknum*<br/>
[in] 取得するロックの識別子。

## <a name="remarks"></a>解説

ロックが既に取得されている場合は、このメソッドによってあらためてロックが取得され、内部 C ランタイム (CRT) エラーが発生します。 メソッドでロックを取得できない場合は、致命的なエラーで終了し、エラー コードが `_RT_LOCK`に設定されます。

## <a name="requirements"></a>必要条件

**ソース:** mlock.c

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
