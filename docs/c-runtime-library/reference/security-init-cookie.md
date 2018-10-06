---
title: __security_init_cookie | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 699a75da7829feb39142a777a34a14fcd85be653
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821137"
---
# <a name="securityinitcookie"></a>__security_init_cookie

グローバル セキュリティ クッキーを初期化します。

## <a name="syntax"></a>構文

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Remarks

グローバル セキュリティ クッキーは、[/GS (バッファーのセキュリティ チェック)](../../build/reference/gs-buffer-security-check.md) を指定してコンパイルされたコードおよび例外処理を使用するコードでバッファー オーバーランから保護するために使用されます。 オーバーランから保護されている関数を開始するときにクッキーはスタックに配置され、関数が終了するときにスタックの値がグローバルなクッキーと比較されます。 違いがある場合はバッファー オーバーランが発生したことを意味し、プログラムは直ちに終了します。

通常、 **_ _security_init_cookie**が初期化されるとき、CRT によって呼び出されます。 CRT の初期化をバイパスする場合: を使用する場合など[/ENTRY](../../build/reference/entry-entry-point-symbol.md)エントリ ポイントを指定する: 呼び出す必要がありますし、 **_ _security_init_cookie**自分でします。 場合 **_ _security_init_cookie**は呼び出されません、グローバル セキュリティ クッキーは既定値に設定され、バッファー オーバーランの保護が損なわれます。 攻撃者は、バッファー オーバーランのチェックを無効にするこの既定のクッキー値を悪用することができます、ために、常に呼び出すことが勧め **_ _security_init_cookie**エントリ ポイントを定義するとき。

呼び出し **_ _security_init_cookie**オーバーランで保護されているいずれかの前に行う必要がある関数の入力は、それ以外の場合、たとえば、見かけ上のバッファー オーバーランが検出されます。 詳細については、「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) をご覧ください。

## <a name="example"></a>例

「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) の例をご覧ください。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**_ _security_init_cookie**は標準の C ランタイム ライブラリの Microsoft 拡張です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)
