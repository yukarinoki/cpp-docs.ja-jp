---
title: _set_new_mode
ms.date: 11/04/2016
apiname:
- _set_new_mode
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
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 0228170e4ab5b55b4b061fa61a412766de77a063
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602463"
---
# <a name="setnewmode"></a>_set_new_mode

新しいハンドラー モードを設定**malloc**します。

## <a name="syntax"></a>構文

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>パラメーター

*newhandlermode*<br/>
新しいハンドラー モードを**malloc**。 有効な値は 0 または 1。

## <a name="return-value"></a>戻り値

以前のハンドラー モードのセットを返します**malloc**します。 戻り値 1、障害時に、メモリの割り当てに**malloc**以前新しいハンドラー ルーチンと呼ばれる戻り値 0 は呼び出さなかったことを示します。 場合、 *newhandlermode*引数が 0 または 1 と等しく、-1 を返します。

## <a name="remarks"></a>Remarks

C++ の **_set_new_mode** 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)します。 既定では、 **malloc**でメモリの割り当ての失敗によって新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドするように、 **malloc** 、メモリの割り当てに失敗した**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗しました。 詳細については、*C++ 言語リファレンス*の「[new](../../cpp/new-operator-cpp.md) および [delete](../../cpp/delete-operator-cpp.md) 演算子」の説明をご覧ください。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

この関数は、そのパラメーターを検証します。 場合*newhandlermode*で説明として、無効なパラメーター ハンドラーを呼び出す 0 または 1 の場合、関数以外の何も[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合<strong>_set_new_mode</strong> -1 を返し**errno**に`EINVAL`します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
