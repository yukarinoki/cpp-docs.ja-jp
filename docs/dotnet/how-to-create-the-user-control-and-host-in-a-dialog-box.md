---
title: '方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20472a80b35318fa4c6d34221a61345de9e40f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136354"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する
この記事の手順は、ダイアログ ベースを作成することを想定しています ([CDialog クラス](../mfc/reference/cdialog-class.md)) が、Microsoft Foundation Classes (MFC) プロジェクトもサポートを追加できます Windows フォーム コントロールの既存の MFC ダイアログ ボックスにします。  
  
### <a name="to-create-the-net-user-control"></a>.NET ユーザー コントロールを作成するには  
  
1.  という名前の Visual c# Windows フォーム コントロール ライブラリ プロジェクトを作成する`WindowsFormsControlLibrary1`です。  
  
     **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。 **Visual c#** フォルダーを選択**Windows フォーム コントロール ライブラリ**です。  
  
     受け入れる、`WindowsFormsControlLibrary1`プロジェクト名をクリックして**OK**です。  
  
     既定では、.NET コントロールの名前は `UserControl1` です。  
  
2.  `UserControl1` に子コントロールを追加します。  
  
     **ツールボックス**を開き、**すべての Windows フォーム** ボックスの一覧です。 ドラッグ、**ボタン**コントロールを`UserControl1`デザイン サーフェイスです。  
  
     追加も、 **TextBox**コントロール。  
  
3.  **ソリューション エクスプ ローラー**をダブルクリックして**UserControl1.Designer.cs**編集用に開きます。 TextBox および Button の説明を `private` から `public` に変更します。  
  
4.  プロジェクトをビルドします。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  MFC アプリケーション プロジェクトを作成します。  
  
     **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。 **Visual C**フォルダーを選択**MFC アプリケーション**です。  
  
     **[名前]** ボックスに「`MFC01`」と入力します。 ソリューションの設定を変更して**ソリューションに追加**です。 **[OK]** をクリックします。  
  
     **MFC アプリケーション ウィザード**、アプリケーションの種類を選択**ダイアログ ベース**です。 残りの既定の設定をそのまま使用し、をクリックして**完了**です。 これにより、MFC ダイアログ ボックスを伴った MFC アプリケーションが作成されます。  
  
2.  MFC ダイアログ ボックスに Placeholder コントロールを追加します。  
  
     **ビュー**  メニューのをクリックして**リソース ビュー**です。 **リソース ビュー**、展開、**ダイアログ**フォルダーおよびダブルクリック`IDD_MFC01_DIALOG`です。 ダイアログ リソースが表示される**リソース エディター**です。  
  
     **ツールボックス**を開き、**ダイアログ エディター**  ボックスの一覧です。 ドラッグ、**静的テキスト**ダイアログ リソースを制御します。 **静的テキスト**コントロールは、.NET Windows フォーム コントロールのプレース ホルダーとして機能します。 コントロールのサイズが Windows フォーム コントロールとほぼ同じサイズになるように調整します。  
  
     **プロパティ**ウィンドウで、変更、 **ID**の**静的テキスト**に制御を`IDC_CTRL1`を変更して、 **TabStop**プロパティを**True**です。  
  
3.  共通言語ランタイム (CLR: Common Language Runtime) に対するサポートをプロジェクトに構成します。  
  
     **ソリューション エクスプ ローラー**mfc01] プロジェクト ノードを右クリックし、[クリックして**プロパティ**です。  
  
     **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ****全般**です。 **プロジェクトの既定値**セクションで、設定**共通言語ランタイム サポート**に**共通言語ランタイム サポート (/clr)** です。  
  
     **構成プロパティ**、展開**C/C++** を選択し、**全般**ノード。 設定**デバッグ情報の形式**に**プログラム データベース (/Zi)** です。  
  
     選択、**コード生成**ノード。 設定**最小リビルドを有効にする**に**いいえ (/Gm-)** です。 設定**基本ランタイム チェック**に**既定**です。  
  
     をクリックして**OK**変更を適用します。  
  
4.  .NET コントロールへの参照を追加します。  
  
     **ソリューション エクスプ ローラー**mfc01] プロジェクト ノードを右クリックし、[クリックして**追加**、**参照**です。 **プロパティ ページ**、 をクリックして**新しい参照の追加** **WindowsFormsControlLibrary1** (下にある、**プロジェクト** タブ)、 をクリック**OK**です。 形式での参照を追加、 [/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプション、プログラムをコンパイルできるようにします。 また、プログラムを実行するために、WindowsFormsControlLibrary1.dll が \MFC01\ プロジェクト フォルダーにコピーされます。  
  
5.  Stdafx.h で次の行を見つけます。  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     その上に次の行を追加します。  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  マネージ コントロールを作成するためのコードを追加します。  
  
     最初に、マネージ コントロールを宣言します。 MFC01Dlg.h でダイアログ クラスの宣言に移動し、Protected のスコープにユーザー コントロールのデータ メンバーを次のように追加します。  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     次に、マネージ コントロールの実装を提供します。 MFC01Dlg.cpp の、MFC アプリケーション ウィザードによって生成された `CMFC01Dlg::DoDataExchange` のダイアログ オーバーライド (同一ファイルの `CAboutDlg::DoDataExchange` ではなく) に次のコードを追加して、マネージ コントロールを作成し、静的なプレースホルダー IDC_CTRL1 に関連付けます。  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  プロジェクトをビルドして実行します。  
  
     **ソリューション エクスプ ローラー**を右クリックして**MFC01**  をクリックし、**スタートアップ プロジェクトとして設定**です。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **デバッグ** メニューのをクリックして**デバッグなしで開始**です。 MFC ダイアログ ボックスに Windows フォーム コントロールが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)