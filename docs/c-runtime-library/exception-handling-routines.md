---
description: 詳細については、「例外処理ルーチン」を参照してください。
title: 例外処理ルーチン
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: d241c3ef7f32a96f08d4ad499887963fda031967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331093"
---
# <a name="exception-handling-routines"></a>例外処理ルーチン

C++ 例外処理関数を利用し、プログラム実行中の予想外のイベントから復旧します。

## <a name="exception-handling-functions"></a>例外処理関数

|機能|使用|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 (C 構造化例外) を C++ 型指定例外として処理する|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|**terminate** によって呼び出される独自の終了ルーチンをインストールする|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|**unexpected** によって呼び出される独自の終了関数をインストールする|
|[解約](../c-runtime-library/reference/terminate-crt.md)|例外がスローされた後、特定の状況下で自動的に呼び出されます。 **terminate** 関数は、**abort** または **set_terminate** で指定した関数を呼び出します|
|[不適切](../c-runtime-library/reference/unexpected-crt.md)|**terminate** を呼び出すか、または **set_unexpected** を使用して指定した関数を呼び出します。 **unexpected** 関数は現在の Microsoft C++ 例外処理の実装では使用されません|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
