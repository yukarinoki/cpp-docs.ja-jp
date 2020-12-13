---
description: '詳細については、次を参照してください: _aligned_offset_malloc_dbg'
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 1d8ae12e62ec1ea335a8bca554e07a0b64a3c3a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336546"
---
# <a name="_aligned_offset_malloc_dbg"></a>_aligned_offset_malloc_dbg

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

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*offset*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*filename*<br/>
割り当て操作を要求したソースファイルの名前へのポインターまたは **NULL**。

*linenumber*<br/>
割り当て操作が要求されたソースファイル内の行番号または **NULL**。

## <a name="return-value"></a>戻り値

割り当てられたメモリブロックへのポインター。操作が失敗した場合は **NULL** 。

## <a name="remarks"></a>解説

**_aligned_offset_malloc_dbg** は、 [_aligned_offset_malloc](aligned-offset-malloc.md) 関数のデバッグバージョンです。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_aligned_offset_malloc_dbg** の各呼び出しは **_aligned_offset_malloc** への呼び出しに限定されます。 **_Aligned_offset_malloc** と **_aligned_offset_malloc_dbg** はどちらもベースヒープにメモリブロックを割り当てますが、 **_aligned_offset_malloc_dbg** はいくつかのデバッグ機能を提供します。リークをテストするための、ブロックのユーザー部分の両側のバッファーと、割り当て要求の発生元を特定するための *filename* / *linenumber* information です。 ブロックの型パラメーターを使用して特定の割り当ての種類を追跡することは、固定された割り当てのデバッグ機能としてサポートされていません。 配置された割り当ては、_NORMAL_BLOCK ブロック型として表示されます。

**_aligned_offset_malloc_dbg** は、要求された *サイズ* よりも若干多くの領域を使用してメモリブロックを割り当てます。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

**_aligned_offset_malloc_dbg** は、入れ子になった要素にアラインメントが必要な場合に役立ちます。たとえば、入れ子になったクラスでアラインメントが必要な場合です。

**_aligned_offset_malloc_dbg** は **malloc** に基づいています。詳細については、「 [malloc](malloc.md)」を参照してください。

メモリ割り当てが失敗した場合、または要求されたサイズが **_HEAP_MAXREQ** より大きい場合、この関数は **errno** を **ENOMEM** に設定します。 **Errno** の詳細については、「 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、 **_aligned_offset_malloc** パラメーターを検証します。 *Alignment* が2の累乗でない場合、または *offset* が *size* 以上で0以外の場合、この関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **NULL** を返し、 **errno** を **EINVAL** に設定します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

割り当てブロックの型とその使用方法については、「 [デバッグヒープ上のブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
