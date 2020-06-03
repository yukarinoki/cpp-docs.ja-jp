---
title: '方法: ユーザー コントロールを作成し、MDI ビューをホストする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: 72501ba32d3b8b9a5c5fd8dd0c56f0628642b147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374465"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>方法: ユーザー コントロールを作成し、MDI ビューをホストする

次の手順では、.NET Framework ユーザー コントロールを作成し、そのユーザー コントロールをコントロール クラス ライブラリ (特に Windows コントロール ライブラリ プロジェクト) に作成し、プロジェクトをアセンブリにコンパイルする方法について説明します。 このコントロールは[、CView クラスおよび CWinFormsView クラス](../mfc/reference/cview-class.md)から派生した[CWinFormsView Class](../mfc/reference/cwinformsview-class.md)クラスを使用する MFC アプリケーションから使用できます。

Windows フォーム ユーザー コントロールを作成し、コントロール クラス ライブラリを作成する方法については、「[方法 : ユーザー コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)」を参照してください。

> [!NOTE]
> サードパーティのグリッド コントロールなどの Windows フォーム コントロールは、MFC アプリケーションでホストした場合に適切に動作しないことがあります。 この問題の推奨回避策は、Windows フォーム ユーザー コントロールを MFC アプリケーションに配置し、サードパーティのグリッド コントロールをユーザー コントロールの内部に配置することです。

この手順では、「[方法 : ダイアログ ボックスでユーザー コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」の手順に従って、WindowsFormsControlLibrary1 という名前の Windows フォーム コントロール ライブラリ プロジェクトを作成したことを前提としています。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. MFC アプリケーション プロジェクトを作成します。

   [**ファイル**] メニューの **[新規作成**] をクリックし、[**プロジェクト**] をクリックします。 Visual **C++** フォルダで **、[MFC アプリケーション**] を選択します。

   [**名前]** ボックスに`MFC02`、[ソリューションの設定] を [**ソリューションに追加]** に入力し、変更します。 **Solution** **[OK]** をクリックします。

   MFC**アプリケーション ウィザード**で、すべての既定値をそのまま使用し、[**完了**] をクリックします。 これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。

1. 共通言語ランタイム (CLR: Common Language Runtime) に対するサポートをプロジェクトに構成します。

   **ソリューション エクスプローラー**で、プロジェクト ノード`MFC01`を右クリックし、コンテキスト メニューから **[プロパティ]** を選択します。 [**プロパティ ページ]** ダイアログ ボックスが表示されます。

   [**構成のプロパティ]** で、[**全般**] を選択します。 [**プロジェクトの既定値]** セクションで、[**共通言語ランタイム のサポート**] を **[共通言語ランタイム サポート ] (/clr)** に設定します。

   [**構成プロパティ]** で **、[C/C++]** を展開し、[**全般**] ノードをクリックします。 **デバッグ情報の形式**を**プログラム データベース (/Zi)** に設定します。

   [**コード生成**] ノードをクリックします。 **[最小再構築を有効**にする] を **[いいえ (/Gm-)]** に設定します。 また、[**基本ランタイム チェック]** を **[既定]** に設定します。

   **[OK] を**クリックして変更を適用します。

1. *pch.h* (2017 年以前のバージョンでは*stdafx.h)* に次の行を追加します。

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET コントロールへの参照を追加します。

   **ソリューション エクスプローラ**で、プロジェクト ノード`MFC02`を右クリックし、[**追加**]、[**参照**] の順に選択します。 [**プロパティ ページ**] で 、[**新しい参照の追加**] をクリックし、[**プロジェクト**] タブの [WindowsFormsControlLibrary1] を選択**して、[OK]** をクリックします。 これにより[、/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプションの形式で参照が追加され、プログラムがコンパイルされます。また、プログラムが実行されるように、`MFC02`プロジェクト ディレクトリに WindowsFormsControlLibrary1.dll をコピーします。

1. stdafx.h で次の行を見つけます。

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   その上に次の行を追加します。

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. ビュー クラスを変更して[、CWinFormsView](../mfc/reference/cwinformsview-class.md)から継承するようにします。

   MFC02View.h では、コードが次のように表示されるように[CView](../mfc/reference/cview-class.md)を[CWinFormsView](../mfc/reference/cwinformsview-class.md)に置き換えます。

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI アプリケーションにビューを追加する場合は、作成する各ビューに対して[CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)を呼び出す必要があります。

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

   **ソリューション エクスプローラ**で MFC02 を右クリックし、[**スタートアップ プロジェクトに設定]** を選択します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [**デバッグ**] メニューの [**デバッグなしで開始**] をクリックします。

## <a name="see-also"></a>関連項目

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
