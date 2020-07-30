---
title: __uncaught_exception
ms.date: 11/04/2016
api_name:
- __uncaught_exception
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 1eb06abbda7978acf578555f966f0857dff02053
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211633"
---
# <a name="__uncaught_exception"></a>__uncaught_exception

1つ以上の例外がスローされたが、try-catch ステートメントの対応するブロックによってまだ処理されていないかどうかを示し **`catch`** ます。 [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md)

## <a name="syntax"></a>構文

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>戻り値

**`true`** ブロック内で、 **`try`** 一致するブロックが初期化されるまで例外がスローされた場合は **`catch`** 。それ以外の場合は **`false`** 。

## <a name="remarks"></a>解説

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>関連項目

[try、throw、catch ステートメント (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
