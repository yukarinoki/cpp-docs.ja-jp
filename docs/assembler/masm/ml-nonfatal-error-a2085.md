---
title: ML の致命的でないエラー A2085
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 729f6f38761171c6ddc4cccfc2443c6a2b597bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177189"
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085

**命令または現在の CPU モードで使用できないレジスタ**

命令、レジスタ、または現在のプロセッサ モードの無効なキーワードを使用しようとしました。

たとえば、32 ビット レジスタが必要な[.386](../../assembler/masm/dot-386.md)以降。 CR0 特権モードが必要などの制御レジスタ[.386P](../../assembler/masm/dot-386p.md)以降。 このエラーを生成することも、 **NEAR32**、 **FAR32**、および**フラット**キーワードで、必要があります **。386**以降。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>