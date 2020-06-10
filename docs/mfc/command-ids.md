---
title: コマンド ID
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: f7d675891904301b16aafe3acb2c294eede6d8d8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619038"
---
# <a name="command-ids"></a>コマンド ID

コマンドは、コマンド ID だけで完全に記述されます ( **WM_COMMAND**メッセージでエンコードされます)。 この ID は、コマンドを生成するユーザーインターフェイスオブジェクトに割り当てられます。 通常、Id には、割り当てられているユーザーインターフェイスオブジェクトの機能の名前が付けられます。

たとえば、[編集] メニューの [すべてクリア] 項目には、 **ID_EDIT_CLEAR_ALL**などの ID が割り当てられる場合があります。 クラスライブラリは、特に、 **ID_EDIT_CLEAR_ALL**や**ID_FILE_OPEN**など、フレームワークが自身を処理するコマンドに対して、いくつかの id を事前します。 他のコマンド Id は自分で作成します。

Visual C++ メニューエディターで独自のメニューを作成する場合は、 **ID_FILE_OPEN**で示されているように、クラスライブラリの名前付け規則に従うことをお勧めします。 [標準コマンド](standard-commands.md)では、クラスライブラリで定義されている標準コマンドについて説明します。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイスオブジェクトとコマンド Id](user-interface-objects-and-command-ids.md)
