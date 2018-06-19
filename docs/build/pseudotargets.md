---
title: 擬似ターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67dbc6ae3ad331ab3297b62d00044c3edf679994
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368409"
---
# <a name="pseudotargets"></a>疑似ターゲット
疑似ターゲットは、依存関係行で、ファイル名の代わりに使用されるラベルです。 ファイルが存在しない、古いとして解釈されます。 (Nmake の) では、疑似ターゲットのタイムスタンプは、一番最近のすべての依存関係の前提としています。 依存関係を持たない、現在の時刻と見なされます。 疑似ターゲットがターゲットとして使用されている場合、そのコマンドが常に実行します。 疑似ターゲット依存関係として使用する必要があります、別の依存関係のターゲットとしても表示されます。 ただし、その依存関係はコマンド ブロックする必要はありません。  
  
 疑似ターゲットの名前では、対象のファイル名の構文規則に従います。 ただし、名前に拡張子がない場合 (つまりはピリオドを含まない)、そのファイル名の最大 8 文字を超えることがあり、最大 256 文字まで使用できます。  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)