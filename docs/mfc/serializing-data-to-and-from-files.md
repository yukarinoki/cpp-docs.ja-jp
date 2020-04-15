---
title: データのファイルへのシリアル化
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: 043ba019c6b5ad79db2cedb6314c9e65f14b14b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376934"
---
# <a name="serializing-data-to-and-from-files"></a>データのファイルへのシリアル化

永続性の基本的な考え方は、オブジェクトが、そのメンバー変数の値で示される現在の状態を永続ストレージに書き込むことができるべきであるということです。 後で、オブジェクトの状態を永続的なストレージから読み取るか、つまり "逆シリアル化" することで、オブジェクトを再作成できます。 ここで重要なポイントは、オブジェクト自体が自身の状態の読み取りと書き込みを担当することです。 したがって、クラスを永続的にするには、基本的なシリアル化操作を実装する必要があります。

フレームワークは、[ファイル] メニューの [保存] コマンドと [名前を付けて保存] コマンドに応じてドキュメントをディスク ファイルに保存する既定の実装を提供し、[開く] コマンドに応答してディスク ファイルからドキュメントを読み込みます。 作業が非常に少ない場合は、ファイルに対してドキュメントのデータを書き込んだり読み取りしたりできる機能を実装できます。 主な操作は、ドキュメント クラスの[Serialize](../mfc/reference/cobject-class.md#serialize)メンバー関数をオーバーライドすることです。

MFC アプリケーション ウィザードは、作成する`CDocument`ドキュメント クラスにメンバー関数`Serialize`のスケルトン オーバーライドを配置します。 アプリケーションのメンバー変数を実装した後、ファイルに接続された "アーカイブ`Serialize`オブジェクト" にデータを送信するコードをオーバーライドに入力できます。 [CArchive](../mfc/reference/carchive-class.md)オブジェクトは、C++ iostream ライブラリの**cin**および**cout**入出力オブジェクトに似ています。 ただし、`CArchive`テキスト形式ではなくバイナリ形式の書き込みと読み取りが行われます。

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [シリアル化](../mfc/serialization-in-mfc.md)

- [シリアル化におけるドキュメントの役割](#_core_the_document.92.s_role_in_serialization)

- [シリアル化におけるデータの役割](#_core_the_data.92.s_role_in_serialization)

- [シリアル化メカニズムのバイパス](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a>シリアル化におけるドキュメントの役割

フレームワークは、ドキュメントのメンバー関数が実装されている場合は、ドキュメントのメンバー関数を呼び出すことによって、[ファイル]`Serialize`メニューの [開く]、[保存]、および [名前を付けて保存] のコマンドに自動的に応答します。 たとえば、ID_FILE_OPENコマンドは、アプリケーション オブジェクトのハンドラー関数を呼び出します。 このプロセス中に、ユーザーは [ファイルを開く] ダイアログ ボックスを表示して応答し、フレームワークはユーザーが選択したファイル名を取得します。 フレームワークは、ドキュメント`CArchive`にデータを読み込むために設定されたオブジェクトを作成し、アーカイブ`Serialize`を に渡します。 フレームワークは既にファイルを開いています。 ドキュメントの`Serialize`メンバー関数のコードは、アーカイブを通じてデータを読み取り、必要に応じてデータ オブジェクトを再構築します。 シリアル化の詳細については、「[シリアル化](../mfc/serialization-in-mfc.md)」を参照してください。

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a>シリアル化におけるデータの役割

一般に、クラス型データは自身をシリアル化できる必要があります。 つまり、オブジェクトをアーカイブに渡すとき、オブジェクトはアーカイブに自身を書き込む方法と、アーカイブから自分自身を読み取る方法を知っている必要があります。 MFC では、この方法でクラスをシリアル化可能にする機能がサポートされています。 データ型を定義するクラスをデザインし、その型のデータをシリアル化する場合は、シリアル化を設計します。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](../mfc/using-documents.md)
