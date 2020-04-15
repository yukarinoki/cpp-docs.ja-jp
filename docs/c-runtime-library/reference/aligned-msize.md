---
title: _aligned_msize
ms.date: 4/2/2020
api_name:
- _aligned_msize
- _o__aligned_msize
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
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 21ae07c90bbf9a729a212a97b7de3e0916f8e2c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350598"
---
# <a name="_aligned_msize"></a>_aligned_msize

ヒープで割り当てられたメモリ ブロックのサイズを返します。

## <a name="syntax"></a>構文

```C
size_t _msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
メモリ ブロックへのポインター。

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*offset*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

符号なし整数としてサイズ (バイト数) を返します。

## <a name="remarks"></a>解説

**_aligned_msize**関数は[、_aligned_malloc](aligned-malloc.md)または[_aligned_realloc](aligned-realloc.md)の呼び出しによって割り当てられたメモリ ブロックのサイズをバイト単位で返します。 *配置*値と*オフセット*値は、ブロックを割り当てた関数に渡される値と同じでなければなりません。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされている場合 **、_aligned_msize**[は _aligned_msize_dbg](aligned-msize-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

この関数は、そのパラメーターを検証します。 *memblock*が null ポインターの場合、または*アライメント*が 2 の累乗でない場合 **、_msize**は無効なパラメータ ハンドラを呼び[出します。](../../c-runtime-library/parameter-validation.md) エラーが処理されると、関数は**errno**を**EINVAL**に設定し、-1 を戻します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
