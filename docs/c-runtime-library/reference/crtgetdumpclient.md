---
description: '詳細については、次を参照してください: _CrtGetDumpClient'
title: _CrtGetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtGetDumpClient
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
- CrtGetDumpClient
- _CrtGetDumpClient
helpviewer_keywords:
- _CrtGetDumpClient function
- CrtGetDumpClient function
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
ms.openlocfilehash: b4163e6f4f252eddd304f2704c3f5a9aa62b5371
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319753"
---
# <a name="_crtgetdumpclient"></a>_CrtGetDumpClient

**_CLIENT_BLOCK** 型のメモリブロックをダンプするための現在のアプリケーション定義関数を取得します (デバッグバージョンのみ)。

## <a name="syntax"></a>構文

```C
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );
```

## <a name="return-value"></a>戻り値

現在のダンプ ルーチンを返します。

## <a name="remarks"></a>解説

**_CrtGetDumpClient** 関数は、C ランタイムデバッグメモリダンププロセス用に、 **_CLIENT_BLOCK** メモリブロックに格納されているオブジェクトをダンプするための現在のフック関数を取得します。

フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtGetDumpClient**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtSetDumpClient](crtsetdumpclient.md)<br/>
