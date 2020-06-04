---
title: リンカー ツールの警告 LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 391a477625b51fd37eacc5d455801ce90d2abbc2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194006"
---
# <a name="linker-tools-warning-lnk4070"></a>リンカー ツールの警告 LNK4070

での/OUT: filename ディレクティブ。EXP が出力ファイル名 ' filename ' と異なります。ディレクティブの無視

.Exp ファイルの作成時に[NAME](../../build/reference/name-c-cpp.md)または[LIBRARY](../../build/reference/library.md)ステートメントで指定された `filename` は、既定で使用されるか、 [/out](../../build/reference/out-output-file-name.md)オプションで指定された出力 `filename` とは異なります。

開発環境で出力ファイルの名前を変更し、プロジェクトの .def ファイルが更新されていない場合は、この警告が表示されます。 この警告を解決するには、.def ファイルを手動で更新してください。

結果の DLL を使用するクライアントプログラムで問題が発生する可能性があります。
