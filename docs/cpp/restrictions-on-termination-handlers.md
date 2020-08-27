---
title: 終了ハンドラーに関する制約
description: 構造化例外処理の終了ハンドラーに関する制限。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 60fdb4c2a105f2fce4a32f475563a04f8e7bfaf9
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898273"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約

ステートメントを使用して、ステートメント **`goto`** **`__try`** ブロックまたはステートメントブロックに移動することはできません **`__finally`** 。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (ただし、ステートメントブロックからジャンプでき **`__try`** ます)。また、ブロック内の例外ハンドラーまたは終了ハンドラーを入れ子にすることはできません **`__finally`** 。

終了ハンドラーで許可されている一部の種類のコードでは、問題のある結果が生成されるため、慎重に使用する必要があります。 1つは、 **`goto`** ステートメントブロックからジャンプするステートメントです **`__finally`** 。 ブロックが通常の終了の一部として実行される場合、異常は発生しません。 しかし、システムがスタックをアンワインドしている場合は、アンワインドが停止します。 その後、現在の関数は、異常終了しなかったかのようにコントロールを取得します。

ステートメント **`return`** ブロック内のステートメントは **`__finally`** 、ほぼ同じ状況を示します。 コントロールは、終了ハンドラーを含む関数の直前の呼び出し元に戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止されます。 次に、例外が発生しなかったかのようにプログラムが続行されます。

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
