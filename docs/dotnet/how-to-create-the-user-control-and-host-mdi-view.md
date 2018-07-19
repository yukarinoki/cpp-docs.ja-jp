---
title: '方法: ユーザー コントロールとホスト MDI ビューを作成 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 449f0026cd2d7603ceb190cc747138189313974f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136484"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>方法: ユーザー コントロールを作成し、MDI ビューをホストする
次の手順では、.NET Framework ユーザー コントロールを作成し、そのユーザー コントロールをコントロール クラス ライブラリ (特に Windows コントロール ライブラリ プロジェクト) に作成し、プロジェクトをアセンブリにコンパイルする方法について説明します。 コントロールから派生したクラスを使用する MFC アプリケーションから使用できます[CView クラス](../mfc/reference/cview-class.md)と[CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)です。  
  
 コントロールを作成し、Windows フォーム ユーザー コントロール クラス ライブラリの作成方法については、次を参照してください。[する方法: ユーザー コントロールの作成](/dotnet/framework/winforms/controls/how-to-author-composite-controls)です。  
  
> [!NOTE]
>  サードパーティのグリッド コントロールなどの Windows フォーム コントロールは、MFC アプリケーションでホストした場合に適切に動作しないことがあります。 この問題の推奨回避策は、Windows フォーム ユーザー コントロールを MFC アプリケーションに配置し、サードパーティのグリッド コントロールをユーザー コントロールの内部に配置することです。  
  
 この手順の前提条件」の手順に従って、WindowsFormsControlLibrary1 をという名前の Windows フォーム コントロール ライブラリ プロジェクトを作成した[する方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)です。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  MFC アプリケーション プロジェクトを作成します。  
  
     **ファイル**メニューの **新規**、クリックして**プロジェクト**です。 **Visual C**フォルダーを選択**MFC アプリケーション**です。  
  
     **名前**ボックスに、入力`MFC02`を変更して、**ソリューション**設定**ソリューションに追加**です。 **[OK]** をクリックします。  
  
     **MFC アプリケーション ウィザード**すべての既定値をそのまま使用し、クリックして**完了**です。 これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。  
  
2.  共通言語ランタイム (CLR: Common Language Runtime) に対するサポートをプロジェクトに構成します。  
  
     **ソリューション エクスプ ローラー**を右クリックし、`MFC01`プロジェクト ノード、および選択**プロパティ**コンテキスト メニュー。 **プロパティ ページ** ダイアログ ボックスが表示されます。  
  
     **構成プロパティ****全般**です。 下にある、**プロジェクトの既定値**セクションで、設定**共通言語ランタイム サポート**に**共通言語ランタイム サポート (/clr)** です。  
  
     [**構成プロパティ**、展開**C と C++** ] をクリックし、**全般**ノード。 設定**デバッグ情報の形式**に**プログラム データベース (/Zi)** です。  
  
     クリックして、**コード生成**ノード。 設定**最小リビルドを有効にする**に**いいえ (/Gm-)** です。 設定**基本ランタイム チェック**に**既定**です。  
  
     をクリックして**OK**して変更を適用します。  
  
3.  stdafx.h に、次の行を追加します。  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  .NET コントロールへの参照を追加します。  
  
     **ソリューション エクスプ ローラー**を右クリックし、`MFC02`プロジェクト ノードを選択**追加**、**参照**です。 **プロパティ ページ**、 をクリックして**新しい参照の追加**、windowsformscontrollibrary1 (下にある、**プロジェクト** タブ)、 をクリック**OK**. 形式での参照を追加、 [/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプション、プログラムをコンパイルできるように; に WindowsFormsControlLibrary1.dll がコピー、`MFC02`プログラムを実行できるように、プロジェクト ディレクトリ。  
  
5.  stdafx.h で次の行を見つけます。  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     その上に次の行を追加します。  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  継承するように、ビュー クラスを変更[CWinFormsView](../mfc/reference/cwinformsview-class.md)です。  
  
     MFC02View.h で置き換えます[CView](../mfc/reference/cview-class.md)で[CWinFormsView](../mfc/reference/cwinformsview-class.md)コードは次のように表示されるようにします。  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     MDI アプリケーションに追加のビューを追加する場合を呼び出す必要があります[とき](../mfc/reference/cwinapp-class.md#adddoctemplate)ビューごとに作成します。  
  
7.  MFC02View.cpp ファイルを変更して、IMPLEMENT_DYNCREATE マクロとメッセージ マップで CView を CWinFormsView に変更し、既存の空のコンストラクターを次に示すコンストラクターに置き換えます。  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  プロジェクトをビルドして実行します。  
  
     **ソリューション エクスプ ローラー**、MFC02 を右クリックし **スタートアップ プロジェクトとして設定**です。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)