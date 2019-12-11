---
title: ML の致命的なエラー A1007
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 01633b4fa084b7d5e14af5a5c6e51e3dca684d2a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856918"
---
# <a name="ml-fatal-error-a1007"></a>ML の致命的なエラー A1007

**入れ子レベルが深すぎます**

アセンブラーが入れ子の制限に達しました。 特に明記されていない限り、制限は20レベルです。

次のいずれかの入れ子のレベルが深すぎます。

- などの高レベルのディレクティブ[。の場合は](../../assembler/masm/dot-if.md) [。](../../assembler/masm/dot-repeat.md)またはを繰り返し[ます。しばらくお待ち](../../assembler/masm/dot-while.md)ください。

- 構造体の定義。

- 条件付きアセンブリディレクティブ。

- プロシージャの定義。

- [Pushcontext](../../assembler/masm/pushcontext.md)ディレクティブ (制限は 10)。

- セグメントの定義。

- インクルードファイル。

- マクロ。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>