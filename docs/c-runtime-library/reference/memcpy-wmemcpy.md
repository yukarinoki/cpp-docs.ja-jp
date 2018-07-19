---
title: memcpy、wmemcpy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- memcpy
- wmemcpy
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
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
dev_langs:
- C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9880bdbc608933a1b6cfffe3473a9b07f0252ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405368"
---
# <a name="memcpy-wmemcpy"></a>memcpy、wmemcpy

バッファー間でバイトをコピーします。 これらの関数のセキュリティを強化したバージョンについては、「[memcpy_s、wmemcpy_s](memcpy-s-wmemcpy-s.md)」をご覧ください。

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

*dest*<br/>
コピー先のバッファー。

*src*<br/>
コピー元のバッファー。

*count*<br/>
コピーする文字数。

## <a name="return-value"></a>戻り値

値*dest*です。

## <a name="remarks"></a>コメント

**memcpy**コピー*カウント*からバイト*src*に*dest*です。**wmemcpy**コピー*カウント*ワイド文字 (2 バイト)。 ソースと変換先が重なり合うかどうかの動作**memcpy**が定義されていません。 使用して**memmove**重なり合う領域を処理します。

> [!IMPORTANT]
> コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

> [!IMPORTANT]
> 非常に多くバッファー オーバーランと、したがって潜在的なセキュリティのぜい弱性がの不適切な使用に由来されているため**memcpy**、この関数が Security Development Lifecycle (SDL) で「禁止」関数間で一覧表示します。  一部の vc++ ライブラリ クラスを使い続けることを確認することがあります**memcpy**です。  さらに、vc++ コンパイラ オプティマイザーへの呼び出しをも出力お気付きかもしれません**memcpy**です。  Visual C++ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合も特定のコード パターンが認識同様のパターンに**memcpy**とは、そのため、関数への呼び出しに置き換えられます。  このような場合、使用する**memcpy**元よりも安全性は変わらない指示が以外の場合は、パフォーマンスが調整への呼び出しに最適化されているだけで**memcpy**関数。  「安全」な CRT 関数を使用しても安全性が保証されるわけではない (安全でない状態になりにくいということに過ぎない) ように、「禁止された」関数を使用しても、危険であると保証されるわけではありません (安全性を保障するのに、より大きな監視が必要になるに過ぎません)。
>
> **Memcpy** vc++ コンパイラとライブラリによる使用量を慎重に調査されている、それ以外の場合 SDL に準拠したコード内でこれらの呼び出しが許可されます。  **memcpy**呼び出しアプリケーションのソース コードで導入された SDL に準拠している場合は使用するセキュリティの専門家によるレビュー済みです。

**Memcpy**と**wmemcpy**場合、関数が廃止される予定のみ定数 **_CRT_SECURE_DEPRECATE_MEMORY**インクルード ステートメントの前に定義されました。次の例など、非推奨である関数:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

または

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**memcpy**|\<memory.h> または \<string.h>|
|**wmemcpy**|\<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

参照してください[memmove](memmove-wmemmove.md)の使用方法のサンプルについては**memcpy**です。

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove、wmemmove](memmove-wmemmove.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
