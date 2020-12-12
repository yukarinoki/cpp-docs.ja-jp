---
description: 詳細については、「リンカーツールの警告 LNK4102」を参照してください。
title: リンカー ツールの警告 LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: b0977cfa89c0ddb5edbc7dc74428b774331a87e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294458"
---
# <a name="linker-tools-warning-lnk4102"></a>リンカー ツールの警告 LNK4102

削除するデストラクター ' name ' のエクスポートです。イメージが正しく実行されない可能性があります

プログラムは、削除中のデストラクターをエクスポートしようとしました。 生成された削除は DLL の境界を越えて発生する可能性があるため、プロセスが所有していないメモリを解放できます。 指定されたシンボルが .def ファイルに含まれていないこと、およびシンボルがリンカーコマンドラインの **/import** または **/export** オプションの引数としてリストされていないことを確認します。

C ランタイムライブラリを再構築する場合は、このメッセージを無視してもかまいません。
