---
title: ML の致命的なエラー A1017 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1017
dev_langs:
- C++
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb98eab68da417526a75beaa57870ce906c85a8d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688560"
---
# <a name="ml-fatal-error-a1017"></a>ML の致命的なエラー A1017

**ソースのファイル名がありません。**

ML をリンカーに渡すアセンブリまたはファイルが見つかりませんでした。

対象となるファイル名を指定しないで ML コマンド ライン オプションを指定すると、このエラーが生成されます。 .Asm 拡張機能がないファイルを構成するには、使用、 **/Ta**コマンド ライン オプション。

このエラーは、ML 環境変数には、コマンド ライン オプションが含まれている場合は、パラメーターなしで ML を呼び出すことによって生成することもできます。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>