---
description: '詳細情報: ML の致命的なエラー A1017'
title: ML の致命的なエラー A1017
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: f15896e18721ef149cabd178bca433844a6edef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129442"
---
# <a name="ml-fatal-error-a1017"></a>ML の致命的なエラー A1017

**ソースファイル名がありません**

ML が、リンカーにアセンブルまたは渡すファイルを見つけることができませんでした。

このエラーは、操作するファイル名を指定せずに ML コマンドラインオプションを指定した場合に生成されます。 拡張子が .asm ではないファイルをアセンブルするには、 **/Ta** コマンドラインオプションを使用します。

ML 環境変数にコマンドラインオプションが含まれている場合は、パラメーターを指定せずに ML を呼び出すことで、このエラーを生成することもできます。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](ml-error-messages.md)
