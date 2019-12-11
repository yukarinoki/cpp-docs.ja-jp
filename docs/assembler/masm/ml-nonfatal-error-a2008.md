---
title: ML の致命的でないエラー A2008
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2008
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
ms.openlocfilehash: 192d82186a58d4e6b534ab5ec65b696d4d7ce3ee
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856754"
---
# <a name="ml-nonfatal-error-a2008"></a>ML の致命的でないエラー A2008

**構文エラー:**

現在の場所のトークンによって構文エラーが発生しました。

次のいずれかが発生している可能性があります。

- ディレクティブにドットプレフィックスが追加されたか、ディレクティブから省略されました。

- 予約語 ( **C**や**サイズ**など) が識別子として使用されました。

- 現在のプロセッサまたはコプロセッサ選択で使用できなかった命令が使用されました。

- 比較実行時演算子 (`==`など) が、関係演算子 ( [EQ](../../assembler/masm/operator-eq.md)など) ではなく、条件付きアセンブリステートメントで使用されました。

- 命令またはディレクティブに指定されたオペランドが少なすぎます。

- Obsolete ディレクティブが使用されました。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>