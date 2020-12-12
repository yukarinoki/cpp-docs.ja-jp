---
description: 詳細については、「ファイル間でのデータのシリアル化」を参照してください。
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
ms.openlocfilehash: 58956b2f11b8f0131aae74a6c5b51715fe25c7e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217446"
---
# <a name="serializing-data-to-and-from-files"></a>データのファイルへのシリアル化

永続化の基本的な考え方は、オブジェクトがそのメンバー変数の値で示されている現在の状態を永続ストレージに書き込むことができることです。 後でオブジェクトを再作成するには、永続ストレージからオブジェクトの状態を読み取り、つまり "逆シリアル化" します。 ここで重要な点は、オブジェクト自体が独自の状態の読み取りと書き込みを行うことです。 したがって、クラスを永続化するには、基本的なシリアル化操作を実装する必要があります。

フレームワークでは、[ファイル] メニューの [名前を付けて保存] コマンドと [名前を付けて保存] コマンドに応答して、ディスクファイルにドキュメントを保存するための既定の実装が提供されます。また、[開く] コマンドに応答してディスクファイルからドキュメントを読み込むことができます。 作業がほとんどない場合は、ファイルとの間でデータの書き込みと読み取りを行うドキュメントの機能を実装できます。 重要なことは、ドキュメントクラスの [Serialize](../mfc/reference/cobject-class.md#serialize) メンバー関数をオーバーライドすることです。

MFC アプリケーションウィザードでは、メンバー関数が作成されたドキュメントクラスのスケルトンオーバーライドが配置 `CDocument` `Serialize` されます。 アプリケーションのメンバー変数を実装した後、 `Serialize` ファイルに接続されている "アーカイブオブジェクト" にデータを送信するコードをオーバーライドに入力できます。 [CArchive](../mfc/reference/carchive-class.md)オブジェクトは、C++ iostream ライブラリの **cin** および **cout** 入出力オブジェクトに似ています。 ただし、は `CArchive` 書式設定されたテキストではなくバイナリ形式を書き込み、読み取ります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [シリアル化](../mfc/serialization-in-mfc.md)

- [シリアル化におけるドキュメントのロール](#_core_the_document.92.s_role_in_serialization)

- [シリアル化におけるデータのロール](#_core_the_data.92.s_role_in_serialization)

- [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a> シリアル化におけるドキュメントのロール

フレームワークは、実装されている場合、ドキュメントのメンバー関数を呼び出すことによって、[ファイル] メニューの [開く]、[保存]、[名前を付けて保存] の各コマンドに自動的に応答し `Serialize` ます。 たとえば、ID_FILE_OPEN のコマンドは、アプリケーションオブジェクト内のハンドラー関数を呼び出します。 この処理中に、ユーザーが [ファイルを開く] ダイアログボックスを表示して応答すると、ユーザーが選択したファイル名がフレームワークによって取得されます。 フレームワークは、 `CArchive` ドキュメントにデータを読み込むために設定されたオブジェクトを作成し、アーカイブをに渡し `Serialize` ます。 フレームワークは既にファイルを開いています。 ドキュメントのメンバー関数内のコードは、 `Serialize` アーカイブを通じて内のデータを読み取り、必要に応じてデータオブジェクトを再構築します。 シリアル化の詳細については、「 [シリアル化](../mfc/serialization-in-mfc.md)」を参照してください。

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a> シリアル化におけるデータのロール

一般に、クラス型のデータは、それ自体をシリアル化できる必要があります。 つまり、オブジェクトをアーカイブに渡すときに、そのオブジェクト自体をアーカイブに書き込む方法と、アーカイブからそれ自体を読み取る方法を把握しておく必要があります。 MFC では、この方法でクラスをシリアル化可能にすることがサポートされています。 データ型を定義するクラスを設計し、その型のデータをシリアル化する場合は、シリアル化のためのを設計します。

## <a name="see-also"></a>関連項目

[ドキュメントの使用](../mfc/using-documents.md)
