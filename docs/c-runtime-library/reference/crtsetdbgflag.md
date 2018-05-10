---
title: _CrtSetDbgFlag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDbgFlag
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
- _CRTDBG_REPORT_FLAG
- _CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_EVERY_128_DF
- CRTDBG_CHECK_EVERY_1024_DF
- _CRTDBG_CHECK_EVERY_128_DF
- CrtSetDbgFlag
- CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_EVERY_1024_DF
- _CrtSetDbgFlag
- CRTDBG_REPORT_FLAG
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_CHECK_EVERY_16_DF macro
- CRTDBG_CHECK_EVERY_16_DF macro
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_ALLOC_MEM_DF macro
- CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_ALLOC_MEM_DF macro
- _CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_1024_DF macro
- CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_CHECK_EVERY_1024_DF macro
- _CrtSetDbgFlag function
- CrtSetDbgFlag function
- _CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 413504d8941aab1585ff03d361f8081fef4529a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag

**_crtDbgFlag** フラグの状態を取得または変更して、デバッグ ヒープ マネージャーの割り当て動作を制御します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
int _CrtSetDbgFlag(
   int newFlag
);
```

### <a name="parameters"></a>パラメーター

*されたフラグ*<br/>
**_crtDbgFlag** の新しい状態。

## <a name="return-value"></a>戻り値

**_crtDbgFlag** の以前の状態を返します。

## <a name="remarks"></a>コメント

**_CrtSetDbgFlag**関数により、アプリケーションのビット フィールドを変更することにより、デバッグ ヒープ マネージャーがメモリ割り当てを追跡する方法を制御する、 **_crtDbgFlag**フラグ。 ビットを設定する (オンにする) ことによって、アプリケーションはデバッグ ヒープ マネージャーに特別なデバッグ操作の実行を指示できます。たとえば、アプリケーション終了時にメモリ リークを確認し、リークを発見した場合に報告したり、解放されたメモリ ブロックをヒープのリンク リストに残すように指定してメモリ不足状況をシミュレーションしたり、すべての割り当て要求時に各メモリ ブロックを検査してヒープの整合性を検証したりすることができます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtSetDbgFlag**プリプロセス時に削除されます。

次の表は、**_crtDbgFlag** のビット フィールドと、その動作の説明の一覧です。 ビットを設定すると、診断出力が増加し、プログラムの実行速度が低下するため、これらのビットは既定では設定されていません (オフになっています)。 これらのビット フィールドの詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

|ビット フィールド|既定値|説明|
|---------------|-------------|-----------------|
|**_CRTDBG_ALLOC_MEM_DF**|ON|オン: を有効にするデバッグ ヒープ割り当てと、メモリ ブロック型識別子の使用など **_CLIENT_BLOCK**です。 オフ: ヒープのリンク リストに新しい割り当てを追加しますが、ブロックの型を **_IGNORE_BLOCK** に設定します。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|
|**_CRTDBG_CHECK_ALWAYS_DF**|OFF|オン: 割り当て要求および解放要求のたびに [_CrtCheckMemory](crtcheckmemory.md) を呼び出します。 オフ: **_CrtCheckMemory**明示的に呼び出す必要があります。<br /><br /> このフラグが設定されている場合、ヒープ頻度チェック マクロは効果がありません。|
|**_CRTDBG_CHECK_CRT_DF**|OFF|オン: 含める **_CRT_BLOCK**リークの検出とメモリの状態の種類の比較の操作です。 オフ: ランタイム ライブラリによって内部的に使用されるメモリは、これらの操作では無視されます。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|
|**_CRTDBG_DELAY_FREE_MEM_DF**|OFF|オン: 解放されたメモリ ブロックをヒープのリンク リストに保持し、それらに **_FREE_BLOCK** 型を割り当てて、バイト値 0xDD を設定します。 オフ: 解放されたブロックをヒープのリンク リストに保持しません。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|
|**_CRTDBG_LEAK_CHECK_DF**|OFF|オン: [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) を呼び出すことによってプログラムの終了時に自動リーク チェックを実行し、アプリケーションが割り当てたすべてのメモリを解放できなかった場合はエラー レポートを生成します。 オフ: プログラムの終了時に自動的なリーク チェックを行いません。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|

**ヒープ頻度チェック マクロ**

C ランタイム ライブラリがデバッグ ヒープの検証を実行する頻度を指定することができます (**_CrtCheckMemory**) への呼び出しの数に基づいて**malloc**、 **realloc**、 **空き**、および **_msize**です。

**_CrtSetDbgFlag**の上位 16 ビットを調べ、*されたフラグ*パラメーターの値。 指定された値の数は、 **malloc**、 **realloc**、**空き**、および **_msize**間の呼び出し **_CrtCheckMemory**呼び出しです。 この目的のために、4 つの定義済みマクロが用意されています。

|マクロ|_CrtCheckMemory の呼び出し間の malloc、realloc、free、および _msize の呼び出し数|
|-----------|------------------------------------------------------------------------------------------|
|_CRTDBG_CHECK_EVERY_16_DF|16|
|_CRTDBG_CHECK_EVERY_128_DF|128|
|_CRTDBG_CHECK_EVERY_1024_DF|1024|
|_CRTDBG_CHECK_DEFAULT_DF|0 (既定では、ヒープ チェックなし)|

既定では、 **_CrtCheckMemory** 1,024 回を呼び出す 1 回呼び出されます**malloc**、 **realloc**、**空き**、および **_msize**です。

ヒープ チェック 16 回指定するたとえば、 **malloc**、 **realloc**、**空き**、および **_msize**を次のコードの操作。

```C
#include <crtdbg.h>
int main( )
{
    int tmp;

    // Get the current bits
    tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);

    // Clear the upper 16 bits and OR in the desired freqency
    tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;

    // Set the new bits
    _CrtSetDbgFlag(tmp);
}
```

上位 16 ビット、*されたフラグ*_CRTDBG_CHECK_ALWAYS_DF が指定されている場合、パラメーターは無視されます。 この場合、 **_CrtCheckMemory**を呼び出すたびに呼び出されますが**malloc**、 **realloc**、**空き**、および **_msize**.

*されたフラグ*に適用する新しい状態は、 **_crtDbgFlag**の各ビット フィールドの値の組み合わせとします。

### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>これらのビット フィールドを変更して、フラグの新しい状態を作成するには

1. 呼び出す **_CrtSetDbgFlag**で*されたフラグ*と等しい **_CRTDBG_REPORT_FLAG**現在を取得する **_crtDbgFlag**状態にあり、保存、一時変数に返される値。

1. ビットごとのビットをオンに**または**対応するビットマスクとのアプリケーション コードではマニフェスト定数) 一時変数のです。

1. 一時変数と、適切なビットマスクのビットごとの **NOT** との **AND** 演算を行い、他のビットをオフにします。

1. 呼び出す **_CrtSetDbgFlag**で*されたフラグ*の新しい状態を設定する一時変数に格納されている値に等しい **_crtDbgFlag**です。

次の例では、メモリ不足をシミュレートする方法を維持することの条件が解放されたメモリ ブロックをヒープのリンク リストおよび防止 **_CrtCheckMemory**割り当て要求のたびに呼び出されてから。

```C
// Get the current state of the flag
// and store it in a temporary variable
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );

