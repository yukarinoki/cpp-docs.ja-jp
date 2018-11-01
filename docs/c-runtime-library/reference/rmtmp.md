---
title: _rmtmp
ms.date: 11/04/2016
apiname:
- _rmtmp
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rmtmp
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: bf4f2cff48e8660682fc8a00d10d9a1fe960a6a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508889"
---
# <a name="rmtmp"></a>_rmtmp

一時ファイルの削除を削除します。

## <a name="syntax"></a>構文

```C

int _rmtmp( void );
```

## <a name="return-value"></a>戻り値

**_rmtmp**閉じられ削除された一時ファイルの数を返します。

## <a name="remarks"></a>Remarks

**_Rmtmp**関数は、現在のディレクトリ内のすべての一時ファイルをクリーンアップします。 関数によって作成されたファイルのみを削除します**tmpfile**; 一時ファイルが作成された同じディレクトリ内でのみ使用します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_rmtmp**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[tmpfile](tmpfile.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
