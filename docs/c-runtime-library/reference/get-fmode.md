---
title: _get_fmode
ms.date: 4/2/2020
api_name:
- _get_fmode
- _o__get_fmode
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: fbaa30d0842400037f37508df94726f3e7fd7090
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345169"
---
# <a name="_get_fmode"></a>_get_fmode

ファイル I/O 操作の既定のファイル変換モードを取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>パラメーター

*Pmode*<br/>
現在の既定モード **(_O_TEXT**または **_O_BINARY)** で入力される整数へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 *pmode*が**NULL**の場合は、「パラメータ[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され、関数は**EINVAL**を返します。

## <a name="remarks"></a>解説

この関数は、[_fmode](../../c-runtime-library/fmode.md) グローバル変数の値を取得します。 この変数は **、_open**、 **_pipe**、 **fopen**、 [freopen](freopen-wfreopen.md)などの低レベルおよびストリーム・ファイル入出力操作のデフォルト・ファイル変換モードを指定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

[_set_fmode](set-fmode.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[テキストおよびバイナリ モード ファイル I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
