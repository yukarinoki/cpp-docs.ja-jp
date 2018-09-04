---
title: ML の致命的でないエラー A2085 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd5ec9f36a4f956b8eeb097b6a8f8eaed89ba2b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681437"
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085

**命令または現在の CPU モードで使用できないレジスタ**

命令、レジスタ、または現在のプロセッサ モードの無効なキーワードを使用しようとしました。

たとえば、32 ビット レジスタが必要な[.386](../../assembler/masm/dot-386.md)以降。 CR0 特権モードが必要などの制御レジスタ[.386P](../../assembler/masm/dot-386p.md)以降。 このエラーを生成することも、 **NEAR32**、 **FAR32**、および**フラット**キーワードで、必要があります **。386**以降。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>