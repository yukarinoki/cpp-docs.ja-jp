---
description: 詳細については、「ウィザードとリソースエディター」を参照してください。
title: ウィザードおよびリソース エディター
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: b493746365809ca6fd193a31d0e7f53917a9646f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284916"
---
# <a name="wizards-and-the-resource-editors"></a>ウィザードおよびリソース エディター

Visual C++ には、多くの統合されたリソースエディターと共に、MFC プログラミングで使用するためのウィザードがいくつか用意されています。 ActiveX コントロールのプログラミングでは、 [Activex コントロールウィザード](../mfc/reference/mfc-activex-control-wizard.md) は、MFC アプリケーションウィザードと同様に機能します。 これらのツールのほとんどを使用せずに MFC アプリケーションを作成することもできますが、ツールを使用すると作業が大幅に簡素化され、速度が向上します。

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a> Mfc アプリケーションウィザードを使用して MFC アプリケーションを作成する

[Mfc アプリケーションウィザード](../mfc/reference/mfc-application-wizard.md)を使用して VISUAL C++ で mfc プロジェクトを作成します。このプロジェクトには、OLE およびデータベースのサポートを含めることができます。 プロジェクト内のファイルには、アプリケーション、ドキュメント、ビュー、フレームウィンドウクラスが含まれています。標準リソース (メニューおよびオプションのツールバーを含む)その他の必要な Windows ファイルまた、必要に応じて、プログラムのヘルプファイルを作成するために変更および拡張できる標準の Windows ヘルプトピックが含まれている .rtf ファイルもあります。

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> クラスビューを使用してクラスと Windows メッセージを管理する

クラスビューを使用すると、Windows のメッセージとコマンドのハンドラー関数の作成、クラスの作成と管理、クラスメンバー変数の作成、オートメーションメソッドとプロパティの作成、データベースクラスの作成などを行うことができます。

> [!NOTE]
> クラスビューを使用すると、MFC クラスの仮想関数をオーバーライドすることもできます。 オーバーライドするクラスと仮想関数を選択します。 残りのプロセスは、次の段落で説明されているように、メッセージ処理に似ています。

Windows で実行されているアプリケーションは、 [メッセージドリブン](../mfc/message-handling-and-mapping.md)です。 実行中のプログラムで発生したユーザー操作やその他のイベントにより、Windows はプログラム内のウィンドウにメッセージを送信します。 たとえば、ユーザーがウィンドウでマウスをクリックすると、Windows は、マウスの左ボタンが押されたときに WM_LBUTTONDOWN メッセージを送信し、ボタンが離されたときに WM_LBUTTONUP メッセージを送信します。 また、ユーザーがメニューバーからコマンドを選択した場合も、WM_COMMAND メッセージが送信されます。

MFC フレームワークでは、ドキュメント、ビュー、フレームウィンドウ、ドキュメントテンプレート、アプリケーションオブジェクトなど、さまざまなオブジェクトがメッセージを "処理" できます。 このようなオブジェクトは、そのメンバー関数の1つとして "ハンドラー関数" を提供し、フレームワークは受信メッセージをハンドラーにマップします。

プログラミングタスクの大部分は、どのメッセージをどのオブジェクトにマップし、そのマッピングを実装するかを選択することです。 これを行うには、クラスビューおよび [クラスウィザード](reference/mfc-class-wizard.md)を使用します。

[クラスウィザード](reference/mfc-class-wizard.md)では、空のメッセージハンドラーメンバー関数を作成し、ソースコードエディターを使用してハンドラーの本体を実装します。 また、クラス (MFC クラスから派生したものではなく、独自のクラスを含む) とそのメンバーをクラスビューで作成または編集することもできます。 クラスビューおよびプロジェクトにコードを追加するウィザードの使用方法の詳細については、「 [コードウィザードを使用](../ide/adding-functionality-with-code-wizards-cpp.md)した機能の追加」を参照してください。

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> リソースエディターを使用してリソースを作成および編集する

Visual C++ [リソースエディター](../windows/resource-editors.md) を使用すると、メニュー、ダイアログボックス、カスタムコントロール、アクセラレータキー、ビットマップ、アイコン、カーソル、文字列、およびバージョンリソースを作成および編集できます。 Visual C++ バージョン4.0 では、ツールバーエディターを使用すると、ツールバーの作成が非常に簡単になります。

さらに多くのことを支援するために、Microsoft Foundation Class ライブラリには COMMON という名前のファイルが用意されています。"クリップアート" リソースが含まれており、これを共通からコピーすることができます。を作成し、独自のリソースファイルに貼り付けます。 的.RES には、ツールバーボタン、一般的なカーソル、アイコンなどが含まれています。 これらのリソースは、アプリケーションで使用、変更、再配布できます。 」を参照してください。「 [クリップアートのサンプル](../overview/visual-cpp-samples.md)」を参照してください。

MFC アプリケーションウィザード、Visual C++ ウィザード、リソースエディター、および MFC フレームワークは、多くの作業を行い、コードをより簡単に管理できるようにします。 アプリケーション固有のコードの大部分は、ドキュメントクラスとビュークラスに含まれています。

## <a name="see-also"></a>関連項目

[クラスを使用して Windows 用のアプリケーションを作成する](../mfc/using-the-classes-to-write-applications-for-windows.md)
