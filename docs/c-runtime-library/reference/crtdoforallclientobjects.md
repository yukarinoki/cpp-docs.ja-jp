---
description: '詳細については、次を参照してください: _CrtDoForAllClientObjects'
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
api_name:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 73d2718aa4bfb68752a8424a385638a48aba2e36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319792"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

ヒープ内のすべての **_CLIENT_BLOCK** 型に対して、アプリケーションによって提供される関数を呼び出します (デバッグバージョンのみ)。

## <a name="syntax"></a>構文

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>パラメーター

*pfn*<br/>
アプリケーションによって提供された関数コールバック関数へのポインター。 この関数の最初のパラメーターは、データを指します。 2番目のパラメーターは、 **_CrtDoForAllClientObjects** の呼び出しに渡されるコンテキストポインターです。

*context*<br/>
アプリケーションによって提供される関数に渡す、アプリケーションによって提供されるコンテキストへのポインター。

## <a name="remarks"></a>解説

**_CrtDoForAllClientObjects** 関数は、ヒープのリンクリスト内で **_CLIENT_BLOCK** 型のメモリブロックを検索し、この型のブロックが見つかったときに、アプリケーションによって提供される関数を呼び出します。 見つかったブロックと *コンテキスト* パラメーターは、アプリケーションによって提供される関数に引数として渡されます。 デバッグ中に、アプリケーションは、デバッグヒープ関数を明示的に呼び出してメモリを割り当て、ブロックに **_CLIENT_BLOCK** ブロック型が割り当てられるように指定することで、特定の割り当てのグループを追跡できます。 これらのブロックは個別に追跡し、リーク検出やメモリ状態のレポート時に異なる方法で報告できます。

[_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグの **_CRTDBG_ALLOC_MEM_DF** ビットフィールドがオンになっていない場合、 **_CrtDoForAllClientObjects** はすぐに制御を戻します。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_CrtDoForAllClientObjects** の呼び出しはプリプロセス中に削除されます。

**_CLIENT_BLOCK** 型の詳細と、他のデバッグ関数での使用方法については、「[デバッグヒープ上のブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

*Pfn* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) は **EINVAL** に設定され、関数はを返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

**ライブラリ:** ユニバーサル C ランタイム ライブラリのデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[ヒープ状態レポート関数](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
