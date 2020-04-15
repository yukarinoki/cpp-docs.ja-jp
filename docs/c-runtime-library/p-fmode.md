---
title: __p__fmode
ms.date: 4/2/2020
api_name:
- __p__fmode
- _o___p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: aecba640099719f90db8bbd5dbe386ea99aae45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349245"
---
# <a name="__p__fmode"></a>__p__fmode

ファイルの入出力操作に対して既定の*ファイル変換モード*を指定する `_fmode` グローバル変数を指し示します。

## <a name="syntax"></a>構文

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>戻り値

`_fmode` グローバル変数へのポインター。

## <a name="remarks"></a>解説

`__p__fmode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。

ファイル変換モードは、[_open](../c-runtime-library/reference/open-wopen.md) および [_pipe](../c-runtime-library/reference/pipe.md) 入出力操作に対して `binary` または `text` の変換を指定します。 詳細については、「[_fmode](../c-runtime-library/fmode.md)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|__p\__fmode|stdlib.h|
