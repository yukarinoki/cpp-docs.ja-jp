---
description: 詳細については、「memmove、wmemmove」を参照してください。
title: memmove、wmemmove
ms.date: 1/14/2021
api_name:
- memmove
- wmemmove
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memmove
- wmemmove
helpviewer_keywords:
- wmemmove function
- memmove function
ms.openlocfilehash: 6f9942c232710585aa5837510f0f04e5db36fb2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243126"
---
# <a name="memmove-wmemmove"></a>`memmove`, `wmemmove`

バッファーを別のバッファーに移動します。 これらの関数のセキュリティを強化したバージョンを使用できます。「」 [ `memmove_s` を `wmemmove_s` ](memmove-s-wmemmove-s.md)参照してください。

## <a name="syntax"></a>構文

```C
void *memmove(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemmove(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*`dest`*\
コピー先のオブジェクト。

*`src`*\
コピー元のオブジェクト。

*`count`*\
コピーするバイト数 ( **`memmove`** ) または文字数 ( **`wmemmove`** )。

## <a name="return-value"></a>戻り値

の値 *`dest`* 。

## <a name="remarks"></a>注釈

*`count`* **`memmove`** からにバイト () または文字 ( **`wmemmove`** ) をコピー *`src`* *`dest`* します。 コピー元とコピー先の領域の一部が重なり合っている場合、どちらの関数も、重なり合っている領域のコピー元のバイトをコピーした後で上書きします。

**セキュリティに関するメモ** コピー先のバッファーのサイズがソース バッファー以上であることをご確認ください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

次の例のように、 **`memmove`** **`wmemmove`** **`_CRT_SECURE_DEPRECATE_MEMORY`** 関数を非推奨にするために、include ステートメントの前に定数が定義されている場合にのみ、関数と関数が非推奨とされます。

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <string.h>
```

or

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`memmove`**|`<string.h>`|
|**`wmemmove`**|`<wchar.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_memcpy.c
// Illustrate overlapping copy: memmove
// always handles it correctly; memcpy may handle
// it correctly.
//

#include <memory.h>
#include <string.h>
#include <stdio.h>

char str1[7] = "aabbcc";

int main( void )
{
   printf( "The string: %s\n", str1 );
   memcpy( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );

   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string

   printf( "The string: %s\n", str1 );
   memmove( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );
}
```

```Output
The string: aabbcc
New string: aaaabb
The string: aabbcc
New string: aaaabb
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memcpy`, `wmemcpy`](memcpy-wmemcpy.md)\
[`strcpy`, `wcscpy`, `_mbscpy`](strcpy-wcscpy-mbscpy.md)\
[`strncpy`, `_strncpy_l`, `wcsncpy`, `_wcsncpy_l`, `_mbsncpy`, `_mbsncpy_l`](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)\
