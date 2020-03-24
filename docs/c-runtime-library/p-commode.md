---
title: __p__commode
ms.date: 11/04/2016
api_name:
- __p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: e3121c127c3ebf0f5fccdeb7ae0f67d0164d0965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171477"
---
# <a name="__p__commode"></a>__p__commode

ファイルの入出力操作に対して既定の`_commode`ファイル コミット モード*を指定する*  グローバル変数を指し示します。

## <a name="syntax"></a>構文

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>戻り値

`_commode` グローバル変数へのポインター。

## <a name="remarks"></a>解説

`__p__commode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。

ファイル コミット モードは重要なデータがディスクに書き込まれるタイミングを指定します。 詳細については、「[fflush](../c-runtime-library/reference/fflush.md)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__p\__commode|internal.h|
