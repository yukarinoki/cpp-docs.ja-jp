---
title: __uncaught_exception | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcae75a5d25710866f781d766cfd77eceb977649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408216"
---
# <a name="uncaughtexception"></a>__uncaught_exception

1 つまたは複数の例外がスローされたが、対応するによってまだ処理されていないかどうかを示す**キャッチ**のブロック、 [try catch](../../cpp/try-throw-and-catch-statements-cpp.md)ステートメントです。

## <a name="syntax"></a>構文

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>戻り値

**true**で例外がスロー時刻から、**を再試行してください**、一致するまでブロック**キャッチ**ブロックは、それ以外の初期化**false**です。

## <a name="remarks"></a>コメント

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>関連項目

[try、throw、catch ステートメント (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
