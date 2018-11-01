---
title: ML の致命的なエラー A1017
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 22a16569364760d0cb1d01011405f7a11dd21cac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560824"
---
# <a name="ml-fatal-error-a1017"></a>ML の致命的なエラー A1017

**ソースのファイル名がありません。**

ML をリンカーに渡すアセンブリまたはファイルが見つかりませんでした。

対象となるファイル名を指定しないで ML コマンド ライン オプションを指定すると、このエラーが生成されます。 .Asm 拡張機能がないファイルを構成するには、使用、 **/Ta**コマンド ライン オプション。

このエラーは、ML 環境変数には、コマンド ライン オプションが含まれている場合は、パラメーターなしで ML を呼び出すことによって生成することもできます。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>