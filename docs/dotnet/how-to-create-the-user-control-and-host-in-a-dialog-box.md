---
description: '詳細については、「方法: ダイアログボックスにユーザーコントロールおよびホストを作成する」を参照してください。'
title: '方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: 400906344f47f7100e52319adb37c39d1fb370e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283966"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する

この記事の手順では、ダイアログベース ([CDialog クラス](../mfc/reference/cdialog-class.md)) MICROSOFT FOUNDATION CLASSES (mfc) プロジェクトを作成していることを前提としていますが、既存の mfc ダイアログボックスに Windows フォームコントロールのサポートを追加することもできます。

### <a name="to-create-the-net-user-control"></a>.NET ユーザー コントロールを作成するには

1. という名前の Visual C# Windows フォームコントロールライブラリプロジェクトを作成 `WindowsFormsControlLibrary1` します。

   **[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックします。 [ **Visual C#** ] フォルダーで、[ **Windows フォームコントロールライブラリ**] を選択します。

   `WindowsFormsControlLibrary1` **[OK]** をクリックして、プロジェクト名を受け入れます。

   既定では、.NET コントロールの名前は `UserControl1` です。

1. `UserControl1` に子コントロールを追加します。

   [ **ツールボックス**] で、[ **すべての Windows フォーム** ] の一覧を開きます。 **ボタン** コントロールをデザインサーフェイスにドラッグし `UserControl1` ます。

   **TextBox** コントロールも追加します。

1. **ソリューションエクスプローラー** で、[ **UserControl1.Designer.cs** ] をダブルクリックして開き、編集します。 TextBox および Button の説明を `private` から `public` に変更します。

1. プロジェクトをビルドします。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. MFC アプリケーション プロジェクトを作成します。

   **[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックします。 **Visual C++** フォルダーで、[ **MFC アプリケーション**] を選択します。

   **[名前]** ボックスに「 `MFC01`」と入力します。 ソリューション設定を [ **ソリューションに追加**] に変更します。 **[OK]** をクリックします。

   **MFC アプリケーションウィザード** で、[アプリケーションの種類] として [**ダイアログベース]** を選択します。 残りの既定の設定をそのまま使用し、[ **完了**] をクリックします。 これにより、MFC ダイアログ ボックスを伴った MFC アプリケーションが作成されます。

1. MFC ダイアログ ボックスに Placeholder コントロールを追加します。

   [ **表示** ] メニューの [ **リソースビュー**] をクリックします。 **リソースビュー** で、**ダイアログ** フォルダーを展開し、をダブルクリックし `IDD_MFC01_DIALOG` ます。 ダイアログリソースが **リソースエディター** に表示されます。

   **ツールボックス** で、[**ダイアログエディター]** の一覧を開きます。 **静的テキスト** コントロールをダイアログリソースにドラッグします。 **静的テキスト** コントロールは、.net Windows フォームコントロールのプレースホルダーとして機能します。 コントロールのサイズが Windows フォーム コントロールとほぼ同じサイズになるように調整します。

   [**プロパティ**] ウィンドウで、**静的テキスト** コントロールの **ID** をに変更 `IDC_CTRL1` し、[ **TabStop** ] プロパティを [ **True**] に変更します。

1. 共通言語ランタイム (CLR: Common Language Runtime) に対するサポートをプロジェクトに構成します。

   **ソリューションエクスプローラー** で、mfc01] プロジェクトノードを右クリックし、[**プロパティ**] をクリックします。

   [ **プロパティページ** ] ダイアログボックスの [ **構成プロパティ**] で、[ **全般**] を選択します。 [ **プロジェクトの既定値** ] セクションで、[ **共通言語ランタイム** サポート] を [ **共通言語ランタイムサポート (/clr)**] に設定します。

   [ **構成プロパティ**] で、[ **C/c + +** ] を展開し、[ **全般** ] ノードを選択します。 **デバッグ情報の形式** を **プログラムデータベース (/zi)** に設定します。

   [ **コード生成** ] ノードを選択します。 **最小リビルドを有効** にする **(/Gm-)** を設定します。 また、 **基本ランタイムチェック** を **既定値** に設定します。

   **[OK]** をクリックして変更を適用します。

1. .NET コントロールへの参照を追加します。

   **ソリューションエクスプローラー** で、mfc01] プロジェクトノードを右クリックし、[**追加**]、[**参照**] の順にクリックします。 [**プロパティ] ページ** で、 **[新しい参照の追加**] をクリックし、[**プロジェクト**] タブの下の [ **WindowsFormsControlLibrary1** ] を選択して、[ **OK]** をクリックします。 これにより、プログラムがコンパイルされるように、 [/fu](../build/reference/fu-name-forced-hash-using-file.md) コンパイラオプションの形式で参照が追加されます。 また、プログラムを実行するために、WindowsFormsControlLibrary1.dll が \MFC01\ プロジェクト フォルダーにコピーされます。

1. Stdafx.h で次の行を見つけます。

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   その上に次の行を追加します。

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. マネージド コントロールを作成するためのコードを追加します。

   最初に、マネージド コントロールを宣言します。 MFC01Dlg.h でダイアログ クラスの宣言に移動し、Protected のスコープにユーザー コントロールのデータ メンバーを次のように追加します。

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   次に、マネージド コントロールの実装を提供します。 MFC01Dlg.cpp の、MFC アプリケーション ウィザードによって生成された `CMFC01Dlg::DoDataExchange` のダイアログ オーバーライド (同一ファイルの `CAboutDlg::DoDataExchange` ではなく) に次のコードを追加して、マネージド コントロールを作成し、静的なプレースホルダー IDC_CTRL1 に関連付けます。

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. プロジェクトをビルドして実行します。

   **ソリューションエクスプローラー** で、[ **mfc01]** ] を右クリックし、[**スタートアッププロジェクトに設定**] をクリックします。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [ **デバッグ** ] メニューの [ **デバッグなしで開始**] をクリックします。 MFC ダイアログ ボックスに Windows フォーム コントロールが表示されます。

## <a name="see-also"></a>関連項目

[MFC ダイアログボックスでの Windows フォームユーザーコントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)
