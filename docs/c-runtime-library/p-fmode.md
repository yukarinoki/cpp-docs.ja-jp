---
title: __p__fmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c4dcea9e3f35bf5fd8dbfbed9273562ac3db551
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056340"
---
# <a name="pfmode"></a>__p__fmode

ファイルの入出力操作に対して既定の*ファイル変換モード*を指定する `_fmode` グローバル変数を指し示します。

## <a name="syntax"></a>構文

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>戻り値

`_fmode` グローバル変数へのポインター。

## <a name="remarks"></a>コメント

`__p__fmode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。

ファイル変換モードは、[_open](../c-runtime-library/reference/open-wopen.md) および [_pipe](../c-runtime-library/reference/pipe.md) 入出力操作に対して `binary` または `text` の変換を指定します。 詳細については、「[_fmode](../c-runtime-library/fmode.md)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__p\__fmode|stdlib.h|