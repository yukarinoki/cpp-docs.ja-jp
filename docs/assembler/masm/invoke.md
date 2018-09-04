---
title: 呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5698acf9986903a1d6d731c1047484a0ce6904
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676518"
---
# <a name="invoke"></a>INVOKE

によって指定されたアドレスで、プロシージャが呼び出す*式*、スタックまたは言語タイプの標準的な呼び出し規則に従ってレジスタで引数を渡すことです。

## <a name="syntax"></a>構文

> INVOKE*式*[、*引数*]

## <a name="remarks"></a>Remarks

プロシージャに渡された各引数は、式、レジスタのペア、またはアドレス式 (式に続く`ADDR`)。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>