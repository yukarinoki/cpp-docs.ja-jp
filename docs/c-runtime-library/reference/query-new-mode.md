---
title: _query_new_mode
ms.date: 11/04/2016
apiname:
- _query_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 327f22c847793316bd126721b4a66846d7da84dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620026"
---
# <a name="querynewmode"></a>_query_new_mode

によって設定された新しいハンドラー モードを示す整数を返します **_set_new_mode**の**malloc**します。

## <a name="syntax"></a>構文

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>戻り値

つまり、0 または 1 の現在の新しいハンドラー モードを返します**malloc**します。 戻り値 1、障害時に、メモリの割り当てに**malloc** ; 新しいハンドラー ルーチンを呼び出すと戻り値 0 は、しないことを示します。

## <a name="remarks"></a>Remarks

C++ **_query_new_mode**関数が C++ によって設定された新しいハンドラー モードを示す整数を返します[_set_new_mode](set-new-mode.md)機能[malloc](malloc.md)します。 新しいハンドラー モードを示す、メモリの割り当てに失敗したときか**malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)します。 既定では、 **malloc**失敗によって新しいハンドラー ルーチンを呼び出しません。 使用することができます **_set_new_mode**この動作をオーバーライドする障害で**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子に失敗した場合メモリを割り当てます。 詳細については、C++ 言語リファレンスの「[new および delete 演算子](../../cpp/new-and-delete-operators.md)」の説明をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
