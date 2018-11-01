---
title: __uncaught_exception
ms.date: 11/04/2016
apiname:
- __uncaught_exception
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 19d1e18af27722d6f9da39ebaaf6c9415c281849
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579635"
---
# <a name="uncaughtexception"></a>__uncaught_exception

1 つまたは複数の例外がスローされたが、対応するによってまだ処理されていないかどうかを示します**キャッチ**のブロックを[try catch](../../cpp/try-throw-and-catch-statements-cpp.md)ステートメント。

## <a name="syntax"></a>構文

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>戻り値

**true**から例外がスローされます、**お試しください**一致するまでブロック**キャッチ**ブロックが初期化された以外の場合、 **false**します。

## <a name="remarks"></a>Remarks

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>関連項目

[try、throw、catch ステートメント (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
