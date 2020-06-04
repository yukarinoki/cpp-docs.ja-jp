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
ms.openlocfilehash: 9e071e0cc25492073cd74ed517284476b6e49ef8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368895"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC : ドキュメントとビューを用いたデータベース クラスの使用

MFC データベース クラスは、ドキュメント/ビュー アーキテクチャの有無にかかわらず使用できます。 このトピックでは、ドキュメントとビューの操作を重点的に説明します。 それは説明します:

- オブジェクトをドキュメントのメイン ビューとして使用して[フォーム ベースのアプリケーションを作成する方法](#_core_writing_a_form.2d.based_application)。 `CRecordView`

- [ドキュメントおよびビューでレコードセット オブジェクトを使用する方法](#_core_using_recordsets_in_documents_and_views)

- [その他の考慮事項](#_core_other_factors):

その他の方法については[、「MFC: ドキュメントとビューを使用しないデータベース クラスの使用」を参照してください](../data/mfc-using-database-classes-without-documents-and-views.md)。

## <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a>フォームベースのアプリケーションの作成

多くのデータ アクセス アプリケーションはフォームに基づいています。 ユーザー インターフェイスは、ユーザーがデータを調べたり、入力したり、編集したりするコントロールを含むフォームです。 申請フォームをベースにするには、class`CRecordView`を使用します。 MFC アプリケーション ウィザードを実行し、[**データベース サポート**] ページで **[ODBC**クライアント`CRecordView`の種類] を選択すると、プロジェクトはビュー クラスに使用します。

フォーム ベースのアプリケーションでは、各レコード ビュー オブジェクトはオブジェクトへの`CRecordset`ポインターを格納します。 フレームワークのレコード フィールド エクスチェンジ (RFX) 機構は、レコードセットとデータ ソースの間でデータを交換します。 ダイアログ データ エクスチェンジ (DDX) 機構は、レコードセット オブジェクトのフィールド データ メンバーとフォーム上のコントロールとの間でデータを交換します。 `CRecordView`また、フォーム上のレコード間を移動するための既定のコマンド ハンドラー関数も提供します。

アプリケーション ウィザードを使用してフォーム ベースのアプリケーションを作成するには、「[フォーム ベースの MFC アプリケーション](../mfc/reference/creating-a-forms-based-mfc-application.md)とデータベース サポートの作成[(MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md))」を参照してください。

フォームの詳細については、「[レコード ビュー](../data/record-views-mfc-data-access.md)」を参照してください。

## <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a>ドキュメントとビューでのレコードセットの使用

多くの単純なフォームベースのアプリケーションでは、ドキュメントは必要ありません。 アプリケーションがより複雑な場合は、データ ソースに接続する`CDatabase`オブジェクトを格納する、データベースのプロキシとしてドキュメントを使用する可能性があります。 フォーム ベースのアプリケーションは、通常、ビューにレコードセット オブジェクトへのポインターを格納します。 他の種類のデータベース アプリケーションでは、`CDatabase`レコードセットとオブジェクトがドキュメントに格納されます。 データベース アプリケーションでドキュメントを使用する場合は、次の方法があります。

- ローカル コンテキストのレコードセットにアクセスする場合は、必要に`CRecordset`応じて、ドキュメントまたはビューのメンバー関数でローカルにオブジェクトを作成します。

   関数のローカル変数としてレコードセット オブジェクトを宣言します。 コンストラクターに NULL を渡すと、フレームワークが一時`CDatabase`オブジェクトを作成して開きます。 代わりに、オブジェクトにポインターを`CDatabase`渡します。 関数内でレコードセットを使用し、関数が終了したときに自動的に破棄されるようにします。

   レコードセット コンストラクターに NULL を渡すと、フレームワークはレコードセットの`GetDefaultConnect`メンバー関数から返される情報を`CDatabase`使用してオブジェクトを作成し、それを開きます。 ウィザードが実装`GetDefaultConnect`されます。

- ドキュメントの有効期間中にレコードセットにアクセスする場合は、ドキュメントに 1`CRecordset`つ以上のオブジェクトを埋め込みます。

   ドキュメントを初期化するとき、または必要に応じてレコードセット オブジェクトを構築します。 レコードセットが既に存在する場合は、そのレコードセットへのポインタを返す関数を記述するか、レコードセットがまだ存在しない場合はレコードセットを構築して開く関数を記述します。 必要に応じてレコードセットを閉じて、削除して再作成するか、`Requery`またはレコードを更新するためにそのメンバー関数を呼び出します。

- ドキュメントの有効期間中にデータ ソースにアクセスする場合は、オブジェクトを`CDatabase`埋め込むか、オブジェクトへの`CDatabase`ポインタを格納します。

   オブジェクト`CDatabase`は、データ ソースへの接続を管理します。 オブジェクトはドキュメントの構築時に自動的に構築され、ドキュメント`Open`を初期化するときにそのメンバー関数を呼び出します。 ドキュメント メンバー関数でレコードセット オブジェクトを構築するときは、ドキュメントの`CDatabase`オブジェクトへのポインターを渡します。 これにより、各レコードセットがデータ ソースに関連付けられます。 通常、データベース オブジェクトは、ドキュメントが閉じると破棄されます。 レコードセット オブジェクトは、通常、関数のスコープを終了すると破棄されます。

## <a name="other-factors"></a><a name="_core_other_factors"></a>その他の要因

フォーム ベースのアプリケーションでは、フレームワークのドキュメントのシリアル化機構を使用できない場合が多いため、[**ファイル]** メニューの **[新規作成**] コマンドと **[開く**] コマンドを削除、無効化、または置換することができます。 [「シリアル化: シリアル化とデータベースの入出力](../mfc/serialization-serialization-vs-database-input-output.md)」を参照してください。

フレームワークがサポートできる多くのユーザー インターフェイスの可能性を利用することもできます。 たとえば、分割ウィンドウで複数`CRecordView`のオブジェクトを使用し、異なるマルチ ドキュメント インターフェイス (MDI) 子ウィンドウで複数のレコードセットを開くことができます。

ビューに含まれるものは、フォームが実装されているか、`CRecordView`他のものであっても、印刷を実装する必要があります。 派生`CFormView`クラス`CRecordView`は印刷をサポートしていませんが、メンバー関数を`OnPrint`オーバーライドして印刷を許可することができます。 詳細については、「[クラス CFormView」を参照してください](../mfc/reference/cformview-class.md)。

ドキュメントとビューをまったく使用したくない場合もあります。 その場合は[、「MFC: ドキュメントとビューを使用しないデータベース クラスの使用」を参照してください](../data/mfc-using-database-classes-without-documents-and-views.md)。

## <a name="see-also"></a>関連項目

[MFC データベース クラス](../data/mfc-database-classes-odbc-and-dao.md)
