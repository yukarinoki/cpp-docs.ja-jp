---
title: 構造体 RUNTIME_FUNCTION |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f3831dc36664c556cf0a020ed87c60200443fd3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718238"
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