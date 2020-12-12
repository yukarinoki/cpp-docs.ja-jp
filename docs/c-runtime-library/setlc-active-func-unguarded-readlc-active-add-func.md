---
description: '詳細については、次を参照してください: ___setlc_active_func、___unguarded_readlc_active_add_func'
title: ___setlc_active_func、___unguarded_readlc_active_add_func
ms.date: 11/04/2016
api_name:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 85273b52102e9cca2e42ba4401da60b1d292560c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277089"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func、___unguarded_readlc_active_add_func

互換性のために残されています。 バイナリの互換性を維持するためにのみ、これらの内部関数は CRT によってエクスポートされます。

## <a name="syntax"></a>構文

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>戻り値

戻される値は重要ではありません。

## <a name="remarks"></a>解説

内部 CRT 関数 `___setlc_active_func` および `___unguarded_readlc_active_add_func` は互換性のために残されており、使用されなくなりましたが、バイナリの互換性を維持するために CRT ライブラリによってエクスポートされます。 `___setlc_active_func` の本来の目的は、`setlocale` 関数の現在アクティブな呼び出しの数を返すことでした。 `___unguarded_readlc_active_add_func` の本来の目的は、ロケールをロックしないで参照した関数の数を返すことでした。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|なし|

## <a name="see-also"></a>関連項目

[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
