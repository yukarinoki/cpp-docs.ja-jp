---
description: '詳細については、次を参照してください: _CrtSetDumpClient'
title: _CrtSetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 89a2648aae62fc7f62b04519eacce4e0f67002f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319535"
---
# <a name="_crtsetdumpclient"></a>_CrtSetDumpClient

**_CLIENT_BLOCK** 型のメモリブロックをダンプするアプリケーション定義関数をインストールします (デバッグバージョンのみ)。

## <a name="syntax"></a>構文

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>パラメーター

*dumpClient*<br/>
C ランタイム デバッグ メモリ ダンプ プロセスにフックする新しいクライアント定義メモリ ダンプ関数。

## <a name="return-value"></a>戻り値

以前に定義されていたクライアント ブロック ダンプ関数を返します。

## <a name="remarks"></a>解説

**_CrtSetDumpClient** 関数を使用すると、アプリケーションは独自の関数をフックして、 **_CLIENT_BLOCK** メモリブロックに格納されているオブジェクトを C ランタイムデバッグメモリダンププロセスにダンプすることができます。 その結果、 [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) や [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) などのデバッグダンプ関数が **_CLIENT_BLOCK** メモリブロックをダンプするたびに、アプリケーションのダンプ関数も呼び出されます。 **_CrtSetDumpClient** は、メモリリークを検出し、 **_CLIENT_BLOCK** ブロックに格納されているデータの内容を検証またはレポートするための簡単な方法をアプリケーションに提供します。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_CrtSetDumpClient** の呼び出しはプリプロセス中に削除されます。

**_CrtSetDumpClient** 関数は、 *dumpclient* に指定された新しいアプリケーション定義のダンプ関数をインストールし、以前に定義したダンプ関数を返します。 クライアント ブロック ダンプ関数の例は、次のとおりです。

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*Userportion* 引数は、メモリブロックのユーザーデータ部分の先頭へのポインターであり、 *blockSize* は、割り当てられたメモリブロックのサイズをバイト数で指定します。 クライアントブロックダンプ関数は、を返す必要があり **`void`** ます。 **_CrtSetDumpClient** に渡されるクライアントダンプ関数へのポインターは、crtdbg.h で定義されている **_CRT_DUMP_CLIENT** 型です。

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

**_CLIENT_BLOCK** 型のメモリブロックを操作する関数の詳細については、「[クライアントブロックのフック関数](/visualstudio/debugger/client-block-hook-functions)」を参照してください。 ブロックの型やその細分化された型に関する情報を返すには、[_CrtReportBlockType](crtreportblocktype.md) 関数を使用できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
