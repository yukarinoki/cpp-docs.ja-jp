---
title: インライン ファイルの再利用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, reusing NMAKE
- revising inline files
- NMAKE program, inline files
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37544db8076d40e638b6ddf6f340070298229149
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722463"
---
# <a name="reusing-inline-files"></a>インライン ファイルの再利用

インライン ファイルを再利用するには指定 <<*filename*ファイルが定義されている、最初に使用される場合は、再利用*ファイル名*せず << 同一または別のコマンド。 インライン ファイルを作成するコマンドは、ファイルを使用するすべてのコマンドの前に実行する必要があります。

## <a name="see-also"></a>関連項目

[メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)