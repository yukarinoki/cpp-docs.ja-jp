---
title: ML の致命的なエラー A1007 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 539ab431510d5dc721e6531c11069a87e27c287a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693602"
---
# <a name="ml-fatal-error-a1007"></a>ML の致命的なエラー A1007

**入れ子のレベルが深すぎます**

アセンブラーでは、その入れ子の上限に達しました。 制限は、20 のレベルを明記します。

次のいずれかの入れ子が深すぎます。

- などの高度なディレクティブ[します。IF](../../assembler/masm/dot-if.md)、[します。繰り返し](../../assembler/masm/dot-repeat.md)、または[します。中に](../../assembler/masm/dot-while.md)します。

- 構造体の定義。

- 条件付きのアセンブリ ディレクティブ。

- プロシージャの定義。

- A [PUSHCONTEXT](../../assembler/masm/pushcontext.md)ディレクティブ (上限は 10)。

- セグメントの定義。

- インクルード ファイル。

- マクロ。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>