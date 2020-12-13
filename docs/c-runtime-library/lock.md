---
description: '詳細については、次を参照してください: _lock'
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
ms.openlocfilehash: 9b95c8b7ad0f0ce84348f9581d9acb611373a27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331040"
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

## <a name="requirements"></a>要件

**ソース:** mlock.c

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
