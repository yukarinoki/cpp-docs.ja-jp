---
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
ms.openlocfilehash: a963f1059eccaddce9ec01cd53a07df668ee46c6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213659"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

**`__finally`** システムが終了ハンドラーの内部リストを実行しているときに、 [try finally ステートメント](../cpp/try-finally-statement.md)のブロックが入力されたかどうかを示します。

## <a name="syntax"></a>構文

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>戻り値

**`true`** システムがスタックを*アンワインド*している場合は。それ以外の場合は **`false`** 。

## <a name="remarks"></a>解説

これは、アンワインドの例外を管理するために使用される内部関数で、ユーザー コードから呼び出されるものではありません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>関連項目

[try-finally ステートメント](../cpp/try-finally-statement.md)
