---
title: ML の致命的でないエラー A2050 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd2e0e6c2fc818ef9286fd303c07a26bdd8b4e5a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680672"
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