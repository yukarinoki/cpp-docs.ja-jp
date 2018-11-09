---
title: _unlock
ms.date: 11/04/2016
apiname:
- _unlock
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- unlock
- _unlock
helpviewer_keywords:
- unlock function
- _unlock function
ms.assetid: 2eda2507-a134-4997-aa12-f2f8cb319e14
ms.openlocfilehash: 6fc9287df16ef2310121ced64622f6aadea5926b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533583"
---
# <a name="unlock"></a>_unlock

マルチスレッドのロックを解放します。

> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。

## <a name="syntax"></a>構文

```
void __cdecl _unlock(
   int locknum
);
```

#### <a name="parameters"></a>パラメーター

*locknum*<br/>
[in] 解放するロックの識別子。

## <a name="requirements"></a>必要条件

**ソース:** mlock.c

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_lock](../c-runtime-library/lock.md)