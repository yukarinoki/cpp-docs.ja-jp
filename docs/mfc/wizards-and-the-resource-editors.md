---
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
ms.openlocfilehash: 04d9f2cf615636b151af93a3c3880f7357496048
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365276"
---
# <a name="wizards-and-the-resource-editors"></a>ウィザードおよびリソース エディター

Visual C++ には、MFC プログラミングで使用するウィザードと、多数の統合リソース エディターが用意されています。 ActiveX コントロールのプログラミングでは、MFC アプリケーション ウィザードと同様に[、ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)が使用できます。 これらのツールの大部分を使用せずに MFC アプリケーションを作成できますが、ツールを使用すると作業が大幅に簡略化され、処理速度が向上します。

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a>MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成する

MFC[アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)を使用して、VISUAL C++ で MFC プロジェクトを作成します。 プロジェクト内のファイルには、アプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウの各クラスが含まれます。メニューやオプションのツールバーなどの標準リソース。その他の必要な Windows ファイル。プログラムのヘルプ ファイルを作成するために改訂および拡張できる標準の Windows ヘルプ トピックを含むオプションの .rtf ファイル。

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a>クラス ビューを使用してクラスと Windows メッセージを管理する

クラス ビューを使用すると、Windows メッセージとコマンドのハンドラー関数の作成、クラスの作成と管理、クラス メンバー変数の作成、オートメーション のメソッドとプロパティの作成、データベース クラスの作成などを行うことができます。

> [!NOTE]
> クラス ビューは、MFC クラスの仮想関数をオーバーライドする場合にも役立ちます。 オーバーライドするクラスと仮想関数を選択します。 プロセスの残りの部分は、次の段落で説明するように、メッセージ処理に似ています。

Windows で実行されているアプリケーションは[、メッセージ駆動型](../mfc/message-handling-and-mapping.md)です。 実行中のプログラムで発生するユーザーの操作やその他のイベントにより、Windows はプログラム内のウィンドウにメッセージを送信します。 たとえば、ユーザーがウィンドウ内でマウスをクリックすると、マウスの左ボタンを押すとWM_LBUTTONDOWNメッセージが送信され、ボタンが離されるとWM_LBUTTONUPメッセージが送信されます。 また、ユーザーがメニュー バーからコマンドを選択したときに、WM_COMMAND メッセージも送信されます。

MFC フレームワークでは、ドキュメント、ビュー、フレーム ウィンドウ、ドキュメント テンプレート、アプリケーション オブジェクトなど、さまざまなオブジェクトがメッセージを "処理" できます。 このようなオブジェクトは、そのメンバー関数の 1 つとして "ハンドラー関数" を提供し、フレームワークは受信メッセージをそのハンドラーにマップします。

プログラミング タスクの大部分は、どのメッセージをどのオブジェクトにマップするかを選択し、そのマッピングを実装することです。 これを行うには、クラス ビューとクラス[ウィザード](reference/mfc-class-wizard.md)を使用します。

[クラス ウィザード](reference/mfc-class-wizard.md)は空のメッセージ ハンドラー メンバー関数を作成し、ソース コード エディターを使用してハンドラーの本体を実装します。 クラス ビューを使用してクラス (MFC クラスから派生したクラスではなく、独自のクラスを含む) およびそのメンバーを作成または編集することもできます。 クラス ビューの使用の詳細と、コードをプロジェクトに追加するウィザードの詳細については、「[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)」を参照してください。

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a>リソース エディタを使用したリソースの作成と編集

Visual C++[リソース エディター](../windows/resource-editors.md)を使用して、メニュー、ダイアログ ボックス、カスタム コントロール、アクセラレータ キー、ビットマップ、アイコン、カーソル、文字列、およびバージョン リソースを作成および編集します。 Visual C++ バージョン 4.0 では、ツール バー エディターを使用すると、ツールバーの作成が大幅に簡略化されています。

さらに役立つよう、マイクロソフト財団クラス ライブラリには COMMON という名前のファイルが用意されています。RES は、COMMON からコピーできる「クリップ アート」リソースを含んでいます。RES を使用して、独自のリソース ファイルに貼り付けます。 共通。RES には、ツールバーのボタン、共通カーソル、アイコンなどが含まれます。 これらのリソースは、アプリケーションで使用、変更、および再配布できます。 COMMON の詳細については、以下を参照してください。RES を参照してください、[クリップアートのサンプル](../overview/visual-cpp-samples.md)を参照してください。

MFC アプリケーション ウィザード、Visual C++ ウィザード、リソース エディター、および MFC フレームワークは、多くの作業を行い、コードの管理を大幅に簡略化します。 アプリケーション固有のコードの大部分は、ドキュメントクラスとビュークラスにあります。

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
