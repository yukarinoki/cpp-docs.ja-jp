---
title: ML の致命的でないエラー A2006
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2006
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
ms.openlocfilehash: 80283bde4dff36e32d276c998f6797b6eeed8160
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490065"
---
# <a name="ml-nonfatal-error-a2006"></a>ML の致命的でないエラー A2006

**未定義のシンボル: 識別子**

定義されていないシンボルの使用が試行されました。

次のいずれかが発生した可能性があります。

- シンボルが定義されていません。

- フィールドの指定された構造体のメンバーでした。

- シンボルは含まれていなかったインクルード ファイルで定義されました。

- 外部シンボルを使用していない、 [EXTERN](../../assembler/masm/extern-masm.md)または[EXTERNDEF](../../assembler/masm/externdef.md)ディレクティブ。

- シンボル名が間違っています。

- ローカル コード ラベルは、そのスコープの外部で参照されました。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>