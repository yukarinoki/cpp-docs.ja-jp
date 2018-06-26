---
title: シリアル化機構のバイパス |Microsoft ドキュメント
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
ms.openlocfilehash: 9252e08fe672f111dcf2b289b1b12891022a318d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931089"
---
# <a name="bypassing-the-serialization-mechanism"></a>シリアル化機構のバイパス
きたように、フレームワークは、ファイルからデータを読み書きする既定の方法を提供します。 ほとんどのアプリケーションのニーズに適したアーカイブ オブジェクトをシリアル化します。 このようなアプリケーションは、ファイルを読み込み、メモリに完全に、によりユーザーは、ファイルを更新でき、し、再度ディスクに更新されたバージョンを書き込みます。  
  
 ただし、一部のアプリケーションがまったく違う方法でデータを操作し、これらのアプリケーションのアーカイブをシリアル化は適していません。 例としては、データベース プログラム、大きなファイルの一部だけを編集するプログラム、プログラム テキストのみのファイルの書き込みをデータ ファイルを共有するプログラムです。  
  
 このような場合は、オーバーライドすることができます、 [Serialize](../mfc/reference/cobject-class.md#serialize)関数を通じたファイル アクションを仲介する別の方法で、 [CFile](../mfc/reference/cfile-class.md)オブジェクトではなく、 [CArchive](../mfc/reference/carchive-class.md)オブジェクト。  
  
 使用することができます、 `Open`、 `Read`、 `Write`、 `Close`、および`Seek`クラスのメンバー関数`CFile`ファイル ポインターを移動するファイルを開くには、レコード (指定された数のバイトを読み取るファイルで特定の時点までには、(シーク)) その時点では、ユーザーが、レコードを更新し、もう一度同じ時点にシークおよびレコードをファイルに書き込むできるようにします。 フレームワークは、ファイルを開くし、使用することができます、`GetFile`クラスのメンバー関数`CArchive`へのポインターを取得する、`CFile`オブジェクト。 オーバーライドすることができますもより高度で柔軟性の高い使用するため、[かまいません](../mfc/reference/cdocument-class.md#onopendocument)と[呼び出す必要はありません](../mfc/reference/cdocument-class.md#onsavedocument)クラスのメンバー関数`CWinApp`です。 詳細については、クラスを参照してください。 [CFile](../mfc/reference/cfile-class.md)で、 *『 MFC リファレンス*です。  
  
 このシナリオでは、`Serialize`をしない場合は、たとえば、ドキュメントを閉じるときに最新に保持するファイルのヘッダーの読み書きがある、何もオーバーライドしません。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントの使い方](../mfc/using-documents.md)

