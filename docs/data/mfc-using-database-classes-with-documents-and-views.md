---
title: 'MFC : ドキュメントとビューを用いたデータベース クラスの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
ms.openlocfilehash: e2b073b20b9518667b43c30e7ee3199a84a3ad38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213383"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC : ドキュメントとビューを用いたデータベース クラスの使用

MFC データベースクラスは、ドキュメント/ビューアーキテクチャの有無に関係なく使用できます。 このトピックでは、ドキュメントとビューの操作について説明します。 次のことについて説明します。

- `CRecordView` オブジェクトをドキュメントのメインビューとして使用して[、フォームベースのアプリケーションを作成する方法](#_core_writing_a_form.2d.based_application)。

- [ドキュメントおよびビューでレコードセットオブジェクトを使用する方法](#_core_using_recordsets_in_documents_and_views)。

- [その他の考慮事項](#_core_other_factors)。

代替方法については、「 [MFC: ドキュメントとビューを使用しないデータベースクラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。

##  <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a>フォームベースのアプリケーションの作成

多くのデータアクセスアプリケーションは、フォームに基づいています。 ユーザーインターフェイスは、ユーザーがデータを調べたり、入力したり、編集したりするコントロールを含むフォームです。 アプリケーションをフォームベースにするには、クラス `CRecordView`を使用します。 MFC アプリケーションウィザードを実行し、 **[データベースのサポート]** ページで **[ODBC]** クライアントの種類 を選択すると、プロジェクトはビュークラスに `CRecordView` を使用します。

フォームベースのアプリケーションでは、各レコードビューオブジェクトに `CRecordset` オブジェクトへのポインターが格納されます。 フレームワークのレコードフィールドエクスチェンジ (RFX) メカニズムによって、レコードセットとデータソースの間でデータが交換されます。 ダイアログデータエクスチェンジ (DDX) メカニズムは、レコードセットオブジェクトのフィールドデータメンバーとフォーム上のコントロールとの間でデータを交換します。 `CRecordView` では、フォーム上のレコード間を移動するための既定のコマンドハンドラー関数も用意されています。

アプリケーションウィザードを使用してフォームベースのアプリケーションを作成するには、「[フォームベースの Mfc アプリケーション](../mfc/reference/creating-a-forms-based-mfc-application.md)および[データベースサポートの作成 (mfc アプリケーションウィザード](../mfc/reference/database-support-mfc-application-wizard.md))」を参照してください。

フォームの詳細については、「[レコードビュー](../data/record-views-mfc-data-access.md)」を参照してください。

##  <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a>ドキュメントおよびビューでのレコードセットの使用

単純なフォームベースのアプリケーションの多くは、ドキュメントを必要としません。 アプリケーションが複雑な場合は、データベースのプロキシとしてドキュメントを使用して、データソースに接続する `CDatabase` オブジェクトを格納することをお勧めします。 フォームベースのアプリケーションでは、通常、ビューのレコードセットオブジェクトへのポインターが格納されます。 その他の種類のデータベースアプリケーションでは、レコードセットと `CDatabase` オブジェクトがドキュメントに格納されます。 データベースアプリケーションでドキュメントを使用する場合、次のような可能性があります。

- ローカルコンテキストでレコードセットにアクセスする場合は、必要に応じて、ドキュメントまたはビューのメンバー関数にローカルに `CRecordset` オブジェクトを作成します。

   関数のローカル変数として、レコードセットオブジェクトを宣言します。 コンストラクターに NULL を渡します。これにより、フレームワークは一時 `CDatabase` オブジェクトを作成して開きます。 別の方法として、`CDatabase` オブジェクトへのポインターを渡します。 関数内でレコードセットを使用して、関数が終了したときに自動的に破棄されるようにします。

   レコードセットコンストラクターに NULL を渡すと、フレームワークは、レコードセットの `GetDefaultConnect` メンバー関数によって返された情報を使用して、`CDatabase` オブジェクトを作成し、それを開きます。 ウィザードでは、`GetDefaultConnect` が実装されます。

- ドキュメントの有効期間中にレコードセットにアクセスする場合は、ドキュメントに1つ以上の `CRecordset` オブジェクトを埋め込みます。

   ドキュメントを初期化するとき、または必要に応じて、レコードセットオブジェクトを構築します。 既に存在する場合は、レコードセットへのポインターを返す関数を記述し、まだ存在しない場合は、レコードセットを作成して開くことができます。 必要に応じてレコードセットを閉じ、削除し、再作成するか、`Requery` メンバー関数を呼び出してレコードを更新します。

- ドキュメントの有効期間中にデータソースにアクセスする場合は、`CDatabase` オブジェクトを埋め込むか、`CDatabase` オブジェクトへのポインターを格納します。

   `CDatabase` オブジェクトは、データソースへの接続を管理します。 オブジェクトはドキュメントの構築時に自動的に構築され、ドキュメントを初期化するときにその `Open` メンバー関数を呼び出します。 ドキュメントメンバー関数にレコードセットオブジェクトを構築する場合は、ドキュメントの `CDatabase` オブジェクトへのポインターを渡します。 これにより、各レコードセットがそのデータソースに関連付けられます。 通常、データベースオブジェクトは、ドキュメントを閉じると破棄されます。 レコードセットオブジェクトは、通常、関数のスコープを終了すると破棄されます。

##  <a name="other-factors"></a><a name="_core_other_factors"></a>その他の要因

多くの場合、フォームベースのアプリケーションは、フレームワークのドキュメントシリアル化機構を使用しません。そのため、 **[ファイル]** メニューの **[新規作成]** および **[開く]** コマンドを削除、無効化、または置換することができます。 「シリアル化[: シリアル化とデータベースの入出力](../mfc/serialization-serialization-vs-database-input-output.md)」を参照してください。

また、フレームワークがサポートできる多くのユーザーインターフェイスの可能性を利用することもできます。 たとえば、分割ウィンドウで複数の `CRecordView` オブジェクトを使用したり、複数のレコードセットを複数のマルチドキュメントインターフェイス (MDI) 子ウィンドウで開いたりすることができます。

`CRecordView` を使用して実装されたフォームであるかどうかにかかわらず、ビューに表示される内容の印刷を実装することもできます。 `CFormView`から派生したクラスとして、`CRecordView` は印刷をサポートしていませんが、`OnPrint` メンバー関数をオーバーライドして印刷できるようにすることができます。 詳細については、「クラス[CFormView](../mfc/reference/cformview-class.md)」を参照してください。

ドキュメントとビューをまったく使用しないことがあります。 その場合は、「 [MFC: ドキュメントとビューを使用しないデータベースクラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。

## <a name="see-also"></a>参照

[MFC データベース クラス](../data/mfc-database-classes-odbc-and-dao.md)
