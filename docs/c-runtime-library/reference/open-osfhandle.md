---
title: _open_osfhandle
ms.date: 4/2/2020
api_name:
- _open_osfhandle
- _o__open_osfhandle
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 9fbe4a4079fcbb8414e09d0f7dd814a3957e0822
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910673"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

C ランタイムファイル記述子を既存のオペレーティングシステムのファイルハンドルに関連付けます。

## <a name="syntax"></a>構文

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>パラメーター

*osfhandle*<br/>
オペレーティングシステムのファイルハンドル。

*flags*<br/>
許可される操作の種類。

## <a name="return-value"></a>戻り値

正常に終了した場合、**_open_osfhandle** は C ランタイム ファイル記述子を返します。 それ以外のときは -1 が返されます。

## <a name="remarks"></a>解説

**_Open_osfhandle**関数は、C ランタイムのファイル記述子を割り当てます。 このファイル記述子を、 *osfhandle*によって指定されたオペレーティングシステムのファイルハンドルに関連付けます。 コンパイラの警告を避けるには、*osfhandle* 引数を **HANDLE** から **intptr_t** にキャストします。 *flags* 引数は、\<fcntl.h> で定義された 1 つ以上のマニフェスト定数で構成された整数式です。 ビットごとの OR 演算子 ( **&#124;** ) を使用すると、2つ以上のマニフェスト定数を結合して*flags*引数を形成できます。

次のマニフェスト定数は \<fcntl.h> で定義されます。

|||
|-|-|
| **\_O\_APPEND** | 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に位置指定します。 |
| **\_O\_RDONLY** | 読み取り専用でファイルを開きます。 |
| **\_O\_テキスト** | ファイルをテキスト (変換) モードで開きます。 |
| **\_O\_WTEXT** | Unicode (UTF-16 に変換) モードでファイルを開きます。 |

**_open_osfhandle** 呼び出しは、ファイル記述子に、Win32 ファイル ハンドルの所有権を転送します。 **_open_osfhandle** を使用して開いたファイルを閉じるには、[\_close](close.md) を呼び出します。 基になる OS ファイル ハンドルも **_close** を呼び出すことで閉じます。 元のハンドルで Win32 関数 **CloseHandle** を呼び出さないでください。 ファイル記述子がファイル **&#42;** ストリームによって所有されている場合、 [fclose](fclose-fcloseall.md)を呼び出すと、ファイル記述子と基になるハンドルの両方が閉じられます。 この場合、**_close** をファイル記述子で呼び出したり、元のハンドルで **CloseHandle** を呼び出したりしないでください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
