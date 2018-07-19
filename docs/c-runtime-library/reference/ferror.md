---
title: ferror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- ferror
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
- ferror
dev_langs:
- C++
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49aaff776a90dd687ee4dae1902903ed01b83e20
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397370"
---
# <a name="ferror"></a>ferror

ストリームのエラーをテストします。

## <a name="syntax"></a>構文

```C
int ferror(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

エラーが発生していない場合*ストリーム*、 **ferror** 0 を返します。 それ以外の場合は、0 以外の値を返します。 ストリームが場合**NULL**、 **ferror** 」の説明に従って、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**は 0 を返します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**Ferror**ルーチン (関数とマクロの両方を実装) を読み取りまたは書き込みをエラーに関連付けられているファイルのテスト*ストリーム*です。 エラーが発生した場合、ストリームのエラー インジケーターの設定は、まで、または、ストリームが閉じているか、巻き戻され、まで**clearerr**に対して呼び出されます。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**ferror**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[feof](feof.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
