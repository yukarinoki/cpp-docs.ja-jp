---
title: outp、outp、_outp、_outpw、_outpd
description: Microsoft C ランタイムライブラリ (CRT) の廃止された outp、outp、_outp、_outpw、および _outpd 関数について説明します。
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: ceaaefbbe6f9debfb5ac8e1e8f5f3d1bbb36c8a8
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404061"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>outp、outp、_outp、_outpw、_outpd

ポート、バイト (、)、 `outp` `_outp` ワード ( `outpw` 、 `_outpw` )、またはダブルワード () を出力し `_outpd` ます。

> [!IMPORTANT]
> これらは古い関数です。 Visual Studio 2015 以降では、CRT では使用できません。
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
int _outp(
   unsigned short port,
   int data_byte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short data_word
);
unsigned long _outpd(
   unsigned short port,
   unsigned long data_word
);
```

### <a name="parameters"></a>パラメーター

*ポート*\
ポート番号。

*data_byte、data_word*\
出力値。

## <a name="return-value"></a>戻り値

関数は、出力データを返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

`_outp`、 `_outpw`、 `_outpd` の各関数は、指定された出力ポートへそれぞれバイト、ワード、ダブルワードを 1 つ書き込みます。 *Port*引数には、0 ~ 65535 の範囲の任意の符号なし整数を指定できます。 *data_byte* 0-255 の範囲の任意の整数を指定できます。 *data_word* 、整数、符号なし短整数、および符号なし長整数の範囲の任意の値を指定できます。

これらの関数は i/o ポートに直接書き込みを行うため、ユーザーモードの Windows コードでは使用できません。

Windows オペレーティングシステムでの i/o ポートの使用の詳細については、「 [Serial Communications](https://docs.microsoft.com/previous-versions/ff802693(v=msdn.10))」を参照してください。

`outp`との `outpw` 名前は、関数および関数の古い名前で、非推奨とされてい `_outp` `_outpw` ます。 詳細については、「 [POSIX 関数名](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

互換性について詳しくは、「 [Compatibility](../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)\
[`inp`, `inpw`, `_inp`, `_inpw`, `_inpd`](../c-runtime-library/inp-inpw-inpd.md)
