---
title: ファイルでデータをシリアル化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec6bfbe647045a334af9fe95cd6d1ab40625a51f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-data-to-and-from-files"></a>データのファイルへのシリアル化
永続性の基本的な考え方は、オブジェクトが永続的ストレージにそのメンバー変数の値によって示される、現在の状態を記述できることです。 後で、読み取り、または「を逆シリアル化、」永続的な記憶域からオブジェクトの状態によって、オブジェクトを再作成できます。 ここで重要な点は、オブジェクト自体が読み取りと書き込みが自身の状態を担当することです。 したがって、クラスを永続的な基本的なシリアル化操作を実装してする必要があります。  
  
 フレームワークは、ドキュメントを保存先への応答ファイルをディスクに保存するための既定の実装を提供し、[ファイル] メニューと開いているコマンドへの応答でディスク ファイルからドキュメントを読み込むための名前を付けて保存のコマンド。 ほとんどの作業では、データとファイルからの読み取りし、書き込みするドキュメントの機能を実装できます。 メインすべき行う必要がありますされて、上書き、 [Serialize](../mfc/reference/cobject-class.md#serialize)ドキュメント クラスのメンバー関数。  
  
 MFC アプリケーション ウィザードのスケルトンのオーバーライドを配置する、 **CDocument**メンバー関数は、`Serialize`それが作成するドキュメント クラスです。 アプリケーションのメンバー変数を実装した後に記入すること、 `Serialize` 「アーカイブ オブジェクト」のファイルに接続されているデータを送信するコードで上書きします。 A [CArchive](../mfc/reference/carchive-class.md)オブジェクトがに似ていますが、`cin`と`cout`入力/出力の C++ の iostream ライブラリのオブジェクト。 ただし、`CArchive`書き込みをバイナリ形式でフォーマットされていないテキストを読み取ります。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [シリアル化](../mfc/serialization-in-mfc.md)  
  
-   [シリアル化における、ドキュメントの役割](#_core_the_document.92.s_role_in_serialization)  
  
-   [シリアル化におけるデータの役割](#_core_the_data.92.s_role_in_serialization)  
  
-   [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a> シリアル化における、ドキュメントの役割  
 フレームワークの応答ファイル メニューの開く を自動的に保存、およびドキュメントを呼び出すことによってコマンドとして保存`Serialize`メンバー関数が実装された場合。 `ID_FILE_OPEN`コマンドはたとえば、アプリケーションのオブジェクト ハンドラー関数を呼び出します。 このプロセス中には、ユーザーに表示され、ファイルを開く ダイアログ ボックスに応答して、フレームワークは、ユーザーが選択したファイル名を取得します。 フレームワークを作成、`CArchive`に対して設定されるオブジェクト、ドキュメントへのデータの読み込みとアーカイブを渡します`Serialize`です。 フレームワークは、ファイルを既に開いています。 ドキュメントのコード`Serialize`メンバー関数は、データを読み取り、必要に応じて、データ オブジェクトを再構築、アーカイブを通じてします。 シリアル化の詳細については、記事を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a> シリアル化におけるデータの役割  
 一般に、クラス型のデータは、自体をシリアル化できる必要があります。 つまり、アーカイブにオブジェクトを渡す際に、オブジェクト知っておく必要があるアーカイブに自体を記述する方法と、アーカイブからそれ自体を読み取る方法です。 MFC には、この方法でシリアル化可能なクラスを行うためのサポートが用意されています。 データ型を定義するクラスをデザインすると、その型のデータをシリアル化する場合、シリアル化用にデザインします。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントの使い方](../mfc/using-documents.md)

