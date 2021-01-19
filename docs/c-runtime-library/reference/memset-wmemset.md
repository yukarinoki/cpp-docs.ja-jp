---
title: memset、wmemset
description: 詳細については、「memset、wmemset」を参照してください。
ms.date: 1/15/2021
api_name:
- wmemset
- memset
- _o_memset
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memset
- wmemset
helpviewer_keywords:
- wmemset function
- memset function
ms.openlocfilehash: 1ee5b3cb3653a3d5486eecb0f3b033e69d9db9fa
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563966"
---
# <a name="memset-wmemset"></a>`memset`, `wmemset`

指定した文字にバッファーを設定します。

## <a name="syntax"></a>構文

```C
void *memset(
   void *dest,
   int c,
   size_t count
);
wchar_t *wmemset(
   wchar_t *dest,
   wchar_t c,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*`dest`*\
ターゲットへのポインター。

*`c`*\
設定する文字。

*`count`*\
文字数。

## <a name="return-value"></a>戻り値

の値 *`dest`* 。

## <a name="remarks"></a>注釈

*`count`* の最初の文字 *`dest`* を文字に設定し *`c`* ます。

**セキュリティ** に関する注意コピー先のバッファーに、少なくとも文字の十分な空き領域があることを確認し *`count`* ます。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`memset`**|`<memory.h>` または `<string.h>`|
|**`wmemset`**|`<wchar.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_memset.c
/* This program uses memset to
* set the first four chars of buffer to "*".
*/

#include <memory.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is a test of the memset function";

   printf( "Before: %s\n", buffer );
   memset( buffer, '*', 4 );
   printf( "After:  %s\n", buffer );
}
```

### <a name="output"></a>出力

```Output
Before: This is a test of the memset function
After:  **** is a test of the memset function
```

wmemset の使用例を次に示します。

```C
// crt_wmemset.c
/* This program uses memset to
* set the first four chars of buffer to "*".
*/

#include <wchar.h>
#include <stdio.h>

int main( void )
{
   wchar_t buffer[] = L"This is a test of the wmemset function";

   wprintf( L"Before: %s\n", buffer );
   wmemset( buffer, '*', 4 );
   wprintf( L"After:  %s\n", buffer );
}
```

### <a name="output"></a>出力

```Output
Before: This is a test of the wmemset function
After:  **** is a test of the wmemset function
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memchr`, `wmemchr`](memchr-wmemchr.md)\
[`memcmp`, `wmemcmp`](memcmp-wmemcmp.md)\
[`memcpy`、wmemcpy](memcpy-wmemcpy.md)\
[`_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l`](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)