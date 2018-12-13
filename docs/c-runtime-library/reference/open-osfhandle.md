---
title: _open_osfhandle
ms.date: 05/29/2018
apiname:
- _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: f45ca46cae459c8606f88a98d03b64c40e5d5f01
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327864"
---
# <a name="openosfhandle"></a>_open_osfhandle

C ランタイム ファイル記述子を既存のオペレーティング システムのファイル ハンドルに関連付けます。

## <a name="syntax"></a>構文

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>パラメーター

*osfhandle*<br/>
オペレーティング システムのファイル ハンドル。

*flags*<br/>
許可される操作の種類。

## <a name="return-value"></a>戻り値

成功した場合、 **_open_osfhandle** C ランタイム ファイル記述子を返します。 それ以外の場合、-1 を返します。

## <a name="remarks"></a>Remarks

**_Open_osfhandle**関数が C ランタイム ファイル記述子を割り当てますで指定されたオペレーティング システム ファイル ハンドルに関連付けます*osfhandle*します。 コンパイラの警告を避けるためには、キャスト、 *osfhandle*から引数**処理**に**intptr_t**します。 *フラグ*引数が 1 つから形成される整数式または複数のマニフェスト定数で定義されている\<fcntl.h >。 フォームに 2 つ以上のマニフェスト定数を使用する場合、*フラグ*引数、定数はビットごとの OR 演算子で組み合わされます ( **&#124;** )。

これらのマニフェスト定数が定義されている\<fcntl.h >:

|||
|-|-|
| **\_O\_追加** | 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に位置指定します。 |
| **\_O\_RDONLY** | 読み取り専用でファイルを開きます。 |
| **\_O\_TEXT** | ファイルをテキスト (変換) モードで開きます。 |
| **\_O\_WTEXT** | Unicode (UTF-16 に変換) モードでファイルを開きます。 |

**_Open_osfhandle**呼び出しは、ファイル記述子に、Win32 ファイル ハンドルの所有権を転送します。 開かれたファイルを閉じる **_open_osfhandle**、呼び出す[\_閉じます](close.md)します。 呼び出しによって基になる OS ファイル ハンドルが閉じられたも **_close**Win32 関数を呼び出す必要はありませんので、 **CloseHandle**元のハンドル。 ファイル記述子が所有している場合、**ファイル&#42;** 呼び出してストリーム[fclose](fclose-fcloseall.md)を**ファイル&#42;** ストリームは、ファイル記述子も閉じられます、基になるハンドル。 この場合、呼び出さない **_close**ファイル記述子。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
