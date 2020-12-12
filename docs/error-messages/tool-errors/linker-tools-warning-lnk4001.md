---
description: 詳細については、「リンカーツールの警告 LNK4001」を参照してください。
title: リンカー ツールの警告 LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: ceae4b205a7d591eff6de6c745fc379d5422a0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332047"
---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001

オブジェクトファイルが指定されていません。使用されるライブラリ

リンカーに1つ以上の .lib ファイルが渡されましたが、.obj ファイルがありませんでした。

リンカーは .obj ファイルにアクセスできる .lib ファイル内の情報にアクセスできないため、この警告は、他のリンカーオプションを明示的に指定する必要があることを示します。 たとえば、 [/MACHINE](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または [/entry](../../build/reference/entry-entry-point-symbol.md) オプションを指定する必要がある場合があります。
