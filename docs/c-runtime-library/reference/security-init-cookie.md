---
description: '詳細については、次を参照してください: __security_init_cookie'
title: __security_init_cookie
ms.date: 11/04/2016
api_name:
- __security_init_cookie
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- security_init_cookie
- __security_init_cookie
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
ms.openlocfilehash: 48051eb34e7fe9fe1e32e41849072f71d6665d94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288946"
---
# <a name="__security_init_cookie"></a>__security_init_cookie

グローバル セキュリティ クッキーを初期化します。

## <a name="syntax"></a>構文

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>解説

グローバル セキュリティ クッキーは、[/GS (バッファーのセキュリティ チェック)](../../build/reference/gs-buffer-security-check.md) を指定してコンパイルされたコードおよび例外処理を使用するコードでバッファー オーバーランから保護するために使用されます。 オーバーランから保護されている関数を開始するときにクッキーはスタックに配置され、関数が終了するときにスタックの値がグローバルなクッキーと比較されます。 違いがある場合はバッファー オーバーランが発生したことを意味し、プログラムは直ちに終了します。

通常、 **__security_init_cookie** は、初期化時に CRT によって呼び出されます。 たとえば、 [/entry](../../build/reference/entry-entry-point-symbol.md) を使用してエントリポイントを指定する場合など、CRT の初期化を省略した場合は、 **__security_init_cookie** を呼び出す必要があります。 **__Security_init_cookie** が呼び出されなかった場合は、グローバルセキュリティ cookie が既定値に設定され、バッファーオーバーランによる保護が損なわれます。 攻撃者はこの既定の cookie 値を悪用してバッファーオーバーランのチェックを破ることができるため、独自のエントリポイントを定義するときは常に **__security_init_cookie** を呼び出すことをお勧めします。

オーバーランによって保護されている関数を入力する前に、 **__security_init_cookie** の呼び出しを行う必要があります。それ以外の場合は、擬似的なバッファーオーバーランが検出されます。 詳細については、「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) をご覧ください。

## <a name="example"></a>例

「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) の例をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** は、標準 C ランタイムライブラリの Microsoft 拡張機能です。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)
