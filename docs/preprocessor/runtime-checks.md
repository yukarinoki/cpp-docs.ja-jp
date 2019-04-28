---
title: runtime_checks
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 44c26fb90a2d2f9ba78ec7dba7cceed65a4b4ed7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179985"
---
# <a name="runtimechecks"></a>runtime_checks
[/RTC](../build/reference/rtc-run-time-error-checks.md) 設定を無効化または復元します。

## <a name="syntax"></a>構文

```
#pragma runtime_checks( "[runtime_checks]", {restore | off} )
```

## <a name="remarks"></a>Remarks

コンパイラ オプションで有効になっていないランタイム チェックを有効にすることはできません。 たとえば、指定しない場合`/RTCs`を指定して`#pragma runtime_checks( "s", restore)`スタック フレームの検証が有効になりません。

**runtime_checks** プラグマは関数の外に表示する必要があり、プラグマが発生した後に定義される最初の関数で適用されます。 *restore* 引数と *off* 引数は **runtime_checks** で指定するオプションのオンとオフを切り替えます。

**runtime_checks** には、次の表に示すパラメーターの 0 個以上を指定できます。

### <a name="parameters-of-the-runtimechecks-pragma"></a>runtime_checks プラグマのパラメーター

|パラメーター|ランタイム チェックの種類|
|--------------------|-----------------------------|
|*s*|スタック (フレーム) 検証を有効にします。|
|*c*|より小さいデータ型に値が代入されてデータが失われる場合に報告します。|
|*u*|定義する前に変数が使用された場合に報告します。|

使用される同じ文字のうち、`/RTC`コンパイラ オプション。 例:

```
#pragma runtime_checks( "sc", restore )
```

空の文字列 ( **""** ) での**runtime_checks**プラグマの使用は、ディレクティブの特殊な形式です。

- *off* パラメーターを使用すると、このトピックの前の表で示したランタイム エラー チェックがオフになります。

- 使用すると、*復元*パラメーターを実行時エラー チェックにリセットされますを指定した、`/RTC`コンパイラ オプション。

```
#pragma runtime_checks( "", off )
.
.
.
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)