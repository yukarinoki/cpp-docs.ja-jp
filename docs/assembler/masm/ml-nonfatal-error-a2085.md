---
description: '詳細情報: ML の致命的でないエラー A2085'
title: ML の致命的でないエラー A2085
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3a2cd89b373f761beb3fc0de01a1bea3ec7bf82e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128546"
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085

**命令またはレジスタは現在の CPU モードで受け入れられません**

現在のプロセッサモードに対して無効な命令、レジスタ、またはキーワードを使用しようとしました。

たとえば、32ビットレジスタでは、 [386](dot-386.md) 以上が必要です。 CR0 レジスタなどのコントロールレジスタでは、特権モードが必要 [です。 386p](dot-386p.md) 以降。 このエラーは、を必要とする **NEAR32**、 **FAR32**、および **FLAT** キーワードに対しても生成されます。**386** 以上。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](ml-error-messages.md)
