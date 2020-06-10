---
title: 'データ オブジェクトとデータ ソース : 操作'
ms.date: 11/04/2016
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
ms.openlocfilehash: f1a83511edbf240d9a05d6d489f6cda9453ccea9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620402"
---
# <a name="data-objects-and-data-sources-manipulation"></a>データ オブジェクトとデータ ソース : 操作

データオブジェクトまたはデータソースを作成した後は、データの挿入と削除、データの形式の列挙など、データに対して多くの一般的な操作を実行できます。 この記事では、最も一般的な操作を完了するために必要な手法について説明します。 取り上げるトピックは次のとおりです。

- [データソースへのデータの挿入](#_core_inserting_data_into_a_data_source)

- [データオブジェクトで使用できる形式の確認](#_core_determining_the_formats_available_in_a_data_object)

- [データオブジェクトからのデータの取得](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a>データソースへのデータの挿入

データソースへのデータの挿入方法は、データがすぐに提供されるか、または必要に応じて提供されるかによって異なります。 その可能性は次のとおりです。

### <a name="supplying-data-immediately-immediate-rendering"></a>すぐにデータを提供する (即時レンダリング)

- `COleDataSource::CacheGlobalData`データを提供するすべてのクリップボード形式に対して、を繰り返し呼び出します。 使用するクリップボード形式、データを格納するメモリへのハンドル、およびデータを記述する**FORMATETC**構造体を渡します。

     \- または -

- **STGMEDIUM**構造体を直接操作する場合は、 `COleDataSource::CacheData` 上のオプションでの代わりにを呼び出し `COleDataSource::CacheGlobalData` ます。

### <a name="supplying-data-on-demand-delayed-rendering"></a>必要に応じたデータの提供 (遅延レンダリング)

これは高度なトピックです。

- `COleDataSource::DelayRenderData`データを提供するすべてのクリップボード形式に対して、を繰り返し呼び出します。 使用するクリップボード形式と、必要に応じて、データを記述する**FORMATETC**構造体を渡します。 データが要求されると、フレームワークは `COleDataSource::OnRenderData` を呼び出します。これは、オーバーライドする必要があります。

     \- または -

- オブジェクトを使用し `CFile` てデータを指定する場合は、 `COleDataSource::DelayRenderFileData` 前のオプションではなくを呼び出し `COleDataSource::DelayRenderData` ます。 データが要求されると、フレームワークは `COleDataSource::OnRenderFileData` を呼び出します。これは、オーバーライドする必要があります。

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a>データオブジェクトで使用できる形式の確認

アプリケーションでユーザーがデータを貼り付けられるようにするには、クリップボードに処理できる形式があるかどうかを確認する必要があります。 これを行うには、アプリケーションで次の操作を行う必要があります。

1. `COleDataObject`オブジェクトと**FORMATETC**構造体を作成します。

1. データオブジェクトのメンバー関数を呼び出して、 `AttachClipboard` データオブジェクトをクリップボードのデータに関連付けます。

1. 次のいずれかの操作を行います。

   - `IsDataAvailable`必要な形式が1つまたは2つしかない場合は、データオブジェクトのメンバー関数を呼び出します。 これにより、クリップボードのデータがアプリケーションよりもはるかに多くの形式をサポートする場合の時間が短縮されます。

     \- または -

   - データオブジェクトのメンバー関数を呼び出して、 `BeginEnumFormats` クリップボードで使用可能な形式の列挙を開始します。 次 `GetNextFormat` に、アプリケーションがサポートする形式をクリップボードが返すか、またはそれ以上形式がないまでを呼び出します。

**ON_UPDATE_COMMAND_UI**を使用している場合は、[編集] メニューの [貼り付け] を有効にし、場合によっては特殊な項目を貼り付けることができます。 これを行うには、 `CMenu::EnableMenuItem` またはを呼び出し `CCmdUI::Enable` ます。 コンテナーアプリケーションがメニュー項目とそのタイミングを使用する場合の詳細については、「[メニューとリソース: コンテナーの追加](menus-and-resources-container-additions.md)」を参照してください。

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a>データオブジェクトからのデータの取得

データ形式を決定した後は、データオブジェクトからデータを取得するだけです。 これを行うために、ユーザーはデータを配置する場所を決定し、アプリケーションは適切な関数を呼び出します。 データは、次のいずれかのメディアで使用できます。

|Medium|呼び出す関数|
|------------|----------------------|
|グローバルメモリ ( `HGLOBAL` )|`COleDataObject::GetGlobalData`|
|File ( `CFile` )|`COleDataObject::GetFileData`|
|**STGMEDIUM**構造体 ( `IStorage` )|`COleDataObject::GetData`|

通常、メディアはクリップボード形式と共に指定されます。 たとえば、 **CF_EMBEDDEDSTRUCT**オブジェクトは常に、 `IStorage` **STGMEDIUM**構造体を必要とする中の中にあります。 したがって、 `GetData` **STGMEDIUM**構造体を受け取ることができるのはこれらの関数の唯一の1つであるため、を使用します。

クリップボードの形式が `IStream` または中の場合 `HGLOBAL` 、フレームワークは `CFile` データを参照するポインターを提供できます。 次に、ファイル読み取りを使用して、ファイルからデータをインポートする場合とほぼ同じ方法でデータを取得できます。 基本的に、これは、 `OnRenderData` `OnRenderFileData` データソース内のルーチンとルーチンに対するクライアント側のインターフェイスです。

これで、ユーザーは、同じ形式の他のデータと同じように、ドキュメントにデータを挿入できるようになりました。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドラッグ アンド ドロップ](drag-and-drop-ole.md)

- [クリップボード](clipboard.md)

## <a name="see-also"></a>関連項目

[データ オブジェクトとデータ ソース (OLE)](data-objects-and-data-sources-ole.md)<br/>
[COleDataObject クラス](reference/coledataobject-class.md)<br/>
[COleDataSource クラス](reference/coledatasource-class.md)
