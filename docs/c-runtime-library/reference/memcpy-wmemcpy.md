---
title: memcpy、wmemcpy
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: afdb854bd28b55735cc6b5e26788307e2db0caa6
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211057"
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

値*dest*します。

## <a name="remarks"></a>Remarks

**memcpy**コピー*カウント*からバイト*src*に*dest*;**wmemcpy**コピー*カウント*ワイド文字 (2 バイト)。 ソースと変換先が重なり合うかどうかの動作**memcpy**が定義されていません。 使用**memmove**重なり合っている領域を処理します。

> [!IMPORTANT]
> コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

> [!IMPORTANT]
> 多数のバッファー オーバーラン、およびセキュリティ攻撃の可能性があるための不適切な使用に由来したため、 **memcpy**、この関数が Security Development Lifecycle (SDL) で「禁止」関数間で一覧表示します。  一部の vc++ ライブラリ クラスが引き続き使用することがわかります**memcpy**します。  Vc++ コンパイラ オプティマイザーを生成する場合の呼び出しをさらに、生じる**memcpy**します。  Visual C++ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合も特定のコード パターンが認識のパターンと同じように、 **memcpy**とは、そのため、関数の呼び出しに置き換えられます。  このような場合は、使用**memcpy**がなくなる元よりも安全でない指示があった; パフォーマンス調整への呼び出しに最適化されているだけ**memcpy**関数。  「安全」な CRT 関数を使用しても安全性が保証されるわけではない (安全でない状態になりにくいということに過ぎない) ように、「禁止された」関数を使用しても、危険であると保証されるわけではありません (安全性を保障するのに、より大きな監視が必要になるに過ぎません)。
>
> **Memcpy** vc++ コンパイラとライブラリによる使用量が十分に注意深く調査、SDL に準拠している場合はコード内でこれらの呼び出しが許可されます。  **memcpy**アプリケーションのソース コードで導入された呼び出しは、使用するセキュリティの専門家によって確認された場合にのみ、SDL に準拠しています。

**Memcpy**と**wmemcpy**場合、関数は廃止のみ定数 **_CRT_SECURE_DEPRECATE_MEMORY**の順序でインクルード ステートメントの前に定義されます次の例に示すように、非推奨にする関数。

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

または

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**memcpy**|\<memory.h> または \<string.h>|
|**wmemcpy**|\<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

参照してください[memmove](memmove-wmemmove.md)を使用する方法の例については**memcpy**します。

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove、wmemmove](memmove-wmemmove.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
