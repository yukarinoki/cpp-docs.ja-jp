---
title: 'MFC: ドキュメントとビューを用いたデータベース クラスの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fcaee376b53c1d592f02aafc830a35d72f64feeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC : ドキュメントとビューを用いたデータベース クラスの使用
ドキュメント/ビュー アーキテクチャの有無は、MFC データベース クラスを使用することができます。 このトピックでは、ドキュメントとビューの操作を強調します。 これを説明します。  
  
-   [フォーム ベースのアプリケーションを記述する方法](#_core_writing_a_form.2d.based_application)を使用して、`CRecordView`オブジェクト、ドキュメントのメイン ビューとして。  
  
-   [ドキュメントとビューのレコード セット オブジェクトを使用する方法](#_core_using_recordsets_in_documents_and_views)です。  
  
-   [他の考慮事項](#_core_other_factors)です。  
  
 代替方法については、次を参照してください。 [MFC: 用いないデータベース クラスとビュー](../data/mfc-using-database-classes-without-documents-and-views.md)です。  
  
##  <a name="_core_writing_a_form.2d.based_application"></a> フォーム ベースのアプリケーションの作成  
 多くのデータ アクセス アプリケーションは、フォームに基づいています。 ユーザー インターフェイスは、コントロールをユーザーを調べ、入力すると、またはデータの編集を含む形式です。 クラスを使用するのには、アプリケーションのフォーム ベース、`CRecordView`です。 MFC アプリケーション ウィザードを実行し、選択する**ODBC**でクライアントの種類、**データベース サポート** ページで、プロジェクトを使用して`CRecordView`ビュー クラス。
  
 レコード ビューの各オブジェクトはフォーム ベースのアプリケーションへのポインターを格納、`CRecordset`オブジェクト。 フレームワークのレコード フィールド エクス (チェンジ RFX) メカニズムでは、レコード セットと、データ ソース間でデータを交換します。 ダイアログ データでは、レコード セット オブジェクトのフィールド データ メンバーと、フォーム上のコントロールの間 (DDX) メカニズム交換データを交換します。 `CRecordView` 関数も提供既定コマンド ハンドラー形式のレコード間を移動するためです。  
  
 アプリケーション ウィザードを使用して、フォーム ベースのアプリケーションを作成するを参照してください。[フォーム ベースの MFC アプリケーションを作成する](../mfc/reference/creating-a-forms-based-mfc-application.md)と[データベースのサポート、MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)です。  
  
 フォームの詳細については、次を参照してください。[レコード ビュー](../data/record-views-mfc-data-access.md)です。  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a> ドキュメントとビュー内のレコード セットを使用します。  
 多くの単純なフォーム ベースのアプリケーションでは、ドキュメントは必要ありません。 アプリケーションがより複雑な多くの場合、データベースのプロキシとして、ドキュメントを使用する場合は、格納、`CDatabase`データ ソースに接続するオブジェクト。 通常、フォーム ベースのアプリケーションでは、ビューにレコード セット オブジェクトへのポインターを格納します。 他の種類のデータベース アプリケーションは、レコード セットを格納および`CDatabase`ドキュメント内のオブジェクト。 データベース アプリケーションでドキュメントの使用例を次に示します。  
  
-   ローカル コンテキストのレコード セットにアクセスする場合は、作成、`CRecordset`必要に応じて、ドキュメントや、ビューのメンバー関数でローカル オブジェクトです。  
  
     関数のローカル変数として、レコード セット オブジェクトを宣言します。 渡す**NULL** 、コンス トラクターを作成し、一時的なを開くのために、フレームワークが`CDatabase`オブジェクト。 代わりへのポインターを渡す、`CDatabase`オブジェクト。 関数内でレコード セットを使用してを関数が終了したときに自動的に破棄されます。  
  
     渡す場合**NULL**レコード セットのコンス トラクターに、フレームワークは、レコード セットによって返される情報を使用して`GetDefaultConnect`メンバー関数を作成する、`CDatabase`オブジェクトを開きます。 ウィザード実装`GetDefaultConnect`します。  
  
-   レコード セットをドキュメントの有効期間中にアクセスする場合は、1 つまたは複数を埋め込む`CRecordset`ドキュメント内のオブジェクト。  
  
     ドキュメントを初期化するときに、または必要に応じて、レコード セット オブジェクトを構築します。 既に存在する場合、または構築まだ存在しない場合は、レコード セットを開き、レコード セットにポインターを返す関数を記述する場合があります。 閉じる、削除、および、必要に応じて、レコード セットを再作成または呼び出すその**Requery**レコードを更新するメンバー関数。  
  
-   ドキュメントの有効期間中に、データ ソースにアクセスする場合を埋め込む、`CDatabase`オブジェクトまたはへのポインターを格納、`CDatabase`内のオブジェクト。  
  
     `CDatabase`オブジェクトは、データ ソースへの接続を管理します。 ドキュメントの構築時に、自動的にオブジェクトを構築し、呼び出すその**開く**ドキュメントの初期化時に、メンバー関数。 ドキュメントへのポインターを渡すドキュメント メンバー関数内のレコード セット オブジェクトを構築するときに`CDatabase`オブジェクト。 これにより、各レコード セットがそのデータ ソースと関連付けられます。 データベース オブジェクトが破棄されるは、ドキュメントを閉じるときに通常します。 関数のスコープを終了すると、レコード セット オブジェクトが通常破棄されます。  
  
##  <a name="_core_other_factors"></a> その他の要因  
 フォーム ベースのアプリケーションが含まれていない、framework のドキュメントのシリアル化機構を使用するため、削除、無効化、または置換をする可能性があります、`New`と**開く**コマンドを使って、**ファイル**メニュー。 記事を参照して[シリアル化: シリアル化とします。データベースの入力/出力](../mfc/serialization-serialization-vs-database-input-output.md)です。  
  
 作成する場合がありますもフレームワークがサポートする多くのユーザー インターフェイス可能性を使用します。 たとえば、複数を使用する可能性があります`CRecordView`分割ウィンドウ内のオブジェクトは、複数ドキュメント インターフェイス (MDI) 子ウィンドウ、別の複数のレコード セットを開きます。  
  
 ビューには、任意の印刷を実装することができますは、フォーム実装されるか`CRecordView`または、それ以外です。 派生したクラスとして`CFormView`、`CRecordView`が印刷をサポートしていませんが、オーバーライドできます、`OnPrint`印刷を許可するメンバー関数。 詳細については、クラスを参照してください。 [CFormView](../mfc/reference/cformview-class.md)です。  
  
 すべてのドキュメントとビューを使用する可能性がありますされません。 その場合を参照してください[MFC: 用いないデータベース クラスとビュー](../data/mfc-using-database-classes-without-documents-and-views.md)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC データベース クラス (../data/mfc-database-classes-odbc-and-dao.md)