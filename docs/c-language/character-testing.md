---
title: 文字テスト
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: 31a90f28d710ffc1b58f9c6b3fcfd01fd8d2d00c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523202"
---
# <a name="character-testing"></a>文字テスト

**ANSI 4.3.1** `isalnum`、`isalpha`、`iscntrl`、`islower`、`isprint`、`isupper` 関数がテストする文字セット

次の一覧は、Microsoft C コンパイラによって実装された、これらの関数について説明します。

|関数|テスト対象|
|--------------|---------------|
|`isalnum`|文字 0 - 9、A - Z、a - z、ASCII 48 - 57、65 - 90、97 - 122|
|`isalpha`|文字 A - Z、a - z、ASCII 65 - 90、97 - 122|
|`iscntrl`|ASCII 0 - 31、127|
|`islower`|文字 a - z、ASCII 97 - 122|
|`isprint`|文字 A - Z、a - z、0 - 9、句読点、スペース、ASCII 32 - 126|
|`isupper`|文字 A - Z、ASCII 65 - 90|

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)