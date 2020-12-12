---
description: 詳細については、「MFC のシリアル化」を参照してください。
title: MFC におけるシリアル化
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 278de59c6e091fd59826622553f50503b12602bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217576"
---
# <a name="serialization-in-mfc"></a>MFC におけるシリアル化

この記事では、Microsoft Foundation Class ライブラリ (MFC) に用意されているシリアル化機構について説明し、プログラムの実行間でオブジェクトを永続化できるようにします。

シリアル化とは、ディスクファイルなどの永続的なストレージメディアとの間で、オブジェクトの書き込みまたは読み取りを行うプロセスです。 シリアル化は、プログラムの実行中または実行後に構造化データ (C++ クラスや構造体など) の状態を維持する必要がある場合に適しています。 MFC に用意されているシリアル化オブジェクトを使用すると、これが標準の一貫性のある方法で行われるため、ユーザーは手動でファイル操作を実行する必要がなくなります。

MFC には、クラスでのシリアル化の組み込みサポートが用意さ `CObject` れています。 したがって、から派生し `CObject` たすべてのクラスは、 `CObject` のシリアル化プロトコルを利用できます。

シリアル化の基本的な考え方は、オブジェクトがその現在の状態 (通常、メンバー変数の値によって示されます) を永続ストレージに書き込むことができることです。 オブジェクトは、後でストレージからオブジェクトの状態を読み取り、つまり逆シリアル化することによって、再作成することができます。 シリアル化は、オブジェクトポインターのすべての詳細と、オブジェクトをシリアル化するときに使用されるオブジェクトへの循環参照を処理します。 重要な点は、オブジェクト自体が独自の状態の読み取りと書き込みを行うことです。 したがって、クラスをシリアル化できるようにするには、基本的なシリアル化操作を実装する必要があります。 記事のシリアル化グループに示されているように、この機能をクラスに簡単に追加できます。

MFC では、 `CArchive` シリアル化するオブジェクトとストレージメディアの仲介として、クラスのオブジェクトを使用します。 このオブジェクトは常にオブジェクトに関連付けられます。このオブジェクトは、 `CFile` シリアル化に必要な情報 (ファイル名、要求された操作が読み取りまたは書き込みのいずれであるかなど) を取得します。 シリアル化操作を実行するオブジェクトは、 `CArchive` ストレージメディアの性質に関係なく、オブジェクトを使用できます。

オブジェクトは、 `CArchive` オーバーロードされた挿入 ( **<\<**) and extraction (**>>** ) 演算子を使用して書き込み操作と読み取り操作を実行します。 詳細については、「シリアル化: オブジェクトのシリアル化」の「 [アーカイブによる通じた cobject の格納と読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md) 」を参照してください。

> [!NOTE]
> `CArchive`クラスは、書式設定されたテキストのみを対象とした汎用の iostream クラスと混同しないでください。 クラスは、 `CArchive` バイナリ形式のシリアル化されたオブジェクト用です。

必要に応じて、MFC のシリアル化をバイパスして、永続的なデータストレージ用の独自のメカニズムを作成することができます。 ユーザーのコマンドでシリアル化を開始するクラスメンバー関数をオーバーライドする必要があります。 ID_FILE_OPEN、ID_FILE_SAVE、ID_FILE_SAVE_AS の標準コマンドの [テクニカルノート 22](../mfc/tn022-standard-commands-implementation.md) に記載されている説明を参照してください。

次の記事では、シリアル化に必要な2つの主要なタスクについて説明します。

- [シリアル化: シリアル化可能なクラスの作成](../mfc/serialization-making-a-serializable-class.md)

- [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

この記事では、シリアル化と [データベースの入力/出力](../mfc/serialization-serialization-vs-database-input-output.md) について説明します。これは、データベースアプリケーションでシリアル化が適切な入出力手法であるかを示しています。

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CArchive クラス](../mfc/reference/carchive-class.md)<br/>
[CObject クラス](../mfc/reference/cobject-class.md)<br/>
[CDocument クラス](../mfc/reference/cdocument-class.md)<br/>
[CFile クラス](../mfc/reference/cfile-class.md)
