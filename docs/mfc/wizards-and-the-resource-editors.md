---
title: ウィザードおよびリソース エディター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33fb1caa496c34111de133a113433a614ff5eb22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383842"
---
# <a name="wizards-and-the-resource-editors"></a>ウィザードおよびリソース エディター
Visual C には、多くの統合リソース エディターと共に、MFC プログラミングに使用するためのいくつかのウィザードが含まれます。 ActiveX コントロールをプログラミングでは、 [ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)MFC アプリケーション ウィザードのとまったく同様に、目的を果たします。 これらのツールのほとんどの MFC アプリケーションを記述するときに、ツールは大幅に簡略化し、作業内容を高速化します。  
  
##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成するには  
 使用して、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)OLE を含めることができ、データベース サポートする Visual c は、MFC プロジェクトを作成します。 プロジェクト内のファイルを含む、アプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウ クラスです。メニュー、省略可能なツールバーなどの標準リソースその他に必要な Windows ファイルです。省略可能な .rtf ファイルを含む改訂できる標準の Windows のヘルプのトピックと、プログラムのヘルプ ファイルを作成するを強化します。  
  
##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> クラス ビューを使用して、クラスと Windows メッセージを管理するには  
 クラス ビューを使用する Windows メッセージとコマンドに対するハンドラー関数を作成、作成およびクラスの管理クラス メンバー変数を作成するには、オートメーション メソッドとプロパティを作成、データベース クラスの作成します。  
  
> [!NOTE]
>  クラス ビューでは、MFC クラスの仮想関数をオーバーライドすることができます。 クラスおよびオーバーライドする仮想関数を選択します。 プロセスの残りの部分は、次の段落で説明したよう、メッセージ処理に似ています。  
  
 Windows で実行されているアプリケーションは、[メッセージ ドリブン](../mfc/message-handling-and-mapping.md)です。 ユーザーの操作と他の実行中のプログラムで発生するイベントと、Windows、windows のプログラムでメッセージを送信します。 たとえば、ユーザーには、ウィンドウでマウスがクリックすると、Windows 送信、`WM_LBUTTONDOWN`マウスの左ボタンが押されたときに、メッセージ`WM_LBUTTONUP`ボタンが離されると、メッセージします。 Windows にも送信**WM_COMMAND**メッセージをユーザーがメニュー バーのコマンドを選択します。  
  
 MFC フレームワークでは、ドキュメント、ビュー、フレーム ウィンドウ、ドキュメント テンプレート、アプリケーション オブジェクトなどのさまざまなオブジェクト「メッセージを処理できます」です。 このオブジェクトは、「ハンドラー関数」のメンバーの 1 つとして、機能を提供し、フレームワークが受信メッセージをそのハンドラーにマップします。  
  
 プログラミング タスクの大部分がどのオブジェクトにマップするメッセージを選択して、そのマッピングを実装します。 これを行うには、クラス ビューおよび [プロパティ] ウィンドウを使用します。  
  
 [プロパティ] ウィンドウには空のメッセージ ハンドラー メンバー関数が作成され、ソース コード エディターを使用して、ハンドラーの本体を実装します。 作成または、クラス (MFC クラスから派生していない、独自のクラスを含む) と クラス ビューとそのメンバーを編集することができますも。 クラス ビューを使用して、プロジェクトにコードを追加するウィザードについての詳細については、次を参照してください。[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)です。  
  
##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> リソース エディターを使用して作成し、リソースの編集  
 Visual C を使用して[リソース エディター](../windows/resource-editors.md)を作成し、メニューのダイアログ ボックス、カスタム コントロール、アクセラレータ キー、ビットマップ、アイコン、カーソル、文字列、およびバージョン リソースを編集します。 Visual C バージョン 4.0 の時点で、ツールバー エディターによって作成ツールバー簡単にします。  
  
 さらに多くのするためは、Microsoft Foundation Class ライブラリは、共通というファイルを提供します。RES 共通からコピーできます「クリップアート」リソースが含まれます。RES とリソース ファイルに貼り付けます。 共通します。RES には、ツールバーのボタン、一般的なカーソル、アイコン、および詳細が含まれています。 使用して、変更、および、アプリケーションでこれらのリソースを再配布することができます。 詳細については共通します。RES」を参照してください、 [Clipart サンプル](../visual-cpp-samples.md)です。  
  
 MFC アプリケーション ウィザード、Visual C のウィザード、リソース エディター、および MFC フレームワークは、多くの作業を自動的に行うし、コードをはるかに簡単に管理します。 特定のアプリケーション コードの大部分は、ドキュメントとビュー クラスです。  
  
## <a name="see-also"></a>関連項目  
 [クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
