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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: aa21854f6a8c4b58a510b16e824449a53b91f329
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218534"
---
# <a name="_set_new_mode"></a>_set_new_mode

**Malloc**の新しいハンドラーモードを設定します。

## <a name="syntax"></a>構文

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>パラメーター

*newhandlermode*<br/>
**Malloc**の新しいハンドラーモード有効な値は0または1です。

## <a name="return-value"></a>戻り値

**Malloc**に対して設定された以前のハンドラーモードを返します。 戻り値1は、メモリの割り当てが失敗したときに **、以前に**新しいハンドラールーチンを呼び出したことを示します。戻り値が0の場合は、返されなかったことを示します。 *Newhandlermode*引数が0または1と等しくない場合、は-1 を返します。

## <a name="remarks"></a>解説

C++ の **_set_new_mode** 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラーモードは、エラー発生時に**malloc**が[_set_new_handler](set-new-handler.md)によって設定された新しいハンドラールーチンを呼び出すかどうかを示します。 既定では、 **malloc**は、メモリの割り当てに失敗したときに新しいハンドラールーチンを呼び出しません。 この既定の動作を無効にすると、 **malloc**がメモリの割り当てに失敗したときに、 **malloc**は、同じ理由で失敗したときと同じ方法で新しいハンドラールーチンを呼び出します **`new`** 。 詳細については、*C++ 言語リファレンス*の「[new](../../cpp/new-operator-cpp.md) および [delete](../../cpp/delete-operator-cpp.md) 演算子」の説明をご覧ください。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

プログラムの初期段階で、または Newmode .obj とリンクします (「[リンクオプション](../../c-runtime-library/link-options.md)」を参照してください)。

この関数は、そのパラメーターを検証します。 *Newhandlermode*が0または1以外の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、 <strong>_set_new_mode</strong>は-1 を返し、 **errno**をに設定し `EINVAL` ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[空け](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
