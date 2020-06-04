---
title: MFC におけるシリアル化
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: eca4d0357977bc7ef21063718c738ae5bd8e7431
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372747"
---
# <a name="serialization-in-mfc"></a>MFC におけるシリアル化

この資料では、プログラムの実行間にオブジェクトを保持できるようにするための MFC (MFC) で提供されるシリアル化機構について説明します。

シリアル化とは、ディスク ファイルなどの永続記憶媒体との間でオブジェクトを書き込んだり読み取ったりするプロセスです。 シリアル化は、プログラムの実行中または実行後に、構造化データ (C++ クラスや構造体など) の状態を維持する必要がある場合に最適です。 MFC が提供するシリアル化オブジェクトを使用すると、これを標準的かつ一貫した方法で実行できるため、ユーザーは手作業でファイル操作を実行する必要がなくなります。

MFC は、クラス`CObject`でシリアル化をサポートする組み込みサポートを提供します。 したがって、派生`CObject`したすべてのクラスは、シリアル化プロトコル`CObject`を利用できます。

シリアル化の基本的な考え方は、オブジェクトが現在の状態 (通常はメンバー変数の値で示される) を永続ストレージに書き込むことができるようにすることです。 後で、オブジェクトの状態をストレージから読み取るか、逆シリアル化することによって、オブジェクトを再作成できます。 シリアル化は、オブジェクト ポインターのすべての詳細と、オブジェクトをシリアル化するときに使用されるオブジェクトへの循環参照を処理します。 重要な点は、オブジェクト自体が自身の状態の読み取りと書き込みを担当することです。 したがって、クラスをシリアル化できるようにするには、基本的なシリアル化操作を実装する必要があります。 記事のシリアル化グループに示すように、この機能をクラスに簡単に追加できます。

MFC は、シリアル化`CArchive`するオブジェクトとストレージ メディアとの間の仲介としてクラスのオブジェクトを使用します。 このオブジェクトは常に`CFile`オブジェクトに関連付けられており、そこからファイル名や要求された操作が読み取りまたは書き込みのいずれであるかなど、シリアル化に必要な情報を取得します。 シリアル化操作を実行するオブジェクトは、ストレージ`CArchive`メディアの性質に関係なく、オブジェクトを使用できます。

オブジェクト`CArchive`は、オーバーロードされた挿入**<**( )**>>** 演算子と抽出 ( ) 演算子を使用して、書き込み操作と読み取り操作を実行します。 詳細については、「シリアル化: オブジェクトのシリアル化」の[「アーカイブを使用した CObject の格納と読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)」を参照してください。

> [!NOTE]
> クラスを`CArchive`、書式設定されたテキスト専用の汎用 iostream クラスと混同しないでください。 この`CArchive`クラスは、バイナリ形式のシリアル化されたオブジェクト用です。

必要に応じて、MFC シリアル化をバイパスして、永続的なデータストレージ用の独自のメカニズムを作成できます。 ユーザーのコマンドでシリアル化を開始するクラス メンバー関数をオーバーライドする必要があります。 ID_FILE_OPEN、ID_FILE_SAVE、およびID_FILE_SAVE_AS標準コマンドの[テクニカル ノート 22](../mfc/tn022-standard-commands-implementation.md)の説明を参照してください。

次の記事では、シリアル化に必要な 2 つの主要なタスクについて説明します。

- [シリアル化 : シリアル化可能なクラスの作成](../mfc/serialization-making-a-serializable-class.md)

- [シリアル化 : オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

「[シリアル化: シリアル化とデータベース入出力](../mfc/serialization-serialization-vs-database-input-output.md)」では、データベース アプリケーションでシリアル化が適切な入出力手法である場合について説明します。

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CArchive クラス](../mfc/reference/carchive-class.md)<br/>
[Cオブジェクトクラス](../mfc/reference/cobject-class.md)<br/>
[CDocument クラス](../mfc/reference/cdocument-class.md)<br/>
[CFile クラス](../mfc/reference/cfile-class.md)
