---
title: 構造体 RUNTIME_FUNCTION
ms.date: 11/04/2016
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
ms.openlocfilehash: 6b113f6cf1e9951f9e4578e15c9ed0af3d036fa6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520251"
---
# <a name="struct-runtimefunction"></a>構造体 RUNTIME_FUNCTION

テーブルに基づく例外処理では、スタック領域の割り当てまたは別の関数 (たとえば、非リーフ関数) を呼び出すすべての関数のテーブルのエントリが必要です。 関数のテーブル エントリ フォーマットであります。

|||
|-|-|
|ULONG|関数の開始アドレス|
|ULONG|関数の終了アドレス|
|ULONG|アンワインド情報のアドレス|

RUNTIME_FUNCTION 構造体は、メモリに配置するか DWORD である必要があります。 すべてのアドレスは、イメージからの相対は、関数のテーブルのエントリを含むイメージの開始アドレスからの 32 ビットのオフセット。 これらのエントリは並べ替えられ、pe 32 + イメージの .pdata セクションに配置します。 [JIT コンパイラ] 動的に生成された関数の場合、ランタイムをこれらの関数をサポートする必要がありますまたはを使用 RtlInstallFunctionTableCallback RtlAddFunctionTable オペレーティング システムにこの情報を提供します。 これに失敗すると、信頼性の低い例外処理やプロセスのデバッグが発生します。

## <a name="see-also"></a>関連項目

[例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)