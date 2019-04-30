---
title: _aligned_msize_dbg
ms.date: 11/04/2016
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: 054f7b88f93eef37a9a88fbb7895452f7c158716
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342036"
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

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

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

符号なし整数としてサイズ (バイト数) を返します。

## <a name="remarks"></a>Remarks

*配置*と*オフセット*値は、ブロックを割り当てた関数に渡される値と同じである必要があります。

**_aligned_msize_dbg**のデバッグ バージョンです、 [_aligned_msize](aligned-msize.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_msize_dbg**への呼び出しに減少 **_aligned_msize**します。 両方 **_aligned_msize**と **_aligned_msize_dbg**ベースのヒープにメモリ ブロックのサイズの計算が **_aligned_msize_dbg**デバッグ機能を追加します。返されるサイズでは、メモリ ブロックのユーザー部分の両側のバッファーが含まれます。

この関数は、そのパラメーターを検証します。 場合 *_expand* null ポインターまたは*配置*が 2 の累乗でない **_msize**で説明されているように、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 関数は、エラーが処理される場合、設定**errno**に**EINVAL** -1 を返します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
