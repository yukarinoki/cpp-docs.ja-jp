---
title: _inp、_inpw、_inpd
ms.date: 11/04/2016
api_name:
- _inp
- _inpw
- _inpd
api_location:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
ms.openlocfilehash: 4668002fdf709e3e425ac379f136e228250896d4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944992"
---
# <a name="_inp-_inpw-_inpd"></a>_inp、_inpw、_inpd

ポートから 1 バイト (`_inp`)、1 ワード (`_inpw`)、または 1 ダブルワード (`_inpd`) のいずれかを読み込みます。

> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。

> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```
int _inp(
   unsigned short port
);
unsigned short _inpw(
   unsigned short port
);
unsigned long _inpd(
   unsigned short port
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
I/O ポート番号。

## <a name="return-value"></a>戻り値

これらの関数は、 `port`から読み込んだバイト、ワード、またはダブルワードを返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

`_inp`、 `_inpw`、 `_inpd` の各関数は、指定された入力ポートからそれぞれバイト、ワード、ダブルワードを 1 つ読み込みます。 ポート番号として、0 - 65,535 の unsigned short 型整数を入力できます。

これらの関数は I/O ポートから直接読み込まれるため、ユーザー コードで使用できません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`_inp`|\<conio.h>|
|`_inpw`|\<conio.h>|
|`_inpd`|\<conio.h>|

互換性の詳細については、「 [互換性](../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)<br/>
[_outp、_outpw、_outpd](../c-runtime-library/outp-outpw-outpd.md)
