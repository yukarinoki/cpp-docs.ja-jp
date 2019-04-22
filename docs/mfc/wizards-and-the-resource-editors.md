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
ms.openlocfilehash: 41cbb86b4245bd78baecd222b5573ba5e877243a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773828"
---
# <a name="wizards-and-the-resource-editors"></a>ウィザードおよびリソース エディター

Visual C には、多くの統合リソース エディターと共に、MFC のプログラミングには中に使用するためのいくつかのウィザードが含まれます。 ActiveX コントロールのプログラミングには、 [ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)MFC アプリケーション ウィザードのとまったく同様に、目的を果たします。 これらのツールのほとんどの MFC アプリケーションを作成することができます、ツールは大幅に簡略化し、作業を高速化します。

##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成するには

使用して、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)OLE を含めることができますし、データベースのサポート、Visual c MFC プロジェクトを作成します。 プロジェクト内のファイルを含む、アプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウ クラスメニューや、省略可能なツールバーなど、標準のリソースその他の必要な Windows ファイル省略可能な .rtf ファイルを含む改訂できる標準の Windows のヘルプのトピックと、プログラムのヘルプ ファイルを作成するを強化します。

##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> クラス ビューを使用して、クラスと Windows メッセージを管理するには

クラス ビューを使用する Windows メッセージとコマンドのハンドラー関数を作成、作成およびクラスを管理クラス メンバー変数を作成するには、オートメーション メソッドとプロパティを作成、データベースのクラスを作成します。

> [!NOTE]
>  クラス ビューでは、MFC クラスで仮想関数をオーバーライドすることもできます。 クラスと、オーバーライドする関数を選択します。 プロセスの残りの部分は、次の段落で説明されているようにメッセージの処理に似ています。

Windows で実行されているアプリケーションは[メッセージ ドリブン](../mfc/message-handling-and-mapping.md)します。 ユーザーの操作とその他の実行中のプログラムで発生するイベントが発生する Windows プログラムのウィンドウにメッセージを送信します。 たとえば、ユーザーには、ウィンドウでマウスがクリックすると、Windows マウスの左ボタンが押されたときに、WM_LBUTTONDOWN メッセージと送信 WM_LBUTTONUP メッセージ、ボタンが離されたときします。 Windows は、ユーザーがメニュー バーのコマンドを選択したときにも WM_COMMAND メッセージを送信します。

MFC フレームワークでは、ドキュメント、ビュー、フレーム ウィンドウ、ドキュメント テンプレート、およびアプリケーション オブジェクトなどのさまざまなオブジェクト「メッセージを処理できます」。 このオブジェクトは、"ハンドラー function"のメンバーの 1 つとして、機能を提供し、フレームワークが受信メッセージをそのハンドラーにマップします。

プログラミング タスクの大部分は、どのオブジェクトにマップするメッセージを選択して、そのマッピングを実装します。 これを行うには、クラス ビューおよび [プロパティ] ウィンドウを使用します。

[プロパティ] ウィンドウには空のメッセージ ハンドラー メンバー関数が作成され、ソース コード エディターを使用して、ハンドラーの本体を実装します。 作成またはクラス (MFC クラスから派生していない、独自のクラスを含む) とクラス ビューでは、そのメンバーを編集することもできます。 クラス ビューを使用して、プロジェクトにコードを追加するウィザードについての詳細については、次を参照してください。[コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)します。

##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> リソース エディターを使用して作成し、リソースの編集

Visual C を使用して、[リソース エディター](../windows/resource-editors.md)を作成し、メニューのダイアログ ボックス、カスタム コントロール、アクセラレータ キー、ビットマップ、アイコン、カーソル、文字列、およびバージョンのリソースを編集します。 Visual C バージョン 4.0 の時点で、ツール バー エディター ツールバーの作成をより簡単です。

さらに多くするために、Microsoft Foundation Class ライブラリには、一般的なという名前のファイルが用意されています。RES 共通からコピーすることができます「クリップアート」リソースが含まれます。RES と独自のリソース ファイルに貼り付けます。 一般的です。RES には、ツールバーのボタン、一般的なカーソル、アイコン、および詳細が含まれています。 使用して、変更、および、アプリケーションでこれらのリソースを再配布することができます。 共通の詳細についてはします。RES」を参照してください、 [Clipart サンプル](../overview/visual-cpp-samples.md)します。

MFC アプリケーション ウィザード、Visual C のウィザード、リソース エディター、および MFC フレームワークが、多くの作業を行うし、コードがはるかに簡単に管理します。 アプリケーション固有のコードの大部分は、ドキュメントとビュー クラスでです。

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
