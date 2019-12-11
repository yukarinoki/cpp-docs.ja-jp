---
title: ML の致命的でないエラー A2085
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3bd89fb2b7f8b755cdb095e63ed89386332ecf9d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855759"
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085

**命令またはレジスタは現在の CPU モードで受け入れられません**

現在のプロセッサモードに対して無効な命令、レジスタ、またはキーワードを使用しようとしました。

たとえば、32ビットレジスタでは、 [386](../../assembler/masm/dot-386.md)以上が必要です。 CR0 レジスタなどのコントロールレジスタでは、特権モードが必要[です。 386p](../../assembler/masm/dot-386p.md)以降。 このエラーは、を必要とする**NEAR32**、 **FAR32**、および**FLAT**キーワードに対しても生成されます。**386**以上。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>