---
description: '詳細については、「方法: ユーザーコントロールを作成し、MDI ビューをホストする」を参照してください。'
title: '方法: ユーザー コントロールを作成し、MDI ビューをホストする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: d05d2132c4382365b1de16490481049cb43ffe22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328771"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>方法: ユーザー コントロールを作成し、MDI ビューをホストする

次の手順では、.NET Framework ユーザー コントロールを作成し、そのユーザー コントロールをコントロール クラス ライブラリ (特に Windows コントロール ライブラリ プロジェクト) に作成し、プロジェクトをアセンブリにコンパイルする方法について説明します。 このコントロールは、 [CView クラス](../mfc/reference/cview-class.md) および [CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)から派生したクラスを使用する MFC アプリケーションから使用できます。

Windows フォームユーザーコントロールを作成し、コントロールクラスライブラリを作成する方法の詳細については、「 [方法: ユーザーコントロール](/dotnet/framework/winforms/controls/how-to-author-composite-controls)を作成する」を参照してください。

> [!NOTE]
> サードパーティのグリッド コントロールなどの Windows フォーム コントロールは、MFC アプリケーションでホストした場合に適切に動作しないことがあります。 この問題の推奨回避策は、Windows フォーム ユーザー コントロールを MFC アプリケーションに配置し、サードパーティのグリッド コントロールをユーザー コントロールの内部に配置することです。

この手順では、 [「方法: ダイアログボックスにユーザーコントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)する」の手順に従って、WindowsFormsControlLibrary1 という名前の Windows フォームコントロールライブラリプロジェクトを作成していることを前提としています。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. MFC アプリケーション プロジェクトを作成します。

   [ **ファイル** ] メニューの [ **新規作成**] をポイントし、[ **プロジェクト**] をクリックします。 **Visual C++** フォルダーで、[ **MFC アプリケーション**] を選択します。

   [**名前**] ボックスに「」と入力し、[ソリューション] `MFC02` の設定を [**ソリューションに追加**] に変更します。  **[OK]** をクリックします。

   **MFC アプリケーションウィザード** で、すべての既定値をそのまま使用し、[**完了**] をクリックします。 これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。

1. 共通言語ランタイム (CLR: Common Language Runtime) に対するサポートをプロジェクトに構成します。

   **ソリューションエクスプローラー** で、プロジェクトノードを右クリックし、 `MFC01` コンテキストメニューから [**プロパティ**] を選択します。 [ **プロパティページ** ] ダイアログボックスが表示されます。

   [ **構成プロパティ**] で [ **全般**] を選択します。 [ **プロジェクトの既定値** ] セクションで、[ **共通言語ランタイム** サポート] を [ **共通言語ランタイムサポート (/clr)**] に設定します。

   [ **構成プロパティ**] で、[ **C/c + +** ] を展開し、[ **全般** ] ノードをクリックします。 **デバッグ情報の形式** を **プログラムデータベース (/zi)** に設定します。

   [ **コード生成** ] ノードをクリックします。 **最小リビルドを有効** にする **(/Gm-)** を設定します。 また、 **基本ランタイムチェック** を **既定値** に設定します。

   [ **OK** ] をクリックして変更を適用します。

1. *.Pch* (Visual Studio 2017 以前の *stdafx.h* ) で、次の行を追加します。

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET コントロールへの参照を追加します。

   **ソリューションエクスプローラー** で、プロジェクトノードを右クリック `MFC02` し、[**追加**]、[**参照**] の順に選択します。 [ **プロパティ] ページ** で、 **[新しい参照の追加**] をクリックし、[ **プロジェクト** ] タブの下の [WindowsFormsControlLibrary1] を選択して、[ **OK]** をクリックします。 これにより、プログラムがコンパイルされるように、 [/fu](../build/reference/fu-name-forced-hash-using-file.md) コンパイラオプションの形式で参照が追加されます。また、WindowsFormsControlLibrary1.dll をプロジェクトディレクトリにコピーして `MFC02` 、プログラムが実行されるようにします。

1. stdafx.h で次の行を見つけます。

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   その上に次の行を追加します。

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. ビュークラスを変更して、 [CWinFormsView](../mfc/reference/cwinformsview-class.md)から継承されるようにします。

   MFC02View で、 [CView](../mfc/reference/cview-class.md) を [CWinFormsView](../mfc/reference/cwinformsview-class.md) に置き換えて、コードが次のように表示されるようにします。

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI アプリケーションにビューを追加する場合は、作成するビューごとに [CWinApp::、adddoctemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) を呼び出す必要があります。

1. MFC02View.cpp ファイルを変更して、IMPLEMENT_DYNCREATE マクロとメッセージ マップで CView を CWinFormsView に変更し、既存の空のコンストラクターを次に示すコンストラクターに置き換えます。

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. プロジェクトをビルドして実行します。

   **ソリューションエクスプローラー** で、[MFC02] を右クリックし、[**スタートアッププロジェクトに設定**] を選択します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [ **デバッグ** ] メニューの [ **デバッグなしで開始**] をクリックします。

## <a name="see-also"></a>関連項目

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
