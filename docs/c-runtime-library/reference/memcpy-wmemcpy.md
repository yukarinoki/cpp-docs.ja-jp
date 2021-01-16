---
description: 詳細については、「memcpy、wmemcpy」を参照してください。
title: memcpy、wmemcpy
ms.date: 1/14/2021
api_name:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: 49b08877f63bf0d331dcc40e2885b375fe6d1ee7
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243139"
---
# <a name="memcpy-wmemcpy"></a>`memcpy`, `wmemcpy`

バッファー間でバイトをコピーします。 これらの関数のセキュリティを強化したバージョンを使用できます。「」 [ `memcpy_s` を `wmemcpy_s` ](memcpy-s-wmemcpy-s.md)参照してください。

## <a name="syntax"></a>構文

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*`dest`*\
コピー先のバッファー。

*`src`*\
コピー元のバッファー。

*`count`*\
コピーする文字数。

## <a name="return-value"></a>戻り値

の値 *`dest`* 。

## <a name="remarks"></a>注釈

**`memcpy`***`count`* からにバイト *`src`* を *`dest`* コピー **`wmemcpy`** *`count`* します。ワイド文字 (2 バイト) をコピーします。 コピー元とコピー先が重複する場合、の動作 **`memcpy`** は定義されていません。 **`memmove`** 重複する領域を処理するために使用します。

> [!IMPORTANT]
> コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

> [!IMPORTANT]
> 多くのバッファーオーバーランが発生しており、セキュリティ攻撃の可能性があり、の不適切な使用のためにトレースされているため **`memcpy`** 、この関数は、セキュリティ開発ライフサイクル (SDL) によって "禁止されている" 機能の中に一覧表示されます。  一部の VC + + ライブラリクラスが引き続き使用されていることがわかり **`memcpy`** ます。  また、VC + + コンパイラオプティマイザーがへの呼び出しを生成することがあり **`memcpy`** ます。  Visual C++ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合、特定のコードパターンがのパターンと同一であると認識され、その **`memcpy`** 結果、関数の呼び出しに置き換えられることがあります。  このような場合、を使用すること **`memcpy`** は、元の手順よりも安全ではありません。これらは、パフォーマンスチューニングされた関数の呼び出しに最適化されてい **`memcpy`** ます。  "安全な" CRT 関数を使用すると、安全であるとは言えません (安全でないことが難しいだけです)。 "禁止された" 関数を使用すると、危険を保証することはできません (安全性を確保するために、より多くの審査が必要になります)。
>
> **`memcpy`** VC + + コンパイラとライブラリによる使用は注意深く調査されているため、これらの呼び出しは、他の方法で SDL に準拠しているコード内で許可されます。  **`memcpy`** アプリケーションのソースコードで導入された呼び出しは、その使用がセキュリティの専門家によって確認されている場合にのみ、SDL に準拠しています。

次の例のように、 **`memcpy`** **`wmemcpy`** **`_CRT_SECURE_DEPRECATE_MEMORY`** 関数を非推奨にするために、include ステートメントの前に定数が定義されている場合にのみ、関数と関数が非推奨とされます。

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

or

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`memcpy`**|`<memory.h>` または `<string.h>`|
|**`wmemcpy`**|`<wchar.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

[`memmove`](memmove-wmemmove.md)の使用例については、「」を参照してください **`memcpy`** 。

## <a name="see-also"></a>参照

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memchr`, `wmemchr`](memchr-wmemchr.md)\
[`memcmp`, `wmemcmp`](memcmp-wmemcmp.md)\
[`memmove`, `wmemmove`](memmove-wmemmove.md)\
[`memset`, `wmemset`](memset-wmemset.md)\
[`strcpy_s`, `wcscpy_s`, `_mbscpy_s`](strcpy-s-wcscpy-s-mbscpy-s.md)\
[`strncpy_s`, `_strncpy_s_l`, `wcsncpy_s`, `_wcsncpy_s_l`, `_mbsncpy_s`, `_mbsncpy_s_l`](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)\
