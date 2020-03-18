---
title: _rmtmp
ms.date: 11/04/2016
api_name:
- _rmtmp
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: de28768f479df00eae315c99b80103c5319b38af
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442786"
---
# <a name="_rmtmp"></a>_rmtmp

一時ファイルの削除を削除します。

## <a name="syntax"></a>構文

```C

int _rmtmp( void );
```

## <a name="return-value"></a>戻り値

**_rmtmp**は、終了して削除された一時ファイルの数を返します。

## <a name="remarks"></a>コメント

**_Rmtmp**関数は、現在のディレクトリ内のすべての一時ファイルをクリーンアップします。 関数は、 **tmpfile**によって作成されたファイルのみを削除します。一時ファイルが作成されたディレクトリと同じディレクトリ内でのみ使用してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_rmtmp**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[tmpfile](tmpfile.md)」の例をご覧ください。

## <a name="see-also"></a>参照

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
