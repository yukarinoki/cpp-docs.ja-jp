---
title: _CrtSetDumpClient
ms.date: 11/04/2016
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 09f319f6298dbec6b229b2923bd86fc9b50314de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342998"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

ダンプのアプリケーション定義の関数をインストール **_CLIENT_BLOCK**メモリ ブロック (デバッグ バージョンのみ) を入力します。

## <a name="syntax"></a>構文

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>パラメーター

*dumpClient*<br/>
C ランタイム デバッグ メモリ ダンプ プロセスにフックする新しいクライアント定義メモリ ダンプ関数。

## <a name="return-value"></a>戻り値

以前に定義されていたクライアント ブロック ダンプ関数を返します。

## <a name="remarks"></a>Remarks

**_CrtSetDumpClient**関数により、アプリケーションに保存されたダンプ オブジェクトの独自の関数をフックする **_CLIENT_BLOCK** C の実行時にメモリ ブロックは、メモリ ダンプ プロセスをデバッグします。 その結果、関数のダンプ デバッグには、毎回など[_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md)または[_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md)ダンプ、 **_CLIENT_BLOCK**メモリ ブロック、アプリケーションのダンプ関数が呼び出されます。 **_CrtSetDumpClient**メモリ リークの検出、検証やに格納されたデータの内容をレポートの簡単な方法でアプリケーションを提供します。 **_CLIENT_BLOCK**ブロックします。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtSetDumpClient**プリプロセス時に削除されます。

**_CrtSetDumpClient**関数で指定された新しいアプリケーション定義ダンプ関数をインストールする*dumpClient*し、以前に定義されたダンプ関数を返します。 クライアント ブロック ダンプ関数の例は、次のとおりです。

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*UserPortion*引数はメモリ ブロックのユーザー データ部分の先頭へのポインターと*blockSize* (バイト単位) のブロックを割り当てられたメモリのサイズを指定します。 クライアント ブロック ダンプ関数が返す必要があります**void**します。 渡されるクライアント ダンプ関数へのポインター **_CrtSetDumpClient**の種類は **_CRT_DUMP_CLIENT**Crtdbg.h で定義されています。

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

操作する関数の詳細については **_CLIENT_BLOCK**メモリ ブロックの型を参照してください[Client ブロック用のフック関数](/visualstudio/debugger/client-block-hook-functions)します。 ブロックの型やその細分化された型に関する情報を返すには、[_CrtReportBlockType](crtreportblocktype.md) 関数を使用できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
