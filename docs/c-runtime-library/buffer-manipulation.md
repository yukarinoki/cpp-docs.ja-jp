---
title: バッファー操作
ms.date: 04/04/2018
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
ms.openlocfilehash: a79bfdb33d2bff5e18c916a2e116ab03251afdf1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443589"
---
# <a name="buffer-manipulation"></a>バッファー操作

次のルーチンを使用して、バイト単位でメモリの領域を操作します。

## <a name="buffer-manipulation-routines"></a>バッファー操作ルーチン

|ルーチン|用途|
|-------------|---------|
|[_memccpy](../c-runtime-library/reference/memccpy.md)|指定した文字または指定した数の文字がコピーされるまで、1 つのバッファーから別のバッファーに文字をコピーします|
|[memchr、wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|バッファーで指定された文字が、指定した数の文字内で最初に発生した場所にポインターを返します|
|[memcmp、wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|2 つのバッファーから指定した数の文字を比較します|
|[memcpy、wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)、[memcpy_s、wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|1 つのバッファーから別のバッファーに指定した数の文字をコピーします|
|[_memicmp、_memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|大文字小文字に関係なく、2 つのバッファーの指定された数の文字を比較します|
|[memmove、wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)、[memmove_s、wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|1 つのバッファーから別のバッファーに指定した数の文字をコピーします|
|[memset、wmemset](../c-runtime-library/reference/memset-wmemset.md)|指定された文字を使用して、バッファー内の指定したバイト数を初期化します|
|[_swab](../c-runtime-library/reference/swab.md)|データのバイト数をスワップし、指定した場所にそのデータを格納します|

ソースとターゲットの領域が重複している場合、**memmove** のみが完全なソースを正しくコピーすることを保証します。

## <a name="see-also"></a>参照

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
