---
title: コマンド Id |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1e03f10199c1b582a1a8603a6ea6c93e1d55473
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931233"
---
# <a name="command-ids"></a>コマンド ID
コマンドが、コマンド ID だけで完全に説明されている (でエンコードされた、 **WM_COMMAND**メッセージ)。 この ID は、コマンドを生成するユーザー インターフェイス オブジェクトに割り当てられます。 通常、Id に割り当てられているユーザー インターフェイス オブジェクトの機能の名前です。  
  
 たとえば、編集 メニューの すべてクリア項目割り当てる可能性がある ID など**ID_EDIT_CLEAR_ALL**です。 クラス ライブラリは、framework が処理する自体などのコマンドをいくつかの Id が組み込まれて**ID_EDIT_CLEAR_ALL**または**ID_FILE_OPEN**です。 その他のコマンド Id は、自分で作成したされます。  
  
 メニュー エディター、Visual C で独自のメニューを作成するときに、クラス ライブラリに従うことをお勧めの名前付け規則に示すように**ID_FILE_OPEN**です。 [標準コマンド](../mfc/standard-commands.md)クラス ライブラリで定義されている標準のコマンドについて説明します。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトとコマンド ID](../mfc/user-interface-objects-and-command-ids.md)

