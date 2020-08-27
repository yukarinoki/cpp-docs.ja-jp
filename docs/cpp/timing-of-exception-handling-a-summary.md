---
title: 例外処理のタイミング:概要
description: Microsoft C++ での例外処理のタイミングと順序。
ms.date: 08/24/2020
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
ms.openlocfilehash: 2ce501d8d74b6f0f7ca92e193c39f8ce58a66053
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898352"
---
# <a name="timing-of-exception-handling-a-summary"></a>例外処理のタイミング:概要

終了ハンドラーは、ステートメントブロックの終了方法に関係なく実行され **`__try`** ます。 原因としては、ブロックからのジャンプ **`__try`** 、 `longjmp` ブロックから制御を移すステートメント、例外処理によるスタックのアンワインドなどがあります。

> [!NOTE]
> Microsoft C++ コンパイラは、ステートメントとステートメントの2つの形式をサポートして `setjmp` `longjmp` います。 高速なバージョンは終了処理をバイパスしますが、より効率的です。 このバージョンを使用するには、ファイルを含め \<setjmp.h> ます。 もう一方のバージョンは、前の段落で説明したような終了処理をサポートします。 このバージョンを使用するには、ファイルを含め \<setjmpex.h> ます。 高速バージョンでパフォーマンスがどの程度向上するかは、ハードウェア構成によって異なります。

オペレーティング システムは、例外ハンドラー本体を含む他のあらゆるコードを実行する前に、適切な順序ですべての終了ハンドラーを実行します。

中断の原因が例外の場合、システムは終了対象を決める前に、最初に 1 つ以上の例外ハンドラーのフィルター部分を実行する必要があります。 イベントの順序は次のとおりです。

1. 例外が発生します。

1. システムは、アクティブな例外ハンドラーの階層を調べ、優先順位が最も高いハンドラーのフィルターを実行します。 これは、最近インストールされ、最も深く入れ子になった例外ハンドラーであり、ブロックと関数呼び出しによって行われます。

1. このフィルターが制御に合格した場合 (0 を返します)、制御を通過しないフィルターが見つかるまでプロセスは続行されます。

1. このフィルターが-1 を返した場合、例外が発生した場所で実行が続行され、終了は行われません。

1. フィルターが 1 を返すと、次のイベントが発生します。

   - システムは、スタックをアンワインドします。これは、例外が発生した場所と例外ハンドラーを含むスタックフレームの間のすべてのスタックフレームをクリアします。

   - スタックがアンワインドされると、スタックの各終了ハンドラーが実行されます。

   - 例外ハンドラー自体が実行されます。

   - この例外ハンドラーの末尾の後ろのコード行に制御が進みます。

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
