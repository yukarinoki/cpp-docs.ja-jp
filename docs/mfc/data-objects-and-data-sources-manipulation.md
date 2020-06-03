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
ms.openlocfilehash: a08b6ff274c73d301c156d65aa56fbecca49128c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370550"
---
# <a name="data-objects-and-data-sources-manipulation"></a>データ オブジェクトとデータ ソース : 操作

データ オブジェクトまたはデータ ソースを作成した後は、データの挿入と削除、データの形式の列挙など、データに対して一般的な操作を実行できます。 この資料では、最も一般的な操作を完了するために必要な手法について説明します。 取り上げるトピックは次のとおりです。

- [データ ソースへのデータの挿入](#_core_inserting_data_into_a_data_source)

- [データ オブジェクトで使用できる形式の決定](#_core_determining_the_formats_available_in_a_data_object)

- [データ オブジェクトからのデータの取得](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a>データ ソースへのデータの挿入

データをデータ ソースに挿入する方法は、データが即時に提供されるか、または要求時に提供されるか、およびどのメディアでデータが提供されるかによって異なります。 可能性は以下の通りです。

### <a name="supplying-data-immediately-immediate-rendering"></a>データの即時供給 (即時レンダリング)

- データ`COleDataSource::CacheGlobalData`を指定するすべてのクリップボード形式に対して、繰り返し呼び出します。 使用するクリップボード形式、データを含むメモリへのハンドル、およびオプションでデータを記述する**FORMATETC**構造体を渡します。

     \- または -

- **STGMEDIUM**構造体を直接操作する場合は、上記のオプション`COleDataSource::CacheData`ではなく`COleDataSource::CacheGlobalData`呼び出します。

### <a name="supplying-data-on-demand-delayed-rendering"></a>オンデマンドでのデータの供給 (遅延レンダリング)

これは高度なトピックです。

- データ`COleDataSource::DelayRenderData`を指定するすべてのクリップボード形式に対して、繰り返し呼び出します。 使用するクリップボード形式を渡し、オプションでデータを記述する**FORMATETC**構造体を渡します。 データが要求されると、フレームワークは を呼`COleDataSource::OnRenderData`び出します。

     \- または -

- オブジェクトを`CFile`使用してデータを提供する場合は、`COleDataSource::DelayRenderFileData`前の`COleDataSource::DelayRenderData`オプションではなく呼び出しを行います。 データが要求されると、フレームワークは を呼`COleDataSource::OnRenderFileData`び出します。

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a>データ オブジェクトで使用できる形式の決定

アプリケーションでユーザーがデータを貼り付けることができるようにするには、クリップボードに処理できる形式があるかどうかを知る必要があります。 これを行うには、アプリケーションは次の操作を行う必要があります。

1. `COleDataObject`オブジェクトと**FORMATETC**構造体を作成します。

1. データ オブジェクトの`AttachClipboard`メンバー関数を呼び出して、データ オブジェクトをクリップボード上のデータに関連付けます。

1. 次のいずれかの操作を行います。

   - 必要な書式が 1`IsDataAvailable`つまたは 2 つしかない場合は、データ オブジェクトのメンバー関数を呼び出します。 これにより、クリップボードのデータがアプリケーションよりも大幅に多くの形式をサポートしている場合に、時間を節約できます。

     \- または -

   - クリップボードで使用できる形式の`BeginEnumFormats`列挙を開始するには、データ オブジェクトのメンバー関数を呼び出します。 次に`GetNextFormat`、クリップボードがアプリケーションでサポートされている形式を返すか、それ以上フォーマットがなくなるまで呼び出します。

**ON_UPDATE_COMMAND_UI**を使用している場合は、[編集] メニューの [貼り付け] と [特殊貼り付け] を有効にできます。 これを行うには、または`CMenu::EnableMenuItem`を`CCmdUI::Enable`呼び出します。 メニュー項目といつコンテナー アプリケーションが実行される場合の詳細については、「[メニューとリソース: コンテナーの追加](../mfc/menus-and-resources-container-additions.md)」を参照してください。

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a>データ オブジェクトからのデータの取得

データ形式を決定したら、残りはデータオブジェクトからデータを取得することだけです。 これを行うには、ユーザーがデータを配置する場所を決定し、アプリケーションは適切な関数を呼び出します。 データは、次のいずれかのメディアで利用できます。

|Medium|呼び出す関数|
|------------|----------------------|
|グローバルメモリ`HGLOBAL`( )|`COleDataObject::GetGlobalData`|
|ファイル`CFile`( )|`COleDataObject::GetFileData`|
|**STGMEDIUM**構造`IStorage`( )|`COleDataObject::GetData`|

通常、メディアはクリップボード形式と共に指定されます。 たとえば **、CF_EMBEDDEDSTRUCT**オブジェクトは **、STGMEDIUM** `IStorage`構造を必要とするメディアに常に含まれます。 したがって`GetData`**、STGMEDIUM**構造体を受け入れることができるのは、これらの関数の 1 つだけであるため、使用します。

クリップボード形式が a または`IStream``HGLOBAL`medium の場合、フレームワークはデータを`CFile`参照するポインターを提供できます。 アプリケーションは、ファイル読み取りを使用して、ファイルからデータをインポートする場合とほぼ同じ方法でデータを取得できます。 基本的に、これはデータ ソースの`OnRenderData`ルーチンとの`OnRenderFileData`クライアント側インターフェイスです。

ユーザーは、同じ形式の他のデータと同じように、文書にデータを挿入できるようになりました。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)

- [クリップボード](../mfc/clipboard.md)

## <a name="see-also"></a>関連項目

[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject クラス](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource クラス](../mfc/reference/coledatasource-class.md)
