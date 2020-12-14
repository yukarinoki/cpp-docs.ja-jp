---
description: '詳細については、次を参照してください: _abnormal_termination'
title: _abnormal_termination
ms.date: 11/04/2016
api_name:
- _abnormal_termination
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: 2fa4b82deeebda7624d8ac96be675efc100ae926
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224284"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

**`__finally`** システムが終了ハンドラーの内部リストを実行しているときに、 [try finally ステートメント](../cpp/try-finally-statement.md)のブロックが入力されたかどうかを示します。

## <a name="syntax"></a>構文

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>戻り値

**`true`** システムがスタックを *アンワインド* している場合は。それ以外の場合は **`false`** 。

## <a name="remarks"></a>解説

これは、アンワインドの例外を管理するために使用される内部関数で、ユーザー コードから呼び出されるものではありません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>関連項目

[try-finally ステートメント](../cpp/try-finally-statement.md)
