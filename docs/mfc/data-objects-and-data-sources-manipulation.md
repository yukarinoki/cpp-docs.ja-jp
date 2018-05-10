---
title: 'データ オブジェクトとデータ ソース: 操作 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c3414734f40ee81689ffa2f160cbbab8306d2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="data-objects-and-data-sources-manipulation"></a>データ オブジェクトとデータ ソース : 操作
データ オブジェクトまたはデータ ソースを作成した後、多数の挿入や削除、データが、形式を列挙する、データなど、データの一般的な操作を実行できます。 この記事では、最も一般的な操作を完了するために必要な手法について説明します。 ここでは、次の内容について説明します。  
  
-   [データ ソースにデータを挿入します。](#_core_inserting_data_into_a_data_source)  
  
-   [データ オブジェクトで使用できる形式を決定します。](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [データ オブジェクトからのデータの取得](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> データ ソースにデータを挿入します。  
 データ ソースにデータを挿入する方法でデータがすぐに提供されているかどうかによって異なります。 またはオンデマンドでと、どの中ことを指定しません。 可能性は次のとおりです。  
  
### <a name="supplying-data-immediately-immediate-rendering"></a>データをすぐに (直接レンダリング) を指定します。  
  
-   呼び出す`COleDataSource::CacheGlobalData`データを指定しているすべてのクリップボード形式の繰り返しです。 使用するには、クリップボードの形式を渡すデータを含むメモリへのハンドルし、必要に応じて、 **FORMATETC**データを記述する構造体。  
  
     - または -  
  
-   直接作業する場合**STGMEDIUM**構造体を呼び出す`COleDataSource::CacheData`の代わりに`COleDataSource::CacheGlobalData`で上記のオプションです。  
  
### <a name="supplying-data-on-demand-delayed-rendering"></a>(遅延レンダリング) 要求時にデータを提供します。  
 これは、高度なトピックです。  
  
-   呼び出す`COleDataSource::DelayRenderData`データを指定しているすべてのクリップボード形式の繰り返しです。 クリップボードの形式を使用するを通過し、必要に応じて、 **FORMATETC**データを記述する構造体。 データが要求されると、フレームワークが呼び出す`COleDataSource::OnRenderData`、オーバーライドする必要があります。  
  
     - または -  
  
-   使用する場合、 `CFile` 、データを提供するオブジェクトを呼び出す`COleDataSource::DelayRenderFileData`の代わりに`COleDataSource::DelayRenderData`前のオプションでします。 データが要求されると、フレームワークが呼び出す`COleDataSource::OnRenderFileData`、オーバーライドする必要があります。  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> データ オブジェクトで使用できる形式を決定します。  
 アプリケーションでは、ユーザーがデータを貼り付けるでできますが、あるかどうかの形式を処理できることをクリップボードにコピーする必要があります。 これを行うには、アプリケーションは、次の操作を行います必要があります。  
  
1.  作成、`COleDataObject`オブジェクトおよび**FORMATETC**構造体。  
  
2.  データ オブジェクトの`AttachClipboard`にデータ オブジェクトをクリップボードのデータに関連付けるメンバー関数。  
  
3.  次のいずれかの操作を行います。  
  
    -   データ オブジェクトの`IsDataAvailable`メンバー関数は 1 つだけを使用する必要があるか 2 つの書式を設定する必要があります。 このはクリップボード上のデータが、アプリケーションよりもはるかに多くの形式をサポートしている場合は時間を節約します。  
  
         - または -  
  
    -   データ オブジェクトの`BeginEnumFormats`クリップボードで使用できる形式の列挙を開始するメンバー関数。 呼び出す`GetNextFormat`クリップボードを返すまで、形式、アプリケーションをサポートしているか、形式がありません。  
  
 使用している場合`ON_UPDATE_COMMAND_UI`、貼り付けや、場合によっては、[編集] メニュー項目を貼り付けを有効にできます。 これを行うには、いずれかを呼び出す`CMenu::EnableMenuItem`または`CCmdUI::Enable`です。 どのようなコンテナーの詳細についてはアプリケーションする必要がありますのメニュー項目と共に実行し、するを参照してください[メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)です。  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> データ オブジェクトからのデータの取得  
 データ形式を決定した後は、データ オブジェクトからデータを取得します。 これを行うには、ユーザーは、データを配置する場所を決定し、アプリケーションが適切な関数を呼び出します。 データは次のメディアのいずれかで使用できます。  
  
|Medium|呼び出す関数|  
|------------|----------------------|  
|グローバル メモリ (`HGLOBAL`)|`COleDataObject::GetGlobalData`|  
|ファイル (`CFile`)|`COleDataObject::GetFileData`|  
|**STGMEDIUM**構造 (`IStorage`)|`COleDataObject::GetData`|  
  
 一般的には、メディアでのクリップボード形式と共に指定されます。 たとえば、 **CF_EMBEDDEDSTRUCT**オブジェクトは常に、`IStorage`が必要なメディア、 **STGMEDIUM**構造体。 したがって、使用するよう`GetData`受け入れることができるこれらの関数の 1 つのみになっているため、 **STGMEDIUM**構造体。  
  
 クリップボードの形式が、ケースの`IStream`または`HGLOBAL`フレームワークを提供できます、中、`CFile`データを参照するポインター。 アプリケーションは、ファイルからデータをインポートする場合と同じ方法で多くのデータを取得するために読み取るファイルを使用できます。 基本的には、これは、クライアント側インターフェイスを`OnRenderData`と`OnRenderFileData`データ ソース内のルーチンです。  
  
 ユーザーは、データをドキュメントに挿入と同様、同じ形式でその他のデータのようになりましたことができます。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
-   [クリップボード](../mfc/clipboard.md)  
  
## <a name="see-also"></a>関連項目  
 [データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject クラス](../mfc/reference/coledataobject-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)
