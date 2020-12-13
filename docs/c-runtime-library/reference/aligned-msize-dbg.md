---
description: '詳細については、次を参照してください: _aligned_msize_dbg'
title: _aligned_msize_dbg
ms.date: 11/04/2016
api_name:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: 37b21f5992db09b1b356191263788be4516decb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335679"
---
# <a name="_aligned_msize_dbg"></a>_aligned_msize_dbg

ヒープで割り当てられたメモリ ブロックのサイズを返します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
size_t _aligned_msize_dbg(
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

*アラインメント* 値と *オフセット* 値は、ブロックを割り当てた関数に渡された値と同じである必要があります。

**_aligned_msize_dbg** は、 [_aligned_msize](aligned-msize.md) 関数のデバッグバージョンです。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_aligned_msize_dbg** の各呼び出しは **_aligned_msize** への呼び出しに限定されます。 **_Aligned_msize** と **_aligned_msize_dbg** はどちらもベースヒープ内のメモリブロックのサイズを計算しますが、デバッグ機能を追加 **_aligned_msize_dbg** ます。これには、メモリブロックのユーザー部分の両側のバッファーが、返されたサイズで含まれます。

この関数は、そのパラメーターを検証します。 *Memblock* が null ポインターであるか、または *アラインメント* が2の累乗ではない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、 **_msize** は無効なパラメーターハンドラーを呼び出します。 エラーが処理された場合、関数は **errno** を **EINVAL** に設定し、-1 を返します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロックの型とその使用方法については、「 [デバッグヒープ上のブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
