---
title: コマンド修飾子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3739c053797bdccd08310e17bf669413ead0db48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367174"
---
# <a name="command-modifiers"></a>コマンド修飾子
前に、コマンドを必要に応じてスペースまたはタブで区切られた 1 つまたは複数のコマンド修飾子を指定することができます。 同様に、コマンドは、修飾子をインデントする必要があります。  
  
|修飾子|目的|  
|--------------|-------------|  
|@*コマンド*|コマンドが表示されなくなります。 コマンドの表示は削除されません。 既定では、実行されたすべてのコマンドがエコーされます。 /S を使用するメイクファイル全体の表示を抑制使用して**です。サイレント**を抑制する状況、メイクファイルの一部を表示します。|  
|**-**[`number` ]*コマンド*|エラー チェックをオフに*コマンド*です。 既定では、(nmake の) は、コマンドには 0 以外の終了コードが返されるときに停止します。 If -`number`はこれを使用すると、(nmake の) を停止する場合は、終了コードを超えています`number`です。 ダッシュ ボードの間のスペースまたはタブに表示できませんと*数。* 間に少なくとも 1 つのスペースまたはタブに表示する必要があります`number`と*コマンド*です。 /I を使用して、メイクファイル全体のエラー チェックをオフにします。使用して**です。無視**メイクファイルの一部のエラー チェックをオフにします。|  
|**!** *command*|実行*コマンド*各依存ファイルの場合は*コマンド*使用**$ \* \*** (すべての依存ファイルの依存関係で) または **$?** (すべての依存ファイル、依存関係のターゲットより後のタイムスタンプを持つ)。|  
  
## <a name="see-also"></a>関連項目  
 [メイクファイルのコマンド](../build/commands-in-a-makefile.md)