---
title: ML の致命的でないエラー A2133 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0df094f5e7135ffb3b9a5f09383e03e411755de3
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678067"
---
# <a name="ml-nonfatal-error-a2133"></a>ML の致命的でないエラー A2133

**登録の呼び出しによって上書き値**

レジスタがプロシージャに引数として渡されましたが、コードを生成して[INVOKE](../../assembler/masm/invoke.md)他の引数を渡すには、レジスタの内容を破棄します。

AX、AL、AH、EAX、DX、DL、DH、および EDX レジスタは、データ変換を実行するアセンブラーで使用できます。

別のレジスタを使用します。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>