---
title: コード ウィザードを使用した機能の追加 (C++)
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.classes
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: 87c46be17c20bf9d592dd2b5c537897fa629e9c2
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57822575"
---
# <a name="adding-functionality-with-code-wizards-c"></a>コード ウィザードを使用した機能の追加 (C++)

一度プロジェクトを作成すると、そのプロジェクトの機能に変更を加えたり、追加したりすることになります。 このようなタスクには、新しいクラスの作成、新しいメンバー関数と変数の追加、オートメーション メソッドとプロパティの追加が含まれます。 コード ウィザードは、これらすべてを実行できるように設計されています。

> [!WARNING]
> 複数の ATL および MFC コード ウィザードが非推奨になっており、Visual Studio の今後のバージョンで削除されます。 これらのウィザードはほとんど使われません。 これらのウィザードを削除しても、ATL と MFC の一般的なサポートには影響ありません。 この非推奨に関するご意見を共有したい場合は、[こちらのアンケート](https://www.surveymonkey.com/r/QDWKKCN)にお答えください。 お客様のご意見は私どもにとって重要です。

> [!NOTE]
>  メッセージ ハンドラーを追加して、そこにメッセージを追加し、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を使用して MFC 仮想関数をオーバーライドできます。

## <a name="accessing-visual-c-code-wizards"></a>Visual C++ コード ウィザードにアクセスする

Visual C++ コード ウィザードには、次の 3 つの場所からアクセスできます。

- **[プロジェクト]** メニューの **[新しい項目の追加]** コマンドによって、`Add New Item` ダイアログ ボックスを表示できます。これは、新しいファイルをプロジェクトに追加するのに役立ちます。 **[クラスの追加]** コマンドでは、[[クラスの追加]](../ide/add-class-dialog-box.md) ダイアログ ボックスが表示されます。このダイアログ ボックスでは、プロジェクトに追加できるクラス タイプごとにウィザードが開かれます。 **[リソースの追加]** コマンドでは、[[リソースの追加]](../windows/add-resource-dialog-box.md) ダイアログ ボックスが表示されます。ここから、プロジェクトに追加するリソースを作成または選択することができます。

   クラス ビューでプロジェクト内のクラスまたはインターフェイスを強調表示している場合、**[プロジェクト]** メニューには次のコマンドも表示されます。

   - **インターフェイスの実装** (コントロール クラスからのみ)

   - **関数の追加**

   - **変数の追加**

   - **Add Connection Point (接続ポイントの追加)** (ATL クラスのみ)

   - **メソッドの追加** (インターフェイスからのみ)

   - **プロパティの追加** (インターフェイスからのみ)

   - **イベントの追加** (コントロール クラスからのみ)

- **ソリューション エクスプローラー**で、任意のフォルダーを右クリックして、ショートカット メニューから **[追加]** をクリックすると、新しいファイルまたは既存のファイル、その他のフォルダー、項目、クラス、リソース、Web 参照をプロジェクトに追加できます。

- [クラス ビュー ウィンドウ](/visualstudio/ide/viewing-the-structure-of-code)から、適切なノードを右クリックして、ショートカット メニューから **[追加]** をクリックすると、関数、変数、クラス、プロパティ、メソッド、イベント、インターフェイス、接続ポイント、またはその他のコードをプロジェクトに追加できます。

   > [!NOTE]
   > Visual Studio では、インターフェイスをプロジェクトに追加するウィザードは提供されません。 [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)を使用してシンプル オブジェクトを追加することで、インターフェイスを ALT プロジェクトに追加するか、[MFC プロジェクトに ATL サポートを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)できます。 また、プロジェクトの .idl ファイルを開き、次のように入力してインターフェイスを作成することもできます。

    ```IDL
    interface IMyInterface {
    };
    ```

   詳細については、「[インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)」および「[Adding Objects and Controls to an ATL Project](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」 (ALT プロジェクトへのオブジェクトとコントロールの追加) を参照してください。

   |コード ウィザードへのアクセス元|説明|
   |-----------------------------|-----------------|
   |新しい項目の追加|[新しい項目の追加] コード ウィザードでは、ソース ファイルを自分のプロジェクトに追加します。 必要に応じて、ファイルを含めるために、追加のディレクトリが作成されます。プロジェクトのビルド エンジンはここでファイルを検索できます。 [項目の追加] アイコンから使用できるコード ウィザードには次が含まれます。<br /><br />- C++ ソース ファイルの追加 (.cpp、.h、.idl、.rc、.srf、.def、.rgs)<br />- Web 開発ファイルの追加 (.html、.asp、.css、.xml)<br />- ユーティリティとリソース ファイルの追加 (.bmp、.cur、.ico、.rct、.sql、.txt)<br /><br />通常、これらのコード ウィザードでユーザーに情報を求めることはありませんが、ファイルが開発ツリーに追加されます。 プロパティ ウィンドウでそのファイルの名前を変更できます。|
   |ソリューション エクスプローラー|ソリューション エクスプローラーから使用できるコード ウィザードは、項目を右クリックしたときのカーソル フォーカスの場所によって異なります。 **[追加]** オプションが項目を右クリックしたときに表示されない場合は、カーソルを開発ツリー内の 1 つ上のレベルに移動して、もう一度試してください。 コード ウィザードでは、カーソルのある場所に関係なく、常に開発ツリーの適切な場所に追加のコードを配置します。 ソリューション エクスプローラーから使用できるコード ウィザードは次のとおりです。<br /><br />- クラスの追加 (新しいコード ウィザードを含む、**[クラスの追加]** ダイアログ ボックスを開きます)。<br />- リソースの追加 (新規、インポート、またはカスタム)。<br />- Web 参照の追加。|
   |クラス ビュー|クラス ビューから使用できるコード ウィザードは、項目を右クリックしたときのカーソル フォーカスの場所によって異なります。 **[追加]** オプションが項目を右クリックしたときに表示されない場合は、カーソルをクラス ツリー内の 1 つ上のレベルに移動して、もう一度試してください。 コード ウィザードでは、カーソルのある場所に関係なく、常に開発ツリーの適切な場所に追加のコードを配置します。 クラス ビューから使用できるコード ウィザードは次のとおりです。<br /><br />- [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)<br />- [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)<br />- [クラスの追加](../ide/adding-a-class-visual-cpp.md)<br />- [インターフェイスの実装](../ide/implement-interface-wizard.md) (コントロール クラスからのみ)<br />- [Add Connection Point (接続ポイントの追加)](../ide/implement-connection-point-wizard.md) (ATL クラスのみ)<br />- [メソッドの追加](../ide/add-method-wizard.md) (インターフェイスからのみ)<br />- [プロパティの追加](../ide/names-add-property-wizard.md) (インターフェイスからのみ)<br />- [イベントの追加](../ide/add-event-wizard.md) (コントロール クラスからのみ)<br /><br />[クラスの追加] を選択すると、**[クラスの追加]** ダイアログ ボックスが開きます。ここでは、すべての新しいクラスの追加コード ウィザードにアクセスできます。|

## <a name="see-also"></a>関連項目

[仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)<br>
[Visual C++ プロジェクトの種類](../build/reference/visual-cpp-project-types.md)<br>
[Visual C++ プロジェクトに対して作成されるファイルの種類](../build/reference/file-types-created-for-visual-cpp-projects.md)
