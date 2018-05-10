---
title: _set_new_mode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b914e950fd94435768c355f327d3d48a653e0d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="setnewmode"></a>_set_new_mode

新しいハンドラー モードを設定**malloc**です。

## <a name="syntax"></a>構文

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>パラメーター

*newhandlermode*<br/>
新しいハンドラー モードを**malloc**以外の場合は有効な値は 0 または 1 です。

## <a name="return-value"></a>戻り値

以前のハンドラーのモードのセットを返します**malloc**です。 戻り値 1 が示す、メモリの割り当てに失敗**malloc**旧称によって新しいハンドラー ルーチンです。 戻り値 0 は、しないことを示します。 場合、 *newhandlermode*引数が 0 または 1 と等しくない、-1 を返します。

## <a name="remarks"></a>コメント

C++ の **_set_new_mode** 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)です。 既定では、 **malloc**メモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすることができるようにときに、 **malloc** 、メモリの割り当てに失敗する**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗します。 詳細については、*C++ 言語リファレンス*の「[new](../../cpp/new-operator-cpp.md) および [delete](../../cpp/delete-operator-cpp.md) 演算子」の説明をご覧ください。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

この関数は、そのパラメーターを検証します。 場合*newhandlermode*として無効なパラメーター ハンドラーを呼び出す 0 または 1 の場合、関数以外の何も記載されて[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_ * * * set_new_mode** -1 を返し**errno**に**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
