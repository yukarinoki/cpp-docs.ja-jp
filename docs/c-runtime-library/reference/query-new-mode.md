---
description: '詳細については、次を参照してください: _query_new_mode'
title: _query_new_mode
ms.date: 11/04/2016
api_name:
- _query_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 90c7355f4babc4726c8b52d61309eb1ceb23c9a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137138"
---
# <a name="_query_new_mode"></a>_query_new_mode

**Malloc** の **_set_new_mode** によって設定された新しいハンドラーモードを示す整数を返します。

## <a name="syntax"></a>構文

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>戻り値

**Malloc** の現在の新しいハンドラーモード (0 または 1) を返します。 戻り値1は、メモリの割り当てが失敗したときに、 **malloc** が新しいハンドラールーチンを呼び出すことを示します。戻り値が0の場合は、そうでないことを示します。

## <a name="remarks"></a>解説

C++ の **_query_new_mode** 関数は、 [Malloc](malloc.md)用に c++ [_set_new_mode](set-new-mode.md)関数によって設定された新しいハンドラーモードを示す整数を返します。 新しいハンドラーモードは、メモリの割り当てに失敗したときに、 **malloc** が [_set_new_handler](set-new-handler.md)によって設定された新しいハンドラールーチンを呼び出すかどうかを示します。 既定では、 **malloc** はエラー発生時に新しいハンドラールーチンを呼び出しません。 **_Set_new_mode** を使用すると、この動作をオーバーライドして、エラー **malloc** がメモリの割り当てに失敗したときと同じ方法で新しいハンドラールーチンを呼び出すことができ **`new`** ます。 詳細については、C++ 言語リファレンスの「[new および delete 演算子](../../cpp/new-and-delete-operators.md)」の説明を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
