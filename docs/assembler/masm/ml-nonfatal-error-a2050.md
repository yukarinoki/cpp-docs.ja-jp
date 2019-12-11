---
title: ML の致命的でないエラー A2050
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 15c6449ff4207c92dee28120d4f61be641cf01c8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856578"
---
# <a name="ml-nonfatal-error-a2050"></a>ML の致命的でないエラー A2050

**実数または BCD の数値は使用できません**

データ初期化子としてではなく、浮動小数点 (実数) またはバイナリのコード化された decimal (BCD) 定数が使用されました。

次のいずれかが発生しました。

- 式で実数または BCD が使用されました。

- [DWORD](../../assembler/masm/dword.md)、 [QWORD](../../assembler/masm/qword.md)、または[t](../../assembler/masm/tbyte.md)以外のディレクティブを初期化するために実数が使用されました。

- BCD は、`TBYTE`以外のディレクティブを初期化するために使用されました。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>