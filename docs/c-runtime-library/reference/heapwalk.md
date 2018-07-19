---
title: _heapwalk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d98260ce281bc8773f597dae5897afe4beee0bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403402"
---
# <a name="heapwalk"></a>_heapwalk

ヒープを走査し、次のエントリに関する情報を返します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。ただし、デバッグ ビルドの場合は除きます。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>パラメーター

*entryinfo*<br/>
ヒープ情報を格納するバッファー。

## <a name="return-value"></a>戻り値

**_heapwalk** Malloc.h に定義されている次の整数マニフェスト定数のいずれかを返します。

|戻り値|説明|
|-|-|
|**_HEAPBADBEGIN**| 初期ヘッダー情報が無効または見つかりません。|
|**_HEAPBADNODE**| ヒープが破損しているか、不適切なノードが見つかりました。|
|**_HEAPBADPTR**| **_Pentry**のフィールド、**された _HEAPINFO**構造に、ヒープに有効なポインターが含まれていませんまたは*entryinfo* null ポインターです。|
|**_HEAPEND**| ヒープの終わりに正常に到達しました。|
|**_HEAPEMPTY**| ヒープが初期化されていません。|
|**_HEAPOK**| エラーのないところです。*entryinfo*は、次のヒープ エントリに関する情報で更新します。|

さらに、エラーが発生する場合に **_heapwalk**設定**errno**に**返る**です。

## <a name="remarks"></a>コメント

**_Heapwalk**関数は、プログラムでヒープ関連の問題をデバッグするのに役立ちます。 関数が、ヒープ、呼び出しごとに 1 つのエントリを走査する手順について説明し、型の構造体へのポインターを返します**された _HEAPINFO**次のヒープ エントリに関する情報を格納します。 **された _HEAPINFO**は、Malloc.h に定義されている型には、次の要素が含まれています。

|フィールド|説明|
|-|-|
|`int *_pentry`|ヒープ エントリのポインター。|
|`size_t _size`|ヒープ エントリのサイズ。|
|`int _useflag`|ヒープ エントリが使用中かどうかを示すフラグ。|

呼び出し **_heapwalk**を返す **_HEAPOK**内のエントリのサイズを格納、 **_size**フィールドとセット、 **_useflag**フィールドが **_FREEENTRY**または **_USEDENTRY** (両方とも Malloc.h に定義された定数です)。 このヒープ内の最初のエントリに関する情報を取得するには、渡す **_heapwalk**へのポインター、**された _HEAPINFO**構造体が **_pentry**メンバーは**NULL**. オペレーティング システムがサポートしていない場合 **_heapwalk**関数を返します (たとえば、Windows 98) **_HEAPEND**設定と**errno**に**返る**.

この関数は、そのパラメーターを検証します。 場合*entryinfo* null ポインターで説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します **_HEAPBADPTR**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
