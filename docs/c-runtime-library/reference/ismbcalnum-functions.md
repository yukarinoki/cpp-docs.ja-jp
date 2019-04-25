---
title: _ismbcalnum、_ismbcalnum_l、_ismbcalpha、_ismbcalpha_l、_ismbcdigit、_ismbcdigit_l
ms.date: 11/04/2016
apiname:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
ms.openlocfilehash: 1a2f928d826b70b788220130f69c53cc351b4910
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157306"
---
# <a name="ismbcalnum-ismbcalnuml-ismbcalpha-ismbcalphal-ismbcdigit-ismbcdigitl"></a>_ismbcalnum、_ismbcalnum_l、_ismbcalpha、_ismbcalpha_l、_ismbcdigit、_ismbcdigit_l

マルチバイト文字が英数字、英字、または数字であるかどうかをチェックします。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _ismbcalnum
(
   unsigned int c
);
int _ismbcalnum_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcalpha
(
   unsigned int c
);
int _ismbcalpha_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcdigit
(
   unsigned int c
);
int _ismbcdigit_l
(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 場合*c*< = 255 は、対応する **_ismbb 系**ルーチン (たとえば、 **_ismbcalnum**に対応する **_ismbbalnum**)、結果は、戻り値に対応する **_ismbb 系**ルーチン。

## <a name="remarks"></a>Remarks

これらの各ルーチンは特定の条件で特定のマルチバイト文字をテストします。

これらの関数のバージョン、 **_l**ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用することを除き、サフィックスは同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

|ルーチンによって返される値|テスト条件|コード ページ 932 の例|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**、 **_ismbcalnum_l**|英数字|場合にのみ、0 以外の値を返します*c* ASCII の英字の 1 バイト表現です。例を参照してください。 **_ismbcdigit**と **_ismbcalpha**します。|
|**_ismbcalpha**、 **_ismbcalpha_l**|alphabetic|場合にのみ、0 以外の値を返します*c* ASCII の英字の 1 バイト表現です。0x41 < =*c*< = 0x5A または 0x61 < =*c*< = 0x7A; またはカタカナの文字。0xA6<=*c*<=0xDF.|
|**_ismbcdigit**, **_ismbcdigit**|数字|場合にのみ、0 以外の値を返します*c* ASCII 数字の 1 バイト表現です。0x30<=*c*<=0x39.|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ismbcalnum**、 **_ismbcalnum_l**|\<mbstring.h>|
|**_ismbcalpha**、 **_ismbcalpha_l**|\<mbstring.h>|
|**_ismbcdigit**、 **_ismbcdigit_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
