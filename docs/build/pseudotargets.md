---
title: 疑似ターゲット
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
ms.openlocfilehash: bf0f1e2feb91611222ade366a7644e89cbe22600
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541077"
---
# <a name="pseudotargets"></a>疑似ターゲット

疑似ターゲットは、依存関係の行で、ファイル名の代わりに使用されるラベルです。 存在しない、古いファイルとして解釈されます。 NMAKE では、疑似ターゲットのタイムスタンプが最新のすべての依存関係の前提としています。 依存関係を持たない、現在の時刻と見なされます。 疑似ターゲットをターゲットとして使用する場合、そのコマンドが常に実行します。 疑似ターゲットが依存しているために使用する必要があります、別の依存関係のターゲットとしても表示されます。 ただし、その依存関係はコマンドのブロックを用意する必要はありません。

疑似ターゲットの名前では、ターゲットのファイル名の構文規則に従います。 ただし、名前が、拡張機能を持たない場合 (つまりは含まれません期間)、ファイル名の最大 8 文字を超えることができ、最大 256 文字まで使用できます。

## <a name="see-also"></a>関連項目

[ターゲット](../build/targets.md)