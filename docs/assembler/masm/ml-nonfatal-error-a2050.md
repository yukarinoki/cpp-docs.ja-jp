---
title: ML の致命的でないエラー A2050
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 59d08b9c2743a3b45633527bcc54b3e1c4d6a58c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439716"
---
# <a name="ml-nonfatal-error-a2050"></a>ML の致命的でないエラー A2050

**リアルタイムまたは 10 進数を許可されていません**

(実際) の浮動小数点数またはバイナリのコード化された 10 進数 (BCD) の定数が他にも使用されたデータの初期化子として。

次のいずれかが発生しました。

- 実数値または BCD は、式で使用されました。

- 以外のディレクティブを初期化するために使用された実数[DWORD](../../assembler/masm/dword.md)、 [QWORD](../../assembler/masm/qword.md)、または[TBYTE](../../assembler/masm/tbyte.md)します。

- BCD は以外のディレクティブを初期化するために使用された`TBYTE`します。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>