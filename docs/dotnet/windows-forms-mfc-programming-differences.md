---
title: Windows フォーム MFC プログラミング上の違い |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ad9e47ba2bb3d9a5e5b21620a4bf4b50177d63b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172672"
---
# <a name="windows-formsmfc-programming-differences"></a>Windows フォームと MFC のプログラミング上の違い
トピックでは、 [MFC における Windows フォーム ユーザー コントロールを使用して](../dotnet/using-a-windows-form-user-control-in-mfc.md)MFC Windows フォームのサポートについて説明します。 .NET Framework または MFC でのプログラミングにあまり慣れていない場合は、このトピックで、.NET Framework と MFC のプログラミング上の違いに関する背景情報を参照してください。  
  
 Windows フォームは、.NET Framework で Microsoft Windows アプリケーションを作成する場合に使用します。 このフレームワークに用意された、オブジェクト指向の、拡張性がある最新のクラスの集合を使用すると、Windows ベースの強力なアプリケーションを開発できます。 Windows フォームを使用すると、さまざまなデータ ソースにアクセスし、Windows フォーム コントロールでデータを表示および編集できる、リッチ クライアント アプリケーションを作成できます。  
  
 ただし、MFC を使い慣れている開発者は、Windows フォームでまだ明示的にサポートされていない種類のアプリケーションを作成することに慣れている場合があります。 Windows フォーム アプリケーションは、MFC ダイアログ アプリケーションとほぼ同等です。 しかし、Windows フォーム アプリケーションには、OLE ドキュメント サーバー/コンテナー、ActiveX ドキュメントなどの他の種類の MFC アプリケーションを直接サポートするインフラストラクチャが用意されていません。また、シングル ドキュメント インターフェイス (SDI)、マルチ ドキュメント インターフェイス (MDI)、およびマルチ トップレベル インターフェイス (MTI) のドキュメント/ビューもサポートしません。 プログラマは、独自のロジックを記述してこれらのアプリケーションを作成できます。  
  
 Windows フォーム アプリケーションの詳細については、次を参照してください。 [Windows フォームの概要](/dotnet/framework/winforms/windows-forms-overview)です。  
  
 MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。  
  
 Windows フォームには、次の MFC ビュー/ドキュメント、およびコマンド ルーティングに相当する機能がありません。  
  
-   シェル統合機能  
  
     MFC は、ドキュメントを右クリックして [開く]、[編集]、[印刷] などの動詞を選択したときにシェルで使用されるダイナミック データ エクスチェンジ (DDE: Dynamic Data Exchange ) コマンドとコマンド ライン引数を処理します。 Windows フォームにはシェル統合機能がないため、Windows フォームはシェルの動詞に応答しません。  
  
-   ドキュメント テンプレート  
  
     MFC では、ドキュメント テンプレートを使用して、MDI モード、SDI モード、または MTI モードのフレーム ウィンドウに含まれているビューを、プログラマが開いたドキュメントに関連付けます。 Windows フォームには、ドキュメント テンプレートに相当する機能がありません。  
  
-   ドキュメント  
  
     MFC はドキュメント ファイルの種類を登録し、シェルからドキュメントを開くときにドキュメントの種類を処理します。 Windows フォームはドキュメントをサポートしません。  
  
-   ドキュメントの状態  
  
     MFC はドキュメントをダーティな状態で維持します。 このため、MFC アプリケーションを終了するとき、MFC アプリケーションを含む最後のビューを閉じるとき、または Windows を終了するときに、ドキュメントを保存するように指示されます。 Windows フォームでは、これに相当する機能がサポートされていません。  
  
-   コマンド  
  
     MFC には、コマンドの概念があります。 メニュー バー、ツール バー、およびコンテキスト メニューのどれを使用しても、[切り取り] や [コピー] などの同じコマンドを呼び出すことができます。 Windows フォームでは、コマンドはメニュー項目などの特定の UI 要素に密接に関連付けられたイベントであるため、すべてのコマンド イベントを明示的にフックする必要があります。 Windows フォームでは、単一のハンドラーで複数のイベントを処理することもできます。 詳細については、次を参照してください。[複数のイベントを Windows フォームの 1 つのイベント ハンドラーを接続する](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms)です。  
  
-   コマンド ルーティング  
  
     MFC のコマンド ルーティングを使用すると、アクティブなビューまたはドキュメントでコマンドを処理できます。 多くの場合、コマンドの意味はビューの種類によって異なるため (たとえば、テキスト エディット ビューの [コピー] の動作とグラフィックス エディターの [コピー] の動作)、コマンドはアクティブなビューで処理する必要があります。 Windows フォームのメニューとツールバーが存在しないため、アクティブなビューの固有の理解は、ビューの種類の別のハンドラーを持つことはできません、 **MenuItem.Click**追加の内部コードを記述することがなくイベント。  
  
-   コマンド更新機構  
  
     MFC にはコマンド更新機構があります。 このため、アクティブなビューまたはドキュメントが、UI 要素の状態 (メニュー項目やツール ボタンの有効化/無効化、チェック状態など) を管理します。 Windows フォームには、コマンド更新機構に相当する機構がありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows フォーム ユーザー コントロールを使用します。](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows フォームのチュートリアル](http://msdn.microsoft.com/en-us/fd44d13d-4733-416f-aefc-32592e59e5d9)