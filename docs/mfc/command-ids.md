---
title: コマンド Id |Microsoft Docs
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
ms.openlocfilehash: 5087c271151793169cbf7350f78750044ccead0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446973"
---
# <a name="command-ids"></a>コマンド ID

コマンドが、コマンド ID だけで完全に説明されている (でエンコードされた、 **WM_COMMAND**メッセージ)。 この ID は、コマンドを生成するユーザー インターフェイス オブジェクトに割り当てられます。 通常、Id に割り当てられているユーザー インターフェイス オブジェクトの機能の名前です。

たとえば、編集 メニューで すべてクリア項目割り当てられる可能性が ID など**ID_EDIT_CLEAR_ALL**します。 クラス ライブラリは特に、フレームワークを処理するなどのコマンドの場合、何らかの Id が組み込まれて**ID_EDIT_CLEAR_ALL**または**ID_FILE_OPEN**します。 その他のコマンド Id 自分で作成します。

メニュー エディター、Visual C の独自のメニューを作成するときに、クラス ライブラリに従うことをお勧めの名前付け規則のように**ID_FILE_OPEN**します。 [標準コマンド](../mfc/standard-commands.md)クラス ライブラリによって定義される標準のコマンドについて説明します。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス オブジェクトとコマンド ID](../mfc/user-interface-objects-and-command-ids.md)

