---
title: MFC におけるシリアル化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd5cf36722dd1ed6ea96dd839bd0935d78df0b32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381024"
---
# <a name="serialization-in-mfc"></a>MFC におけるシリアル化
この記事では、間で永続化するオブジェクトを許可する Microsoft Foundation Class ライブラリ (MFC) でのシリアル化機構が、プログラムの実行について説明します。  
  
 シリアル化は、ディスク ファイルなどの永続的なストレージ メディアからの書き込みまたはでオブジェクトを読み取り中のプロセスです。 シリアル化は、インストール中またはプログラムの実行後、構造化データ (C++ のクラスまたは構造体) などの状態を維持するために必要な場合の状況に最適です。 MFC によって提供されるシリアル化オブジェクトを使用すると、これを行う標準と一貫性のある形で、ファイル操作を手動で実行する必要性からユーザーを軽減できます。  
  
 MFC クラスでのシリアル化の組み込みサポートを提供する`CObject`です。 すべてのクラスを派生するため、`CObject`活用できる`CObject`のシリアル化します。  
  
 シリアル化の基本的な考え方は、オブジェクトが永続的ストレージに、メンバー変数の値で通常示される、現在の状態を記述できることです。 後で、読み取り、または逆シリアル化、記憶域からオブジェクトの状態によって、オブジェクトを再作成できます。 シリアル化では、オブジェクトのポインターとオブジェクトをシリアル化する際に使用されるオブジェクトを循環参照のすべての詳細を処理します。 重要な点は、オブジェクト自体が読み取りと書き込みが自身の状態を担当することです。 したがって、シリアル化できるクラスは、基本的なシリアル化操作を実装してする必要があります。 アーティクルのシリアル化のグループのようは、簡単にクラスにこの機能を追加します。  
  
 MFC のオブジェクトを使用して、`CArchive`クラスをシリアル化されるオブジェクトと記憶域メディアの間の媒介として。 このオブジェクトが関連付けでは常に、`CFile`からファイル名を含む、シリアル化に必要な情報を取得し、要求された操作は、読み取りまたは書き込みするかどうかのオブジェクト。 シリアル化操作を実行するオブジェクトで使用できる、`CArchive`ストレージ メディアの種類に関係なくオブジェクト。  
  
 A`CArchive`オブジェクトは、オーバー ロードされた挿入を使用して (**<\<**) と抽出 (**>>**) 演算子を書き込んだり読み取ったり、操作を実行します。 詳細については、次を参照してください。[の保存とアーカイブを通じた Cobject の読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)記事シリアル化: オブジェクトのシリアル化します。  
  
> [!NOTE]
>  混同しないでください、`CArchive`書式付きテキストのみの汎用的な iostream のクラスを持つクラス。 `CArchive`クラスは、バイナリ形式でシリアル化されたオブジェクト。  
  
 する場合は、永続的なデータ ストレージ用の独自のメカニズムを作成する MFC シリアル化をバイパスできます。 ユーザーのコマンドでシリアル化を開始する、クラス メンバー関数をオーバーライドする必要があります。 説明を参照[テクニカル ノート 22:](../mfc/tn022-standard-commands-implementation.md)の`ID_FILE_OPEN`、 **ID_FILE_SAVE**、および**ID_FILE_SAVE_AS**標準コマンド。  
  
 次の記事では、シリアル化に必要な 2 つの主なタスクを説明します。  
  
-   [シリアル化: シリアル化可能なクラスの作成](../mfc/serialization-making-a-serializable-class.md)  
  
-   [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)  
  
 アーティクル[シリアル化: シリアル化とします。データベースの入力/出力](../mfc/serialization-serialization-vs-database-input-output.md)とシリアル化は、データベース アプリケーションでの適切な入力/出力手法について説明します。  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CArchive クラス](../mfc/reference/carchive-class.md)   
 [CObject クラス](../mfc/reference/cobject-class.md)   
 [CDocument クラス](../mfc/reference/cdocument-class.md)   
 [CFile クラス](../mfc/reference/cfile-class.md)
