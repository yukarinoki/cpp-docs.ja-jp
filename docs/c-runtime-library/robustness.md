---
title: 保全性
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 9244ba430efab01cd82b8ad773ad669470d67cff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454705"
---
# <a name="robustness"></a>保全性

プログラムの信頼性を向上させるには、次の C ランタイム ライブラリ関数を使用します。

## <a name="run-time-robustness-functions"></a>ランタイムの信頼性関数

|関数|使用|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|**new** 演算子がメモリの割り当てに失敗した場合は、独自のエラー処理機構に制御を移します。|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 (C 構造化例外) を C++ 型指定例外として処理します。|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[terminate](../c-runtime-library/reference/terminate-crt.md) によって呼び出される独自の終了関数をインストールします。|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[unexpected](../c-runtime-library/reference/unexpected-crt.md) によって呼び出される独自の終了関数をインストールします。|

## <a name="see-also"></a>参照

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](https://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
