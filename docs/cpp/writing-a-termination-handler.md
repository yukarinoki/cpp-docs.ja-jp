---
description: 詳細については、「終了ハンドラーの記述」を参照してください。
title: 終了ハンドラーの記述
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
ms.openlocfilehash: a203cab7d61be66c5fe919aefe1895aa0928c5d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302986"
---
# <a name="writing-a-termination-handler"></a>終了ハンドラーの記述

例外ハンドラーとは異なり、終了ハンドラーは、コードの保護されたブロックが正常に終了したかどうかに関係なく、常に実行されます。 終了ハンドラーの唯一の目的は、コードのセクションの実行がどのように終了したかに関係なく、メモリ、ハンドル、ファイルなどのリソースが適切に閉じられるようにすることです。

終了ハンドラーは、try-finally ステートメントを使用します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [try-finally ステートメント](../cpp/try-finally-statement.md)

- [リソースの後処理](../cpp/cleaning-up-resources.md)

- [例外処理でのアクションのタイミング](../cpp/timing-of-exception-handling-a-summary.md)

- [終了ハンドラーに関する制約](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>関連項目

[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
