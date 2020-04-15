---
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2d5d4e224b39e9fa597e12975d27fa5720fbfbc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345255"
---
# <a name="_get_doserrno"></a>_get_doserrno

オペレーティング システムが**errno**値に変換される前に返されたエラー値を取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
**_doserrno**グローバル マクロの現在の値を格納する整数へのポインター。

## <a name="return-value"></a>戻り値

**_get_doserrno**成功すると、ゼロが返されます。失敗した場合は、エラー コードを返します。 *pValue*が**NULL**の場合は、「パラメータ[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

## <a name="remarks"></a>解説

**_doserrno**グローバル・マクロは、CRT の初期化時に、プロセスの実行が開始される前にゼロに設定されます。 オペレーティング システム エラーを返すシステム レベルの関数呼び出しによって返されたオペレーティング システム エラー値に設定され、実行中に 0 にリセットされることはありません。 関数から返されるエラー値をチェックするコードを記述する場合は、関数呼び出しの前に[_set_doserrno](set-doserrno.md)を使用して **、常に_doserrno**をオフにします。 別の関数呼び出しによって_doserrnoが上書きされる可能性があるため **、** 関数呼び出しの直後に **_get_doserrno**を使用して値を確認します。

移植性[_get_errno](get-errno.md)の高いエラー コードの代わりに **_get_errnoを_get_doserrno**することをお勧めします。

**_doserrno**の値は errno.h>で\<定義されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>、\<cstdlib> (C++)|\<errno.h>、\<cerrno> (C++)|

**_get_doserrno**はマイクロソフトの拡張機能です。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_set_doserrno](set-doserrno.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
