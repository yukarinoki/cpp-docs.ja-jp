---
title: '例外処理のタイミング: 概要'
ms.date: 05/07/2019
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 17d1c250a98afc2b86c198735602df7d80118bd4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316598"
---
# <a name="timing-of-exception-handling-a-summary"></a>例外処理のタイミング: 概要

**__try**ステートメント ブロックの終了方法に関係なく、終了ハンドラーが実行されます。 原因としては **、__try**ブロックから飛び`longjmp`出す、ブロックから制御を転送するステートメント、例外処理によるスタックのアンワインドなどがあります。

> [!NOTE]
> Microsoft C++ コンパイラは、 および`setjmp``longjmp`ステートメントの 2 つの形式をサポートします。 高速なバージョンは終了処理をバイパスしますが、より効率的です。 このバージョンを使用するには、ファイル\<setjmp.h>含めます。 もう一方のバージョンは、前の段落で説明したような終了処理をサポートします。 このバージョンを使用するには、ファイル\<setjmpex.h>を含めます。 高速バージョンでパフォーマンスがどの程度向上するかは、ハードウェア構成によって異なります。

オペレーティング システムは、例外ハンドラー本体を含む他のあらゆるコードを実行する前に、適切な順序ですべての終了ハンドラーを実行します。

中断の原因が例外の場合、システムは終了対象を決める前に、最初に 1 つ以上の例外ハンドラーのフィルター部分を実行する必要があります。 イベントの順序は次のとおりです。

1. 例外が発生します。

1. システムは、アクティブな例外ハンドラーの階層を参照し、最も優先順位が高いハンドラーのフィルターを実行します。これは、ブロックと関数呼び出しの点から見て、最も後にインストールされ、最も深く入れ子になった例外ハンドラーです。

1. 制御がこのフィルターを通過する (フィルターが 0 を返す) と、制御が通過できないフィルターが見つかるまで処理が続行されます。

1. このフィルターが -1 を返した場合、例外が発生した場所で実行が続行され、終了は行われなくなります。

1. フィルターが 1 を返すと、次のイベントが発生します。

   - システムは、スタックをアンワインドし、現在実行中のコード (例外が発生した場所) と制御を取得している例外ハンドラーを含むスタック フレームの間のすべてのスタック フレームをクリアします。

   - スタックがアンワインドされると、スタックの各終了ハンドラーが実行されます。

   - 例外ハンドラー自体が実行されます。

   - この例外ハンドラーの末尾の後ろのコード行に制御が進みます。

## <a name="see-also"></a>関連項目

[終了ハンドラーの作成](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
