---
description: pragmaMicrosoft C/c + + での runtime_checks ディレクティブの詳細については、こちらを参照してください。
title: runtime_checks pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragma, runtime_checks
no-loc:
- pragma
ms.openlocfilehash: 4932126ffe33d2f8a99f6d94e3c58d2c0322df92
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712818"
---
# <a name="runtime_checks-no-locpragma"></a>`runtime_checks` pragma

コンパイラオプションの設定を無効または復元し [`/RTC`](../build/reference/rtc-run-time-error-checks.md) ます。

## <a name="syntax"></a>構文

> **`#pragma runtime_checks( "`** [ *ランタイム-チェック-オプション* ] **`",`** { **`restore`** | **`off`** } **`)`**

## <a name="remarks"></a>解説

コンパイラオプションによって有効にされていないランタイムチェックを有効にすることはできません。 たとえば、コマンドラインでを指定しない場合、を指定しても **`/RTCs`** `#pragma runtime_checks( "s", restore)` スタックフレームの検証は有効になりません。

は **`runtime_checks`** pragma 関数の外に出現する必要があり、が表示された後に定義された最初の関数で有効になり pragma ます。 **`restore`** 引数と **`off`** 引数は、で指定されたオプションをオン **`runtime_checks`** pragma またはオフにします。

*ランタイムチェックオプション* は、次の表に示すパラメーターの0個以上にすることができます。

### <a name="parameters-of-the-runtime_checks-pragma"></a>runtime_checks プラグマのパラメーター

| パラメーター | ランタイム チェックの種類 |
|--------------------|-----------------------------|
| **`s`** | スタック (フレーム) 検証を有効にします。 |
| **`c`** | より小さいデータ型に値が代入されてデータが失われる場合に報告します。 |
| **`u`** | 変数が定義される前に使用されたことを報告します。 |

これらのパラメーターは、コンパイラオプションで使用されるものと同じ **`/RTC`** です。 例:

```cpp
#pragma runtime_checks( "sc", restore )
```

を **`runtime_checks`** pragma 空の文字列 () と共に使用すること **`""`** は、ディレクティブの特殊な形式です。

- パラメーターを使用すると、 **`off`** 上記の表に一覧表示されているランタイムエラーチェックがオフになります。

- パラメーターを使用すると、 **`restore`** ランタイムエラーチェックがコンパイラオプションを使用して指定したものにリセットされ **`/RTC`** ます。

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
