---
title: vfscanf、vfwscanf
ms.date: 11/04/2016
apiname:
- vfwscanf
- vfscanf
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
- vfwscanf
- _vftscanf
- vfscanf
ms.assetid: c06450ef-03f1-4d24-a8ac-d2dd98847918
ms.openlocfilehash: 3076f63e05e156a479372adfca9dc707255f9e6a
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521506"
---
# <a name="vfscanf-vfwscanf"></a>vfscanf、vfwscanf

ストリームから書式化されたデータを読み出します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[vfscanf_s、vfwscanf_s](vfscanf-s-vfwscanf-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int vfscanf(
   FILE *stream,
   const char *format,
   va_list argptr
);
int vfwscanf(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*format*<br/>
書式指定文字列。

*arglist*<br/>
可変個引数リスト。

## <a name="return-value"></a>戻り値

これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 エラーが発生した場合、または戻り値は、ファイル ストリームの末尾に達した場合は、最初の変換の前に、 **EOF**の**vfscanf**と**vfwscanf**します。

これらの関数では、パラメーターの検証が行われます。 場合*ストリーム*または*形式*null ポインターの場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EOF**設定と**errno**に**EINVAL**します。

## <a name="remarks"></a>Remarks

**Vfscanf**関数は、の現在位置からデータを読み取る*ストリーム*で指定されている場所に、 *arglist*引数リスト。 リスト内の各引数は型指定子に対応する型の変数へのポインターである必要があります*形式*します。 *形式*コントロール入力の解釈のフィールドし、同じ形式し、機能、*形式*引数**scanf**; を参照してください[scanf](scanf-scanf-l-wscanf-wscanf-l.md)の説明*形式*します。

**vfwscanf**のワイド文字バージョンは、 **vfscanf**; 引数 format **vfwscanf**はワイド文字列です。 ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。 **vfscanf** UNICODE ストリームからの入力をサポートしていません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf**|**vfscanf**|**vfscanf**|**vfwscanf**|

詳細については、「[Format Specification Fields: scanf and wscanf Functions](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」(scanf 関数と wscanf 関数の書式指定フィールド) をご覧ください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**vfscanf**|\<stdio.h>|
|**vfwscanf**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_vfscanf.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses vfscanf to
// read the various data back from the file.

#include <stdio.h>
#include <stdarg.h>

FILE *stream;

int call_vfscanf(FILE * istream, char * format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vfscanf(istream, format, arglist);
    va_end(arglist);
    return result;
}

int main(void)
{
    long l;
    float fp;
    char s[81];
    char c;

    if (fopen_s(&stream, "vfscanf.out", "w+") != 0)
    {
        printf("The file vfscanf.out was not opened\n");
    }
    else
    {
        fprintf(stream, "%s %ld %f%c", "a-string",
            65000, 3.14159, 'x');
        // Security caution!
        // Beware loading data from a file without confirming its size,
        // as it may lead to a buffer overrun situation.

        // Set pointer to beginning of file:
        fseek(stream, 0L, SEEK_SET);

        // Read data back from file:
        call_vfscanf(stream, "%s %ld %f%c", s, &l, &fp, &c);

        // Output data read:
        printf("%s\n", s);
        printf("%ld\n", l);
        printf("%f\n", fp);
        printf("%c\n", c);

        fclose(stream);
    }
}
```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf、_cscanf_l、_cwscanf、_cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[fscanf_s、_fscanf_s_l、fwscanf_s、_fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
[vfscanf_s、vfwscanf_s](vfscanf-s-vfwscanf-s.md)<br/>
