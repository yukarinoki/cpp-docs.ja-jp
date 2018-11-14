---
title: _get_fmode
ms.date: 11/04/2016
apiname:
- _get_fmode
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
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: dc4740b20ab7283dd8b9f73f458eaba34e582832
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328046"
---
# <a name="getfmode"></a>_get_fmode

ファイル I/O 操作の既定のファイル変換モードを取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>パラメーター

*pmode*<br/>
現在の既定のモードを格納する整数へのポインター: **_O_TEXT**または **_O_BINARY**します。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 場合*pmode*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**EINVAL**します。

## <a name="remarks"></a>Remarks

この関数は、[_fmode](../../c-runtime-library/fmode.md) グローバル変数の値を取得します。 この変数は、低レベルの両方の既定のファイル変換モードを指定しなどのファイル I/O 操作をストリーム **_open**、 **_pipe**、 **fopen**、および[freopen](freopen-wfreopen.md)します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[_set_fmode](set-fmode.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
