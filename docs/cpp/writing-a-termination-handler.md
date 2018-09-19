---
title: 終了ハンドラーの記述 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85241d9dde87e929b02328a6e7d0c75b5ce068ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116231"
---
# <a name="writing-a-termination-handler"></a>終了ハンドラーの記述

例外ハンドラーとは異なり、終了ハンドラーは、コードの保護されたブロックが正常に終了したかどうかに関係なく、常に実行されます。 終了ハンドラーの唯一の目的は、コードのセクションの実行がどのように終了したかに関係なく、メモリ、ハンドル、ファイルなどのリソースが適切に閉じられるようにすることです。

終了ハンドラーは、try-finally ステートメントを使用します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [Try-finally ステートメント](../cpp/try-finally-statement.md)

- [リソースをクリーンアップします。](../cpp/cleaning-up-resources.md)

- [例外の処理アクションのタイミング](../cpp/timing-of-exception-handling-a-summary.md)

- [終了ハンドラーに関する制約](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>関連項目

[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)