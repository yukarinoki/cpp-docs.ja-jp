---
description: '詳細については、次を参照してください: __p__commode'
title: __p__commode
ms.date: 4/2/2020
api_name:
- __p__commode
- _o___p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: f3f779196b650d05bb16c0da652d47946fc2a10d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213625"
---
# <a name="__p__commode"></a>__p__commode

ファイルの入出力操作に対して既定の *ファイル コミット モード* を指定する `_commode` グローバル変数を指し示します。

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

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__p\__commode|internal.h|
