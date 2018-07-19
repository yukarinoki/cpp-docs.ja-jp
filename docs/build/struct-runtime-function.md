---
title: 構造体 RUNTIME_FUNCTION |Microsoft ドキュメント
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
ms.openlocfilehash: 3c2f28380d4a14cf7617653ede20468c45649a8b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379927"
---
# <a name="struct-runtimefunction"></a>構造体 RUNTIME_FUNCTION
テーブル ベースの例外処理では、スタック領域を割り当てるか、または別の関数 (たとえば、非リーフ関数) を呼び出すすべての関数のテーブルのエントリが必要です。 関数のテーブルのエントリではの形式があります。  
  
|||  
|-|-|  
|ULONG|関数の開始アドレス|  
|ULONG|関数の終了アドレス|  
|ULONG|アンワインド情報のアドレス|  
  
 RUNTIME_FUNCTION 構造体には、メモリ内の配置 DWORD をする必要があります。 すべてのアドレスはイメージからの相対、つまり、関数のテーブルのエントリを格納する、イメージの開始アドレスからの 32 ビット オフセットします。 これらのエントリは並べ替えられ、pe 32 + イメージの .pdata セクションに配置します。 関数 [JIT コンパイラ] の動的に生成された場合、ランタイムをこれらの関数をサポートする必要がありますまたはを使用 RtlInstallFunctionTableCallback RtlAddFunctionTable オペレーティング システムにこの情報を提供します。 信頼性の低い例外が処理され、プロセスのデバッグを行うためにエラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)