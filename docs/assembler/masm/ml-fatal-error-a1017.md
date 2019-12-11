---
title: ML の致命的なエラー A1017
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 6fb0835cca135fc994866dc2453734d7b3012a64
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856827"
---
# <a name="ml-fatal-error-a1017"></a>ML の致命的なエラー A1017

**ソースファイル名がありません**

ML が、リンカーにアセンブルまたは渡すファイルを見つけることができませんでした。

このエラーは、操作するファイル名を指定せずに ML コマンドラインオプションを指定した場合に生成されます。 拡張子が .asm ではないファイルをアセンブルするには、 **/Ta**コマンドラインオプションを使用します。

ML 環境変数にコマンドラインオプションが含まれている場合は、パラメーターを指定せずに ML を呼び出すことで、このエラーを生成することもできます。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>