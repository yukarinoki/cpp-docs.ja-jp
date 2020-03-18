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
ms.openlocfilehash: adbe2a77fb0069e9874ab20a51b3ab08aabbe1f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447005"
---
# <a name="data-objects-and-data-sources-manipulation"></a>データ オブジェクトとデータ ソース : 操作

データオブジェクトまたはデータソースを作成した後は、データの挿入と削除、データの形式の列挙など、データに対して多くの一般的な操作を実行できます。 この記事では、最も一般的な操作を完了するために必要な手法について説明します。 取り上げるトピックは次のとおりです。

- [データソースへのデータの挿入](#_core_inserting_data_into_a_data_source)

- [データオブジェクトで使用できる形式の確認](#_core_determining_the_formats_available_in_a_data_object)

- [データオブジェクトからのデータの取得](#_core_retrieving_data_from_a_data_object)

##  <a name="_core_inserting_data_into_a_data_source"></a>データソースへのデータの挿入

データソースへのデータの挿入方法は、データがすぐに提供されるか、または必要に応じて提供されるかによって異なります。 その可能性は次のとおりです。

### <a name="supplying-data-immediately-immediate-rendering"></a>すぐにデータを提供する (即時レンダリング)

- データを提供するすべてのクリップボード形式に対して `COleDataSource::CacheGlobalData` を繰り返し呼び出します。 使用するクリップボード形式、データを格納するメモリへのハンドル、およびデータを記述する**FORMATETC**構造体を渡します。

     または

- **STGMEDIUM**構造体を直接操作する場合は、上記のオプションの `COleDataSource::CacheGlobalData` ではなく `COleDataSource::CacheData` を呼び出します。

### <a name="supplying-data-on-demand-delayed-rendering"></a>必要に応じたデータの提供 (遅延レンダリング)

これは高度なトピックです。

- データを提供するすべてのクリップボード形式に対して `COleDataSource::DelayRenderData` を繰り返し呼び出します。 使用するクリップボード形式と、必要に応じて、データを記述する**FORMATETC**構造体を渡します。 データが要求されると、フレームワークは `COleDataSource::OnRenderData`を呼び出します。これはオーバーライドする必要があります。

     または

- `CFile` オブジェクトを使用してデータを指定する場合は、前のオプションで `COleDataSource::DelayRenderData` の代わりに `COleDataSource::DelayRenderFileData` を呼び出します。 データが要求されると、フレームワークは `COleDataSource::OnRenderFileData`を呼び出します。これはオーバーライドする必要があります。

##  <a name="_core_determining_the_formats_available_in_a_data_object"></a>データオブジェクトで使用できる形式の確認

アプリケーションでユーザーがデータを貼り付けられるようにするには、クリップボードに処理できる形式があるかどうかを確認する必要があります。 これを行うには、アプリケーションで次の操作を行う必要があります。

1. `COleDataObject` オブジェクトと**FORMATETC**構造体を作成します。

1. データオブジェクトの `AttachClipboard` メンバー関数を呼び出して、データオブジェクトをクリップボードのデータに関連付けます。

1. 以下のいずれかを実行します。

   - 必要な形式が1つまたは2つしかない場合は、データオブジェクトの `IsDataAvailable` メンバー関数を呼び出します。 これにより、クリップボードのデータがアプリケーションよりもはるかに多くの形式をサポートする場合の時間が短縮されます。

     \- または -

   - データオブジェクトの `BeginEnumFormats` メンバー関数を呼び出して、クリップボードで使用可能な形式の列挙を開始します。 次に、アプリケーションがサポートする形式がクリップボードから返されるまで、または形式がなくなるまで `GetNextFormat` を呼び出します。

**ON_UPDATE_COMMAND_UI**を使用している場合は、[編集] メニューの [貼り付け] を有効にし、場合によっては特殊な項目を貼り付けることができます。 これを行うには、`CMenu::EnableMenuItem` または `CCmdUI::Enable`を呼び出します。 コンテナーアプリケーションがメニュー項目とそのタイミングを使用する場合の詳細については、「[メニューとリソース: コンテナーの追加](../mfc/menus-and-resources-container-additions.md)」を参照してください。

##  <a name="_core_retrieving_data_from_a_data_object"></a>データオブジェクトからのデータの取得

データ形式を決定した後は、データオブジェクトからデータを取得するだけです。 これを行うために、ユーザーはデータを配置する場所を決定し、アプリケーションは適切な関数を呼び出します。 データは、次のいずれかのメディアで使用できます。

|中|呼び出す関数|
|------------|----------------------|
|グローバルメモリ (`HGLOBAL`)|`COleDataObject::GetGlobalData`|
|ファイル (`CFile`)|`COleDataObject::GetFileData`|
|**STGMEDIUM**構造体 (`IStorage`)|`COleDataObject::GetData`|

通常、メディアはクリップボード形式と共に指定されます。 たとえば、 **CF_EMBEDDEDSTRUCT**オブジェクトは常に、 **STGMEDIUM**構造体を必要とする `IStorage` メディアにあります。 したがって、 **STGMEDIUM**構造体を受け取ることができる関数の唯一の1つであるため、`GetData` を使用します。

クリップボードの形式が `IStream` または `HGLOBAL` 中の場合、フレームワークはデータを参照する `CFile` ポインターを提供できます。 次に、ファイル読み取りを使用して、ファイルからデータをインポートする場合とほぼ同じ方法でデータを取得できます。 基本的に、これはデータソース内の `OnRenderData` および `OnRenderFileData` ルーチンへのクライアント側のインターフェイスです。

これで、ユーザーは、同じ形式の他のデータと同じように、ドキュメントにデータを挿入できるようになりました。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドラッグアンドドロップ](../mfc/drag-and-drop-ole.md)

- [クリップボード](../mfc/clipboard.md)

## <a name="see-also"></a>参照

[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject クラス](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource クラス](../mfc/reference/coledatasource-class.md)
