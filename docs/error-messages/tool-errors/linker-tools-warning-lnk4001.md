---
title: リンカー ツールの警告 LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: d9659b0cf372ff8ebc225b890fb68866872bb3d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194409"
---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001

オブジェクトファイルが指定されていません。使用されるライブラリ

リンカーに1つ以上の .lib ファイルが渡されましたが、.obj ファイルがありませんでした。

リンカーは .obj ファイルにアクセスできる .lib ファイル内の情報にアクセスできないため、この警告は、他のリンカーオプションを明示的に指定する必要があることを示します。 たとえば、 [/MACHINE](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または[/entry](../../build/reference/entry-entry-point-symbol.md)オプションを指定する必要がある場合があります。
