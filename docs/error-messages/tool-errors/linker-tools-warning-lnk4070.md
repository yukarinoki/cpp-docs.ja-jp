---
description: 詳細については、「リンカーツールの警告 LNK4070」を参照してください。
title: リンカー ツールの警告 LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 188c8d88fa4fec332dad80fd5afee346f6099fca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210180"
---
# <a name="linker-tools-warning-lnk4070"></a>リンカー ツールの警告 LNK4070

での/OUT: filename ディレクティブ。EXP が出力ファイル名 ' filename ' と異なります。ディレクティブの無視

`filename`.Exp ファイルの作成時に[NAME](../../build/reference/name-c-cpp.md)または[LIBRARY](../../build/reference/library.md)ステートメントで指定されたは、 `filename` 既定で想定されているか、 [/out](../../build/reference/out-output-file-name.md)オプションで指定された出力とは異なります。

開発環境で出力ファイルの名前を変更し、プロジェクトの .def ファイルが更新されていない場合は、この警告が表示されます。 この警告を解決するには、.def ファイルを手動で更新してください。

結果の DLL を使用するクライアントプログラムで問題が発生する可能性があります。
