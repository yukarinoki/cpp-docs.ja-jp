---
title: シリアル化機構のバイパス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25fc281e35fc07151fa609d07be540430a6a1da6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399815"
---
# <a name="bypassing-the-serialization-mechanism"></a>シリアル化機構のバイパス

説明したように、フレームワークはファイルとの間でデータを読み書きする既定の方法を提供します。 アーカイブ オブジェクトをシリアル化するには、多くの優れたアプリケーションのニーズが適しています。 このようなアプリケーションは、全体がメモリにファイルを読み取り、ユーザーがファイルを更新できるようにし、ディスクに再び更新されたバージョンを書き込みます。

ただし、一部のアプリケーションは非常に異なる方法でデータを操作し、これらのアプリケーションのアーカイブをシリアル化は適していません。 例には、データベース プログラム、大きなファイルの部分のみを編集プログラム、テキストのみのファイルの書き込みプログラムおよびデータ ファイルを共有するプログラムが含まれます。

このような場合は、オーバーライドすることができます、 [Serialize](../mfc/reference/cobject-class.md#serialize)を介してファイルのアクションを仲介する別の方法で関数を[CFile](../mfc/reference/cfile-class.md)オブジェクトではなく[CArchive](../mfc/reference/carchive-class.md)オブジェクト。

使用することができます、 `Open`、 `Read`、 `Write`、 `Close`、および`Seek`クラスのメンバー関数`CFile`ファイル ポインターを移動するファイルを開くには、レコード (指定された数のバイトを読み取るファイルで、特定のポイントには、(シーク)) その時点では、ユーザー レコードを更新し、もう一度同じ時点にシークし、レコードをファイルに書き込むできるようにします。 フレームワークは、ファイルを開くし、使用することができます、`GetFile`クラスのメンバー関数`CArchive`へのポインターを取得する、`CFile`オブジェクト。 オーバーライドすることができます、さらに高度で柔軟性の高い使用するため、[かまいません](../mfc/reference/cdocument-class.md#onopendocument)と[呼び出す必要はありません](../mfc/reference/cdocument-class.md#onsavedocument)クラスのメンバー関数`CWinApp`します。 詳細については、クラスを参照してください。 [CFile](../mfc/reference/cfile-class.md)で、 *MFC リファレンス*します。

このシナリオで、`Serialize`しない場合は、たとえば、ドキュメントを閉じるときに最新の状態を保持するファイルのヘッダーの読み書きに何もオーバーライドしません。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](../mfc/using-documents.md)

