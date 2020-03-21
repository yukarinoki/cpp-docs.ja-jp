---
title: fflush
ms.date: 09/11/2019
api_name:
- fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: 4597a013054a549047b4467c5bfed605e55e7656
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077340"
---
# <a name="fflush"></a>fflush

ストリームをフラッシュします。

## <a name="syntax"></a>構文

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fflush**は、バッファーが正常にフラッシュされた場合に0を返します。 指定したストリームにバッファーがないか、読み取り専用で開かれる場合にも、値 0 が返されます。 **EOF**の戻り値はエラーを示します。

> [!NOTE]
> **Fflush**が**EOF**を返す場合、書き込みエラーによってデータが失われている可能性があります。 重大なエラーハンドラーを設定するときは、 **setvbuf**関数でバッファリングを無効にするか、ストリーム i/o 関数の代わりに **_open**、 **_close**、 **_write**などの低レベルの i/o ルーチンを使用することが最も安全です。

## <a name="remarks"></a>解説

**Fflush**関数は、ストリーム*ストリーム*をフラッシュします。 書き込みモードでストリームを開いた場合、または更新モードで開き、最後の操作が書き込みだった場合、基になるファイルまたはデバイスにストリーム バッファーの内容が書き込まれ、バッファーは破棄されます。 ストリームが読み取りモードで開かれた場合、またはストリームにバッファーがない場合、 **fflush**を呼び出すと無効になり、すべてのバッファーが保持されます。 **Fflush**を呼び出すと、ストリームの**ungetc**に対する以前の呼び出しの効果が否定されます。 呼び出し後もストリームは開いたままになります。

*ストリーム*が**NULL**の場合、動作は、開いている各ストリームでの**fflush**の呼び出しと同じです。 書き込みモードで開いたすべてのストリームと、更新モードで開いて最後の操作が書き込みだったすべてのストリームは、フラッシュされます。 この呼び出しは、他のストリームに影響がありません。

バッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。 ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 プログラムのオブジェクト ファイルを COMMODE.OBJ にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。 生成された実行可能ファイルでは、を呼び出して、すべてのバッファーの内容をディスクに書き込み **_flushall**ます。 COMMODE .OBJ によって影響を受けるのは、 **_flushall**と**fflush**だけです。

ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](fopen-wfopen.md)」、および「[_fdopen](fdopen-wfdopen.md)」を参照してください。

この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「 **_fflush_nolock**」を参照してください。

## <a name="requirements"></a>必要条件

|Function|必須ヘッダー|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fflush.c
// Compile with: cl /W4 crt_fflush.c
// This sample gets a number from the user, then writes it to a file.
// It ensures the write isn't lost on crash by calling fflush.
#include <stdio.h>

int * crash_the_program = 0;

int main(void)
{
    FILE * my_file;
    errno_t err = fopen_s(&my_file, "myfile.txt", "w");
    if (my_file && !err)
    {
        printf("Write a number: ");

        int my_number = 0;
        scanf_s("%d", &my_number);

        fprintf(my_file, "User selected %d\n", my_number);

        // Write data to a file immediately instead of buffering.
        fflush(my_file);

        if (my_number == 5)
        {
            // Without using fflush, no data was written to the file
            // prior to the crash, so the data is lost.
            *crash_the_program = 5;
        }

        // Normally, fflush is not needed as closing the file will write the buffer.
        // Note that files are automatically closed and flushed during normal termination.
        fclose(my_file);
    }
    return 0;
}
```

```Input
5
```

```myfile.txt
User selected 5
```

## <a name="see-also"></a>参照

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
