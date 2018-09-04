---
title: ML の致命的なエラー A1010 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12b7e8698951e8ef59e0433134ec992af5d5f77f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676298"
---
# <a name="ml-fatal-error-a1010"></a>ML の致命的なエラー A1010

**比類のないブロックの入れ子。**

ブロックの先頭に、対応する end がないか、ブロックの終了を開始に対応するありませんでした。 次のいずれかが含まれます。

- などの高度なディレクティブ[します。IF](../../assembler/masm/dot-if.md)、[します。繰り返し](../../assembler/masm/dot-repeat.md)、または[します。中に](../../assembler/masm/dot-while.md)します。

- などの条件付きのアセンブリ ディレクティブ[場合](../../assembler/masm/if-masm.md)、[繰り返します](../../assembler/masm/repeat.md)、または**中**します。

- 構造体または共用体の定義。

- プロシージャの定義。

- セグメントの定義。

- A [POPCONTEXT](../../assembler/masm/popcontext.md)ディレクティブ。

- 条件付きアセンブリなど、ディレクティブ、 [ELSE](../../assembler/masm/else-masm.md)、 [ELSEIF](../../assembler/masm/elseif-masm.md)、または**ENDIF** 、一致することがなく[場合](../../assembler/masm/if-masm.md)。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>