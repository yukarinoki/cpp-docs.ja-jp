---
title: _set_new_mode
ms.date: 4/2/2020
api_name:
- _set_new_mode
- _o__set_new_mode
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 3a27717d65714de54f477e4e2b3f243c4631fd8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332319"
---
# <a name="_set_new_mode"></a>_set_new_mode

**malloc**の新しいハンドラモードを設定します。

## <a name="syntax"></a>構文

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>パラメーター

*ニューハンドラーモード*<br/>
**malloc**の新しいハンドラモード ;有効な値は 0 または 1 です。

## <a name="return-value"></a>戻り値

**malloc**に対して設定された前のハンドラ モードを返します。 戻り値が 1 の場合、メモリの割り当てが失敗した場合 **、malloc**は以前に new ハンドラー ルーチンと呼ばれ、その後は新しいハンドラー ルーチンが呼び出されていました。戻り値が 0 の場合は、その値が返されなかったことを示します。 *newhandlermode*引数が 0 または 1 でない場合は、-1 を返します。

## <a name="remarks"></a>解説

C++ の **_set_new_mode** 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラ モードは、失敗時に**malloc**が[_set_new_handler](set-new-handler.md)で設定された新しいハンドラ ルーチンを呼び出すかどうかを示します。 既定では **、malloc**はメモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 **malloc**がメモリの割り当てに失敗した場合に **、malloc**が new ハンドラールーチンを呼び出すのと同じ理由で失敗した場合と同じ方法で、malloc が**新しい**ハンドラー・ルーチンを呼び出すようになります。 詳細については、*C++ 言語リファレンス*の「[new](../../cpp/new-operator-cpp.md) および [delete](../../cpp/delete-operator-cpp.md) 演算子」の説明をご覧ください。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

プログラムの早い段階で、または Newmode.obj とリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照)。

この関数は、そのパラメーターを検証します。 *newhandlermode*が 0 または 1 以外の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合<strong>、_set_new_mode</strong>は -1 を返し **、errno**を に設定します`EINVAL`。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[無料](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
