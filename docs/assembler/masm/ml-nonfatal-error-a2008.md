---
title: ML の致命的でないエラー A2008 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 774cf4c2a51bf084fb63e572cc99b0c8e3cba26f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679376"
---
# <a name="ml-nonfatal-error-a2008"></a>ML の致命的でないエラー A2008

**構文エラー:**

現在の場所にあるトークンには、構文エラーが発生しました。

次のいずれかが発生した可能性があります。

- ドット プレフィックスに追加またはディレクティブから省略するとします。

- 予約語 (など**C**または**サイズ**) 識別子として使用されました。

- 現在のプロセッサまたはコプロセッサの選択で提供されていなかった命令が使用されました。

- 実行時の比較演算子 (など`==`) 関係演算子ではなく、アセンブリの条件付きステートメントで使用された (など[EQ](../../assembler/masm/operator-eq.md))。

- 命令またはディレクティブもいくつかのオペランドが指定されました。

- 古い形式のディレクティブが使用されました。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>