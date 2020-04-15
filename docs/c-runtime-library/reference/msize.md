---
title: _msize
ms.date: 4/2/2020
api_name:
- _msize
- _o__msize
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
- msize
- _msize
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
ms.openlocfilehash: 7d5f62bd6111a305c18b0ee19bb6d3e90f2ddb49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338668"
---
# <a name="_msize"></a>_msize

ヒープで割り当てられたメモリ ブロックのサイズを返します。

## <a name="syntax"></a>構文

```C
size_t _msize(
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
メモリ ブロックへのポインター。

## <a name="return-value"></a>戻り値

**_msize**は、サイズ (バイト単位) を符号なし整数として返します。

## <a name="remarks"></a>解説

**_msize**関数は **、calloc**、 **malloc**、または**realloc**の呼び出しによって割り当てられたメモリ ブロックのサイズをバイト単位で返します。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされると **、_msize**[は _msize_dbg](msize-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

この関数は、そのパラメーターを検証します。 *memblock*が null ポインターの場合は **、_msize**は、「[パラメーター検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 エラーが処理されると、関数は**errno**を**EINVAL**に設定し、-1 を戻します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[realloc](realloc.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[_expand](expand.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
