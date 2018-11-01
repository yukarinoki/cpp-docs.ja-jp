---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 481109a5ed7d137aa2d10c77955a2f460cba43c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507537"
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

指定された配置境界にメモリを割り当てます (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
要求されたメモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
割り当て操作が要求されたソース ファイル内の番号を行または**NULL**します。

## <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、操作に失敗しました。

## <a name="remarks"></a>Remarks

**_aligned_offset_malloc_dbg**のデバッグ バージョンです、 [_aligned_offset_malloc](aligned-offset-malloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_offset_malloc_dbg**への呼び出しに減少 **_aligned_offset_malloc**します。 両方 **_aligned_offset_malloc**と **_aligned_offset_malloc_dbg**ベースのヒープのメモリのブロックを割り当てますが、 **_aligned_offset_malloc_dbg**いくつか提供していますデバッグ機能: リーク、特定の割り当ての種類を追跡するためのブロック型パラメーターをテストする、ブロックのユーザー部分の両側のバッファーと*filename*/*linenumber*割り当て要求の起点を特定する情報。

**_aligned_offset_malloc_dbg**メモリ ブロックを要求したよりも少し多い領域を割り当てます*サイズ*します。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

**_aligned_offset_malloc_dbg** ; 入れ子になった要素の配置が必要な場合に便利ですたとえば、入れ子になったクラスに対するアラインメントが必要です。

**_aligned_offset_malloc_dbg**に基づいて**malloc**; 詳細についてを参照してください[malloc](malloc.md)します。

この関数は、設定**errno**に**ENOMEM** 、メモリの割り当てに失敗した場合、または要求されたサイズより大きい場合 **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_offset_malloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*0 以外の場合、この関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
