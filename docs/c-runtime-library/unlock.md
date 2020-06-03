---
title: _unlock
ms.date: 11/04/2016
api_name:
- _unlock
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unlock
- _unlock
helpviewer_keywords:
- unlock function
- _unlock function
ms.assetid: 2eda2507-a134-4997-aa12-f2f8cb319e14
ms.openlocfilehash: 73eec2b05b1d321bfc8ac61e743459bf2323fb8e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745108"
---
# <a name="_unlock"></a>_unlock

マルチスレッドのロックを解放します。

> [!IMPORTANT]
> この関数は、現在使用されていません。 Visual Studio 2015 以降では、CRT で使用できません。

## <a name="syntax"></a>構文

```cpp
void __cdecl _unlock(
   int locknum
);
```

#### <a name="parameters"></a>パラメーター

*locknum*<br/>
[in] 解放するロックの識別子。

## <a name="requirements"></a>必要条件

**ソース:** mlock.c

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_lock](../c-runtime-library/lock.md)