// Turn On (OR) - Keep freed memory blocks in the
// heap's linked list and mark them as freed
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;

// Turn Off (AND) - prevent _CrtCheckMemory from
// being called at every allocation request
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;

// Set the new state for the flag
_CrtSetDbgFlag( tmpFlag );
```

メモリ管理とデバッグ ヒープの概要については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

フラグを無効にする、 **_CrtSetDbgFlag**関数、する必要があります**AND** 、ビットごとの変数**いない**のビットマスクのです。

場合*されたフラグ*は有効な値ではありません」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**の以前の状態を返しますと **_crtDbgFlag**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetDbgFlag**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

```C
// crt_crtsetdflag.c
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug

// This program concentrates on allocating and freeing memory
// blocks to test the functionality of the _crtDbgFlag flag.

#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main( )
{
    char *p1, *p2;
    int tmpDbgFlag;

    _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );
    _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );

    // Set the debug-heap flag to keep freed blocks in the
    // heap's linked list - This will allow us to catch any
    // inadvertent use of freed memory
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;
    tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Allocate 2 memory blocks and store a string in each
    p1 = malloc( 34 );
    p2 = malloc( 38 );
    strcpy_s( p1, 34, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 38, "p2 points to a Client allocation block" );

    // Free both memory blocks
    free( p2 );
    free( p1 );

    // Set the debug-heap flag to no longer keep freed blocks in the
    // heap's linked list and turn on Debug type allocations (CLIENT)
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;
    tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Explicitly call _malloc_dbg to obtain the filename and
    // line number of our allocation request and also so we can
    // allocate CLIENT type blocks specifically for tracking
    p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );
    p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );
    strcpy_s( p1, 40, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 40, "p2 points to a Client allocation block" );

    // _free_dbg must be called to free the CLIENT block
    _free_dbg( p2, _CLIENT_BLOCK );
    free( p1 );

    // Allocate p1 again and then exit - this will leave unfreed
    // memory on the heap
    p1 = malloc( 10 );
}
```

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtCheckMemory](crtcheckmemory.md)<br/>
