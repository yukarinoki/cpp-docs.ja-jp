---
title: '例外処理のタイミング: 概要 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f45b6ee85924106e949a7487f133b8e3fbe0b9e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465010"
---
# <a name="timing-of-exception-handling-a-summary"></a>例外処理のタイミング: 概要
終了ハンドラーの実行方法に関係なく **_ _try**ステートメント ブロックが終了します。 原因としてからのジャンプ、 **_ _try**ブロック、`longjmp`ステートメント ブロック、および例外処理によるスタックのアンワインドから制御を転送します。  
  
> [!NOTE]
>  Visual C++ は、`setjmp` ステートメントと `longjmp` ステートメントの 2 つの形式をサポートします。 高速なバージョンは終了処理をバイパスしますが、より効率的です。 このバージョンを使用するファイルをインクルード\<setjmp.h >。 もう一方のバージョンは、前の段落で説明したような終了処理をサポートします。 このバージョンを使用するファイルをインクルード\<setjmpex.h >。 高速バージョンでパフォーマンスがどの程度向上するかは、ハードウェア構成によって異なります。  
  
 オペレーティング システムは、例外ハンドラー本体を含む他のあらゆるコードを実行する前に、適切な順序ですべての終了ハンドラーを実行します。  
  
 中断の原因が例外の場合、システムは終了対象を決める前に、最初に 1 つ以上の例外ハンドラーのフィルター部分を実行する必要があります。 イベントの順序は次のとおりです。  
  
1.  例外が発生します。  
  
2.  システムは、アクティブな例外ハンドラーの階層を参照し、最も優先順位が高いハンドラーのフィルターを実行します。これは、ブロックと関数呼び出しの点から見て、最も後にインストールされ、最も深く入れ子になった例外ハンドラーです。  
  
3.  制御がこのフィルターを通過する (フィルターが 0 を返す) と、制御が通過できないフィルターが見つかるまで処理が続行されます。  
  
4.  このフィルターは、-1 を返す場合、例外が発生したし、終了を行わずに実行が続行されます。  
  
5.  フィルターが 1 を返すと、次のイベントが発生します。  
  
    -   システムは、スタックをアンワインドし、現在実行中のコード (例外が発生した場所) と制御を取得している例外ハンドラーを含むスタック フレームの間のすべてのスタック フレームをクリアします。  
  
    -   スタックがアンワインドされると、スタックの各終了ハンドラーが実行されます。  
  
    -   例外ハンドラー自体が実行されます。  
  
    -   この例外ハンドラーの末尾の後ろのコード行に制御が進みます。  
  
## <a name="see-also"></a>関連項目  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)